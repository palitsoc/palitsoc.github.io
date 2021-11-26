---
title: Frontend Loading Optimization
subtitle: "Application Performance Optimization : Frontend Loading"
slideshow_title: "Application Performance Optimization : Frontend Loading"
author: Ameen Alqattow
author_title: Development Tech Lead @ Innotech
description: "Application Performance Optimization : Frontend Loading by Ameen Alqattow"
layout: slideshow
date: 2021-11-27
published: true
image: /assets/img/logo.png
---

<section>
    <h1>Why is page loading experience important</h1>
</section>
<section>
    <ul>
        <li>Increase in Website Traffic</li>
        <li>Higher Customer Satisfaction</li>
        <li>Better SEO</li>
    </ul>
</section>
<section>
    <h1>How do we measure page loading experience</h1>
</section>
<section>
    <h2>Metrics Definition</h2>
    <ul>
        <li>There are 3 Main metrics for Page Loading</li>
        <li>FCP : First Contentful Paint, which is the time in seconds until we see anything of significance on the page</li>
        <li>LCP : Largest Contentful Paint, which is the time in seconds until the largest element/content on the page has finished rendering</li>
        <li>TTI: Time To Interactive, which is the time ins econds until the user can interact with page elements(forms, buttons,etc)</li>
    </ul>
</section>
<section>
    <h2>Tool Introduction</h2>
    <ul>
        <li>We use 2 Main tools to evaluate page performance</li>
        <li>Page Speed Insights by Google</li>
        <li>Web Page Test by webpagetest.org</li>
    </ul>
</section>
<section>
    <h3>Page Speed Insights</h3>
    <ul>
        <li>General tool</li>
        <li>Not Very Detailed</li>
        <li>Gives us a good evaluation of the user point of view, and reccomendations, but does not let us access raw data</li>
        <li>Gives Results for both Mobile and Desktop</li>
    </ul>
</section>
<section>
    <h3>Page Speed Insights</h3>
    <img data-src="/assets/slideshows/2021-11-27-ameen-alqattow-frontend-optimization/pagespeed-insights.png">
</section>
<section>
    <h3>WebPage Test</h3>
    <ul>
        <li>More Specialized Tool</li>
        <li>Very Detailed, includes request patterns, security scores, server checking, headers, screenshots, video recordings, etc</li>
        <li>Gives us a good technical evaluation, and helpds us investigate</li>
        <li>Automateable API for Continuous Testing</li>
        <li>Needs to Be configured for each run; very flexible</li>
    </ul>
</section>
<section>
    <h3>WebPage Test</h3>
    <img data-src="/assets/slideshows/2021-11-27-ameen-alqattow-frontend-optimization/webpagetest.png">
</section>
<section>
    <h1>Common Tricks to improve page loading experience</h1>
</section>
<section>
    <h2>Deferred Resources</h2>
    <ul>
        <li>Deferred Resources are Resources That are downloaded in the background and then processed after HTML is Processed</li>
        <li>This means that the page will render, then these resources will be parsed and rendered</li>
        <li>This helps us by making non-essential parts of our page show up later</li>
    </ul>
</section>
<section>
    <h3>Deferred JS</h3>
    <ul>
        <li>Deferred JS is usually used for non-critical 3rd party libraries</li>
        <li>It is also used for JS that is not used directly when the page is loaded</li>
        <li>Easily added by using "defer" tags on script elements</li>
    </ul>
    <pre><code><script type="text/template">
        <script src="my/script/source" defer></script>
    </script></code></pre>
</section>
<section>
    <h3>Deferred CSS</h3>
    <ul>
        <li>Deferred CSS is usually used for styles that do not affect the initial page render</li>
        <li>It is rarer to use, as most CSS styles are distribured together, but can have a high impact on page load</li>
        <li>Usually combined with Over the Head CSS for maximum effect</li>
    </ul>
    <pre><code><script type="text/template">
    <link rel="preload" href="/path/to/styles.css"
    as="style" onload="this.onload=null;this.rel='stylesheet'">
    </script></code></pre>
</section>
<section>
    <h2>Over the Head CSS</h2>
    <ul>
        <li>Over the Head CSS is an optimization Technique where critical styles are sent as block styles in HTML</li>
        <li>This is especially useful when combined with Deferred CSS, or end of Body CSS</li>
        <li>Usually used to maintain the skeleton structure while the page loads</li>
    </ul>
</section>
<section>
    <h2>Over the Head CSS</h2>
    <pre><code><script type="text/template">
        <head>
        <!-- Metadata, Scripts, etc-->
        <style type="text/css">
          /* Critical Styles Here */
        </style>
        <!-- Non Critical Styles Here -->
        <link rel="stylesheet" href="/path/to/styles.css">
        </head>
    </script></code></pre>
</section>
<section>
    <h2>Async Resources</h2>
    <ul>
        <li>Async Resources are resources that are downloaded in the background, then processed once the download is completed</li>
        <li>This means that they stop HTML rendering while they are being loaded</li>
        <li>This is useful for something which is not needed for structure, but also needed for content</li>
    </ul>
</section>
<section>
    <h3>Async JS</h3>
    <ul>
        <li>Async JS are JS files that are downloaded asynchronously and processed</li>
        <li>Useful for 3rd party integrations, trackers, etc</li>
        <li>But unlike deferred JS, will block the HTML render while processed</li>
    </ul>
    <pre><code><script type="text/template">
    <script src="my/script/source" async></script>
    </script></code></pre>
</section>
<section>
    <h3>Lazy Loaded Media</h3>
    <ul>
        <li>Media, Such as Video, Images, etc, can be loaded asynchronously as well</li>
        <li>This is called Lazy Loading</li>
        <li>As media may make up the bulk of a page's content, this is very helpful in getting the structure of the page up and making it feel faster</li>
    </ul>
    <pre><code><script type="text/template">
    <!-- Add loading="lazy" to image -->
    <img src="my/image/source/image.png" loading="lazy">
    <!-- Add preload="none" to videos -->
    <video controls preload="none" poster="placeholder.jpg">
    <!-- Video Sources -->
    </video>
    </script></code></pre>
</section>
<section>
    <h2>CDN</h2>
    <ul>
        <li>CDN means Content Distribution Network</li>
        <li>It is a distributed set of servers that serve your static content</li>
        <li>Many providers, such as AWS, Cloudflare, Akamai</li>
        <li>The main goal is to serve content as close as possible to the client is</li>
        <li>This reduces network latency, which improves load times</li>
        <li>Reduces load on our servers, meaning less response delay, improving load times</li>
    </ul>
</section>
<section>
    <h2>Caching</h2>
    <ul>
        <li>Caching is keeping our content saved on the client's device for a period of time(set by us)</li>
        <li>This means there is less network operations going on</li>
        <li>Which in turn, means less IO, and no latency</li>
        <li>Resulting in instant loading of some resources</li>
    </ul>
</section>
<section>
    <h3>Header Caching</h3>
    <ul>
        <li>The First way to do caching is using response headers</li>
        <li>We use the
            <code>Cache-Control</code>
            HTTP header for this</li>
        <li>This is great for setting cache policies for the entire server</li>
        <li>Not so great when fine tuning cache policies</li>
        <li>Also not dynamic - can be configured either for all clients or none</li>
    </ul>
</section>
<section>
    <h3>Service Worker Caching</h3>
    <ul>
        <li>The Second way to do caching is using Service Workers</li>
        <li>These are a special kind of javascript code that allows us to manipulate the HTTP requests going out of the browser(among other things, such as notifications and background processing)</li>
        <li>These allow us to have very fine control over caching, storage, and policies</li>
        <li>Are client side, so can be tailored to suit the environment</li>
    </ul>
</section>

<section>
    <h2>Response Compression</h2>
    <ul>
        <li>HTTP Responses are either text or binary data</li>
        <li>These can be compressed to save network bandwidth</li>
        <li>As a general rule, the less network bandwidth used, the faster the page loads</li>
    </ul>
</section>
<section>
    <h3>Text/Response Compression</h3>
    <ul>
        <li>Response Compression is performed by the web server</li>
        <li>This compression happens Just in Time, as the response is leaving the server</li>
        <li>May reduce up to 70% network bandwidth</li>
        <li>Handled transperantly by the browser and server</li>
        <li>Can also be used to compress JSON, file downloads, etc</li>
    </ul>
</section>
<section>
    <h3>Media Compression</h3>
    <ul>
        <li>Media compression is using media formats that come pre-compressed</li>
        <li>An Example of this is JPEG and WebM</li>
        <li>This is done when these resources are created/exported, and not by the web server</li>
        <li>Very helpful in content-heavy sites</li>
    </ul>
</section>

<section>
    <h1>Optimizing SPAs</h1>
</section>
<section>
    <h2>Tree Shaking</h2>
    <ul>
    <li>Tree Shaking is the name of a common JS technique to remove dead code</li>
    <li>Its usually done by javascript bundlers, and relies on <code>import</code> and <code>export</code> statements</li>
    <li>Each Bundler does it a little different</li>
    <li>But the end result is the same : smaller JS, leading to faster loading and render times</li>
    </ul>
</section>
<section>
    <h2>Code Splitting</h2>
    <ul>
    <li>Code splitting is a technique where our application gets divided into multiple files</li>
    <li>This is done, once again, by javascript bundlers</li>
    <li>The main premise is to split parts of the code that are not relevant and loading them seperately</li>
    <li>Another use is to only load common/shared code once</li>
    <li>Once again, the result is the same, smaller JS files in the page, leading to faster loading and rendering, at the cost of complexity in coding/bundling</li>
    </ul> 
</section>
<section>
    <h2>Lazy Loading</h2>
    <ul>
        <li>Lazy loading is a technique where our applications components get loaded only as they are needed</li>
        <li>This comes at a cost of more complexity in the front end, and slower interaction when page components need to be loaded</li>
        <li>Each framework implements this differently, but the permise is the same : load only what you need at startup, and then load the components you need as you go</li>
        <li>This means we only load the bare minimum on the initial load, making it very fast</li>
    </ul>
</section>
<section>
    <h2>Dependency Un/Bundling</h2>
    <ul>
        <li>The Last technique is dependency bundling and unbundling</li>
        <li>We can instruct our javascript bundler on how to work with our dependencies, and how to distribute them</li>
        <li>By using dependency un/bundling correctly, in tandem with agressive caching policies and a CDN, its possible to isolate our own code from our libraries</li>
        <li>This means that only our code - that we change - is loaded, while our library code/imported code stays cached, leading to faster load times</li>
    </ul>
</section>
