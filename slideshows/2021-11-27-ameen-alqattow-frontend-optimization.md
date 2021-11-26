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
        <li>There are 4 Main metrics for Page Loading</li>
        <li>TTFB : Time to First Byte, the time that it takes for a user's browser to receive the first byte of page content</li>
        <li>FCP : First Contentful Paint, which is the time in seconds until we see anything of significance on the page</li>
    </ul>
</section>
<section>
    <h2>Metrics Definition</h2>
    <ul>
        <li>LCP : Largest Contentful Paint, which is the time in seconds until the largest element/content on the page has finished rendering</li>
        <li>TTI: Time To Interactive, which is the time in seconds until the user can interact with page elements(forms, buttons,etc)</li>
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
    </ul>
    <pre><code><script type="text/template">
    <link rel="preload" href="/path/to/styles.css"
    as="style" onload="this.onload=null;this.rel='stylesheet'">
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
        <li>---
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
        <li>There are 4 Main metrics for Page Loading</li>
        <li>TTFB : Time to First Byte, the time that it takes for a user's browser to receive the first byte of page content</li>
        <li>FCP : First Contentful Paint, which is the time in seconds until we see anything of significance on the page</li>
    </ul>
</section>
<section>
    <h2>Metrics Definition</h2>
    <ul>
        <li>LCP : Largest Contentful Paint, which is the time in seconds until the largest element/content on the page has finished rendering</li>
        <li>TTI: Time To Interactive, which is the time in seconds until the user can interact with page elements(forms, buttons,etc)</li>
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
    </ul>
    <pre><code><script type="text/template">
    <link rel="preload" href="/path/to/styles.css"
    as="style" onload="this.onload=null;this.rel='stylesheet'">
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
        <li>Service workers essentially act as proxy servers that sit between web applications, the browser, and the network (when available).</li>
        <li>Run in a worker context: it therefore has no DOM access, and runs on a different thread to the main JavaScript that powers your app, so it is non-blocking.</li>
        <li>These give us ability to intercept and handle network requests</li>
        <li>Used with Offline First and PWA</li>
    </ul>
</section>
