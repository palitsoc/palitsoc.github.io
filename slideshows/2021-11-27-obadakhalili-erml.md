---
title: ERML
subtitle: Understanding ERML
slideshow_title: Understanding ERML
author: Obada Khalili
author_title: "Software Engineer @ Foothill Solutions <br/> AI Student @ An-Najah National University"
description: Understanding the ERML organization's vision by Obada Khalili
layout: slideshow
date: 2021-11-27
published: true
image: /assets/img/logo.png
---

<section>
    <section>
        <h2>About the talk</h2>
        <ul>
            <li>We will be talking about a project of mine named ERML</li>
            <li>ERML is an organization that namespaces an array of tools targeted towards the SQL community</li>
        </ul>
    </section>
    <section>
        <h3>Quick refresher on ERD and RM</h3>
        <div class="r-stack">
            <img src="/assets/slideshows/2021-11-27-obadakhalili-erml/example_ERD.png" width="500" height="300">
            <img class="fragment" src="/assets/slideshows/2021-11-27-obadakhalili-erml/example_RM.png" width="300" height="450">
        </div>
    </section>
    <section>
        ERML tries to fulfill a vision where you can visualize your database's ERD and RM, and generate SQL schema code, all from a single source
        <img class="fragment" src="/assets/slideshows/2021-11-27-obadakhalili-erml/ERML_vision.png">
    </section>
    <section>
        To meet this vision, it requires three primary components, and I will be covering them in this talk
    </section>
</section>
<section>
    <section>
        <h2>ERML - The Language</h2>
        <p>
            ERML (Entity-Relationship Markup Language) is a language standard defined by me that aims to provide a complete solution to represent any ERD requirement, and to do that intuitively
        </p>
    </section>
    <section>
        <div style="display: flex; align-items: center;">
            <div style="flex: 1 1 0%;">
                <img src="/assets/slideshows/2021-11-27-obadakhalili-erml/simple_ERD.png">
            </div>
            <div class="fragment" style="flex: 1 1 0%;">
                <pre>
                <code data-trim data-line-numbers>
                    <script type="text/template">
                        ENTITY User {
                            PRIMARY "ID",
                            SIMPLE "DoB",
                            DERIVED "Age",
                            COMPOSITE "fullname" {
                                SIMPLE "firstname",
                                SIMPLE "lastname"
                            }
                        }
                    </script>
                </code>
                </pre>
            </div>
        </div>
    </section>
    <section>
        <div style="display: flex; align-items: center;">
            <div style="flex: 1 1 0%;">
                <img src="/assets/slideshows/2021-11-27-obadakhalili-erml/complex_ERD.png">
            </div>
            <div style="flex: 1 1 0%;">
                <pre>
                    <code data-trim data-line-numbers>
                        <script type="text/template">
                            ENTITY A {
                                SIMPLE "attr"
                            }

                            WEAK ENTITY B OWNER A {
                                SIMPLE "attr"
                            }

                            IDEN REL a_b  {
                                A <TOTAL, 1>,
                                B <PARTIAL, 1>,
                            }

                            ENTITY C {
                                SIMPLE "attr"
                            }

                            ENTITY D {
                                SIMPLE "attr",
                            }

                            REL c_d_b {
                                C <PARTIAL, 1>,
                                D <PARTIAL, 1>,
                                B <PARTIAL, 1>,
                                ATTRIBUTES {
                                    SIMPLE "attr"
                                }
                            }
                        </script>
                    </code>
                </pre>
            </div>
        </div>
    </section>
    <section>
        <a href="https://codesandbox.io/s/erml-talk-vp92e?file=/src/index.js" target="_blank">@erml/parser</a>
        is an open-source parser implementation of ERML standards
    </section>

</section>
<section>
    <h2>ERML - The Visualizer</h2>
    <ul>
        <li>An online ERD visualization tool that converts ERML code into SVG drawings</li>
        <li>
            <a href="http://erml-visualizer.netlify.app/" target="_blank">Quick tour</a>
        </li>
        <li class="fragment">With that, we achieve the first piece of the vision; The ERD Visualizer</li>
    </ul>
</section>
<section>
    <section>
        <h3>ERML - The DBML Compiler</h3>
        <ul>
            <li>DBML (Database Markup Language) is another language standard, set by Holistics, and it's designed to define and document database schemas and structures (relational models)</li>
            <li>
                DBML has an online RM visualization tool;
                <a href="https://dbdiagram.io/d/619c7ced02cf5d186b6369c9" target="_blank">dbdiagram</a>
            </li>
        </ul>
    </section>
    <section>
        <ul>
            <li>DBML can be converted into SQL</li>
            <li>
                ERML can hook into the DBML organization by providing a compiler to DBML, which achieves the second and third parts of ERML's vision; RM Visualizer and SQL schema code generator
            </li>
        </ul>
    </section>
    <section>
        <img src="/assets/slideshows/2021-11-27-obadakhalili-erml/ERML_vision_detailed.png" width="500">
    </section>
    <section>
        An ERML-to-DBML compiler doesn't exist (yet), which moves us to the next part
    </section>
</section>
<section>
    <h4>Growing the Palestinian's Open-source Culture</h4>
    <ul>
        <li>
            The computer science community of the Palestinian youth targets all of its efforts and talent into solving competitive programming problems. This is a good skill to have, but it's important to know when to stop, and start channeling this effort into more practical areas of computer science, like open-source
        </li>
        <li>Browse open-source projects that meet your requirements, choose one, and start solving its problems</li>
    </ul>
</section>
