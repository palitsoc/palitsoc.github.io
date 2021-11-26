---
title: "Elixir & OTP"
subtitle: "Elixir & OTP"
slideshow_title: "Elixir & OTP"
author: Ameer Alqam
author_title: "Software Engineer @  UserPilot"
description: "Elixir & OTP by Ameer Alqam"
layout: slideshow
date: 2021-11-27
published: true
image: /assets/img/logo.png
---

<section>
    <section>
        <h2>The BEAM platform</h2>
        <ul>
            <li>Erlang was a language invented by Joe Armstrong at Ericsson
                <ul>
                    <li>Designed specifically to address the problem of distributed systems</li>
                    <li>Uses the BEAM VM for it’s runtime and features</li>
                </ul>
            </li>
            <li>
                The BEAM has other programming languages taking advantage of it
                <ul>
                    <li>Elixir</li>
                    <li>Gleam</li>
                </ul>
            </li>
        </ul>
    </section>
    <section>
        <h1>It all starts with a process</h1>
    </section>
    <section>
        <h2>A process?</h2>
        <ul>
            <li>Not an OS process</li>
            <li>A very small piece of sequential code</li>
            <li>Elixir is functional in this context, but not pure</li>
        </ul>
        <img data-src="/assets/slideshows/2021-11-27-ameer-alqam-elixir/1.1_single_process.png">
    </section>
    <section>
        <h2>Starting a new process</h2>
        <pre><code><script type="text/template"> 	
        # Simplest way to start a process
        spawn fn -> do_some_other_thing() end
        </script></code></pre>
        <img data-src="/assets/slideshows/2021-11-27-ameer-alqam-elixir/1.2_two_processes.png">
    </section>
</section>
<section>
    <section>
        <h1>Super high-level overview</h1>
    </section>
    <section>
        <div class="r-stack">
            <img data-src="/assets/slideshows/2021-11-27-ameer-alqam-elixir/2.1_the_beam.png">
            <img class="fragment" data-src="/assets/slideshows/2021-11-27-ameer-alqam-elixir/2.2_the_beam.png">
            <img class="fragment" data-src="/assets/slideshows/2021-11-27-ameer-alqam-elixir/2.3_the_beam.png">
        </div>
    </section>
</section>
<section>
    <section>
        <h1>Message passing</h1>
    </section>
    <section>
        <img data-src="/assets/slideshows/2021-11-27-ameer-alqam-elixir/3.1_message_passing.png">
    </section>
</section>
<section>
    <section>
        <h1>Quick demo</h1>
    </section>
    <section>
        <iframe width="700" height="700" src="https://evening-river-84248.herokuapp.com/"></iframe>
    </section>
</section>
<section>
    <h2>Check them out</h2>
    <ul>
        <li>
        <a href="https://www.youtube.com/watch?v=JvBT4XBdoUE" traget="_blank">The soul of Erlang and Elixir, by Saśa Jurić.</a>
        </li>
        <li>
        <a href="https://www.youtube.com/watch?v=lxYFOM3UJzo" traget="_blank">Elixir, the Documentary, featuring José Valim.</a>
        </li>
    </ul>
</section>
