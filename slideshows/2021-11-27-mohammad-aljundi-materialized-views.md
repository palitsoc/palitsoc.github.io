---
title: "Materialized Views"
subtitle: "Application Performance Optimization : Materialized Views"
slideshow_title: "Application Performance Optimization : Materialized Views"
author: Mohammad Al-Jundi
author_title: "Senior System Engineer @ Innotech"
description: "Materialized Views by Mohammad Al-Jundi"
layout: slideshow
date: 2021-11-27
published: true
image: /assets/img/logo.png
---

<section>
    <h2>Content</h2>
    <ul>
        <li>Caching & how it works.</li>
        <li>Caching Pros & Cons.</li>
        <li>Materialized Views.</li>
        <li>When we can use Materialized Views.</li>
        <li>Similarities & Differences.</li>
        <li>Materialized Views scenario and examples</li>
    </ul>
</section>
<section>
    <h2>Caching</h2>
    <ul>
        <li>Caching is a cost-effective solution that ensures fast response for most businesses.</li>
        <li>Caching is used to store two main types of data:
            <ul>
                <li>Frequently used data.</li>
                <li>Data need more computations and calculations</li>
            </ul>
        </li>
    </ul>
</section>
<section>
    <h2>How does caching work</h2>
    <ul>
        <li>The data in a cache is generally stored in fast access hardware such as RAM.</li>
        <li>A cache's primary purpose is to increase data retrieval performance by reducing the need to access the underlying slower storage layer.</li>
        <li>Caches can be applied throughout various layers of technology including Operating Systems, Networking layers including Content Delivery Networks (CDN) and DNS, web applications, and Databases.</li>
    </ul>
</section>
<section>
    <h2>Caching Pros & Cons</h2>
    <ul>
        <li>
            Pros:
            <ul>
                <li>Better speed.</li>
                <li>Reduce bottleneck.</li>
            </ul>
        </li>
        <li>
            Cons:
            <ul>
                <li>Small size.</li>
                <li>Expensive.</li>
                <li>Need to be recalculated.</li>
            </ul>
        </li>
    </ul>
</section>
<section>
    <h2>Materialized Views</h2>
    <ul>
        <li>A materialized view is a database object that contains the results of a query for later use.</li>
        <li>Materialized views can speed up expensive aggregation, and selection operations, especially those that run frequently and that run on large data sets</li>
    </ul>
</section>
<section>
    <h2>Deciding When to Create a Materialized View</h2>
    Materialized views are particularly useful when:
    <ul>
        <li>Query results contain a small number of rows and/or columns relative to the base table.
        </li>
        <li>Query results contain results that require significant processing, aggregates that take a long time to calculate.
        </li>
        <li>The view’s base table does not change frequently.
        </li>
    </ul>
</section>
<section>
    <h2>A Materialized View or a Regular View ?</h2>
    <p>Create a materialized view when all of the following are true:</p>
    <ul>
        <li>The Query results from the view don’t change often.</li>
        <li>The Results of the view are used often.</li>
        <li>The Query consumes a lot of resources.</li>
    </ul>
</section>
<section>
    <h2>A Materialized View or a Regular View ?</h2>
    <p>Create a regular view when any of the following are true:</p>
    <ul>
        <li>The Results of the view change often.</li>
        <li>The Results are not used often.</li>
        <li>The Query is not resource intensive so it is not costly to re-run it.</li>
    </ul>
</section>
<section>
    <h2>Similarities and Differences</h2>
    <img data-src="/assets/slideshows/2021-11-27-mohammad-aljundi-materialized-views/materialized_views_1.png">
</section>
<section>
    <h2>Some Use Cases</h2>
    <ul>
        <li>Real life scenario - Central pharmacy stock.</li>
        <li>Real life scenario - Aggergate Sales Statistics</li>
        <li>Real life scenario - multi-currency e-store items</li>
        <li>General scenario - Query Q contains an expensive sub-query S</li>
    </ul>
</section>
