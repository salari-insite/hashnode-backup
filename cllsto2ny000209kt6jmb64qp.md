---
title: "How to Implement and Use APIs in Software"
datePublished: Sun Aug 27 2023 02:19:20 GMT+0000 (Coordinated Universal Time)
cuid: cllsto2ny000209kt6jmb64qp
slug: how-to-implement-and-use-apis-in-software
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/95YRwf6CNw8/upload/4fb5805eb095430f66b2cb4a87e894a6.jpeg
tags: software-development, web-development, apis, coding

---

In this article, I'm going to cover what APIs are in general and provide an in-depth real example that you can follow along with.

---

# What are APIs?

On the most basic level, application programming interfaces (APIs) are just lines of code that instruct how two separate software components transmit information to each other. When an API function is called, two processes occur. The first process is **Software Component A** sending a *request* to **Software Component B**, and the second process is **Software Component B** sending a *response* to **Software Component A.**

Here's a simple example: let's say that I'm tracking my daily body weight and storing the data in a simple text file. If I want to automate the process of calculating my weekly averages and automate the process of storing the averages in the text file, I can do so with a simple Python script. Using built-in functions in Python that can send requests to files, and receive responses from files, I can allow my Python script to read the contents of the text file, calculate the weekly averages, and then write those weekly averages to the text file.

The above example of an API uses local software components stored on a singular computer. Although, usually when people refer to APIs, they're referring to web APIs. Web APIs allow for the transmission of information between separate software components on separate computers over a network of networks of computers (aka, the internet).

---

# How to Implement and Use APIs

I'm going to walk you through the full process from finding an API to implementing the API in code.

## Finding an API

In my example, let's say that I run a blog dedicated to cats, and I want to add a button on my blog that displays a random picture of a cat upon being clicked.

To start, I'm going to simply search "cat API" on Google.

The first result on Google is [The Cat API](https://thecatapi.com/). To find out the gist of this API and how to use it, I'm going to click on the [Documentation](https://developers.thecatapi.com/view-account/ylX4blBYT9FaoVd6OhvR?report=bOoHBz-8t) tab.

![screenshot of cat API website](https://cdn.hashnode.com/res/hashnode/image/upload/v1693016108889/71be5858-a16d-405c-8936-31d04cdd62a4.png align="center")

Every API should have documentation explaining the API, how to implement it, API methods, and terms of service.

In **The Cat API** documentation, I see that this API does involve sending images of cats as API responses. The next step is to review the terms of service.

## Reviewing the terms of service

In reviewing the terms of service for an API, there are 5 main factors you want to clarify:

<details data-node-type="hn-details-summary"><summary>Whether you need an API key to send API requests</summary><div data-type="detailsContent">API keys are sometimes required to be able to authenticate and authorize an API request. This is to prevent malicious uses of an API, protect sensitive information, and for the API developer to be able to monetize the API.</div></details><details data-node-type="hn-details-summary"><summary>Whether the API communicates over HTTPS</summary><div data-type="detailsContent">Similar to casual browsing on the internet, it's strongly advised that you only communicate over HTTPS (especially if the content matter of the API request and/or response is sensitive information). In a nutshell, HTTP transfers data in the form of plain text, allowing the possibility for a hacker to intercept raw data. Whereas HTTPS properly encrypts the data, reducing the chances of a hacker stealing the data (of course nothing is impossible, and a hacker could theoretically decrypt the data, although this is highly unlikely).</div></details><details data-node-type="hn-details-summary"><summary>Whether the API allows cross-origin resource sharing (CORS)</summary><div data-type="detailsContent">CORS is a security protocol in web browsers that allows web servers to securely send an API response to a different domain than where the data is originally being served. Without CORS, hackers would be able to exploit stored session cookies on a client's web browser to make unauthorized requests to a domain that the client is visiting. If an API hasn't enabled CORS, you won't be able to receive API responses in client-side programs (such as JavaScript running in the browser). However, there is a workaround method of receiving the API response on a server-side program or a proxy server. I'll go into more detail on how to do this further in this article.</div></details><details data-node-type="hn-details-summary"><summary>Whether there's a limit to how many API requests that can be sent</summary><div data-type="detailsContent">To protect servers from being overloaded with requests, API developers enforce limits on how many API requests a client can send. This limit is usually represented as a rate of number of requests per some variable of time, such as hours, days, months, etc. Remember that servers require energy (hence money as well) to operate, so it's unethical for server hosts, other clients accessing the API, and the environment to overload servers with requests.</div></details><details data-node-type="hn-details-summary"><summary>Whether the API can be used for personal and/or business uses</summary><div data-type="detailsContent">Similar to the last point, server hosts don't want their servers to be abused by API requests. Typically, APIs that are meant for hobby projects will prohibit usage of the API in business applications. For APIs that could be used for both personal and business applications, API developers will typically have a free version for personal use and a paid version for businesses that expect to make a lot of API requests.</div></details>

After reviewing the documentation for **The Cat API**, here's what I've gathered:

* **An API key is not required** if I request no more than 10 images per API request. Although, obtaining an API key is free and allows me to receive up to 100 images per API request, and allows me 10,000 API requests per month.
    
* API requests and responses **are sent over HTTPS.**
    
* **CORS is not enabled** for this API.
    
* I can make **10,000 requests per month** in the free plan, 100,000 requests per month for $10/month, and unlimited requests per month in their "enterprise" plan which is volume-based pricing.
    
* If you're using the free plan, they **require you to only implement their API in non-monetized applications**. However, if you charge users to use an application that involves the implementation of **The Cat API**, then you must select at least the paid plan of $10/month.
    

All in all, I feel safe using this API, and my intentions of using it don't violate their terms. Even though CORS is not enabled for this API, we can work around this by using a proxy server.

## Make an API call

The next step is to read the API documentation to obtain the URL that you send a request to, and the parameters that you can include in the request.

For The Cat API, I didn't sign up for an API key, so I'm going to use the URL that sends a request for 1 random image of a cat.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693038044068/4915d177-2edf-47c0-85a6-9e8db5dece08.png align="center")

Notice how the URL for an API request looks very similar to a URL for a webpage that displays HTML. The main difference is that a URL for an API request has "api" instead of "www". This tells the server to serve an API response in the form of a data file (usually a JSON file format) as opposed to serving a webpage that displays HTML.

Also, take note of how parameters are added to an API URL to specify a request. For **The Cat API**, the base URL to make a request is https://api.thecatapi.com/v1/images/search. This request will return one random image of a cat, but we can modify the request by adding parameters to the URL. For example, there's a parameter "limit" that we can set to specify how many images we want in that request, "breed\_ids" that we can set to specify the breed of the cat(s) in the images, etc. Depending on the API, some parameters are required to define, but there's usually a plethora of parameters that are optional and you'll only know about them if you study the API documentation.

Finally, notice how you can even click the URL in the web browser, and a new tab opens.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693038184348/12489ba7-82f7-4c61-9ff7-e67869f6af05.png align="center")

This raw data is the API response formatted as JSON. There are 4 key-value pairs in the response: id (the API documentation tells us that every image has an id), url (this is the path to the image file stored on a content delivery network (CDN)), width (width of the image in pixels), and height (height of the image in pixels).

It's important to view how an API response is formatted before implementing it so that you know the names of the keys that you want to work with. In this example, we're only going to be using the url key.

## Implement the API into the JavaScript program

Finally, we're at the stage of coding. I've embedded the exact HTML and JavaScript code that I used in this example below.

There's one extra step we'll have to do to use this API though. Since this API doesn't have CORS enabled, we're simply going to use a proxy server. In this example, we'll use a demo reverse proxy called [CORS Anywhere](https://cors-anywhere.herokuapp.com/corsdemo). CORS Anywhere is an open-source project on GitHub (you can find the repository [here](https://github.com/Rob--W/cors-anywhere)). Essentially, it's a proxy server that adds CORS headers to the API request. To use it, click on the hyperlink I added above, and request temporary access to the proxy server.

When making the API call in JavaScript, all you have to do is prefix the API request URL with "https://cors-anywhere.herokuapp.com/".

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693040300248/d04e2392-946d-4ace-95bd-05a26c117f3a.png align="left")

Time to start coding. First, I'm going to make a basic HTML document with a `button` element that will have a click event defined in the JavaScript program. I'll also add a `div` element that will contain the image of the cat. Finally, make sure to include your JavaScript file in the HTML `body`.

```markdown
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>

    <button id = 'img_generator'>Click for image of a cat!</button>

    <div id = 'img_container'>

    </div>

<script src = 'cat_api_call.js'></script>
</body>
</html>
```

Next, I'm going to make the API call in the JavaScript program (don't forget to prefix the API URL path with the CORS Anywhere URL), declare the image of the cat as a variable, and append the image to the HTML document using an event listener for the button.

```javascript
// Define the url that we'll make the API call to (prefix with proxy server url)

const api_url = `https://cors-anywhere.herokuapp.com/https://api.thecatapi.com/v1/images/search`;

// Define relevant HTML elements

const img_generator = document.getElementById('img_generator');

const img_container = document.getElementById('img_container');

img_generator.addEventListener('click', getCat)

// Write an async function to call API

async function getCat() {
    
    // Wait for successful API call

    let response = await fetch(api_url);

    // Format JSON response to a JavaScript object

    let data = await response.json();

    // Define path to image by entering request body (data[0]) and retreiving value for the url key

    cat_img_url = data[0].url;

    // Add image to HTML document

    const img = document.createElement('img');
    img.src = `${cat_img_url}`;

    img_container.appendChild(img)
}
```

## Test to see if everything works

Here is my beautifully designed webpage that allows users to click a button to get a picture of a cat.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693040852584/645c6a75-7b69-49fb-a870-d3b397ec1c78.png align="center")

And ta-da! It works!

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1693040972150/a4ec4e76-de70-4a0e-aadb-3d46d4babd47.png align="center")

---

# Conclusion

I hope that this post helped clarify the concept of APIs, and also provided you with enough knowledge to start using APIs in your software.

Please comment down below if you have any lingering questions or suggestions for an article topic that I should cover in the future.

Also, please make sure to follow my newsletter to stay up to date on when I post new articles.