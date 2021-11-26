---
title: Frontend Loading Optimization
subtitle: "Application Performance Optimization : Frontend Loading"
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
</section>
<section>
    <h3>Deferred JS</h3>
</section>
<section>
    <h3>Deferred CSS</h3>
</section>
<section>
    <h2>Async Resources</h2>
</section>
<section>
    <h3>Async JS</h3>
</section>
<section>
    <h3>Async Media</h3>
</section>
<section>
    <h2>CDN</h2>
</section>
<section>
    <h2>Caching</h2>
</section>
<section>
    <h3>Headers</h3>
</section>
<section>
    <h3>Service Workers</h3>
</section>
<section>
    <h2>Over the Head CSS</h2>
</section>
<section>
    <h2>Response Compression</h2>
</section>
<section>
    <h3>Media Compression</h3>
</section>
<section>
    <h3>Text/Response Compression</h3>
</section>

<section>
    <h1>Optimizing SPAs</h1>
</section>
<section>
    <h2>Tree Shaking</h2>
</section>
<section>
    <h2>Code Splitting</h2>
</section>
<section>
    <h2>Lazy Loading</h2>
</section>
<section>
    <h2>Dependency Un/Bundling</h2>
</section>
