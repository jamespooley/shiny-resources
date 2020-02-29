# ✨ Shiny Resources

Shiny is a great tool for the working data scientist that needs to quickly build an MVP data
product, but also wants to build a long-lasting "productized" application.

The following is a compendium of books, help documents, blog posts, etc. that I've found
helpful when building Shiny apps.

As always, R Studio has a very helpful Shiny [cheat sheet](https://shiny.rstudio.com/articles/cheatsheet.html).

<!-- toc -->

### Foundations

* [Mastering Shiny](https://mastering-shiny.org/) is a WIP book by R hero Hadley Wickham.
* The official R Studio Shiny [documentation](https://shiny.rstudio.com/articles)
* [R Powered Web Applications with Shiny: A Tutorial and Cheat Sheet with 40 Example Apps](http://zevross.com/blog/2016/04/19/r-powered-web-applications-with-shiny-a-tutorial-and-cheat-sheet-with-40-example-apps/)

### Advanced Shiny

* [Advanced Shiny: tips and Tricks for Improving Your Apps and Solving Common Problems](https://github.com/daattali/advanced-shiny)


### Reactive Programming

Remember the [4 maxims](https://shiny.rstudio.com/articles/understanding-reactivity.html) of reactive programming in Shiny prepared
by Garret Grolemund:

1. R expressions update themselves, if you ask.
2. Nothing needs to happen instantly.
3. The app must do as little as possible.
4. Think carrier pigeons, not electricity.

Joe Cheng's two presentations on reactivity from [Shiny DevCon 2016](https://resources.rstudio.com/shiny-developer-conference) are excellent
places to start to learn about the programming model used by Shiny.

* [Reactivity: Part 1](https://resources.rstudio.com/shiny-developer-conference/shinydevcon-reactivity-joecheng-part-1-1080p)
* [Reactivity: Part 2](https://resources.rstudio.com/shiny-developer-conference/shinydevcon-reactivity-joecheng-part-2-1080p)


[The Introduction to Reactive Programming You've Been Missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) sounds relevant, but have not read it ... yet.

### Development Workflow

* The [Workflow](https://mastering-shiny.org/action-workflow.html) chapter in Hadley Wickham's
Mastering Shiny has a lot of good advice. In particular, the part of [Shiny apps in background jobs](https://github.com/sol-eng/background-jobs/tree/master/shiny-job) when using R Studio.
* A simple change that works for me is [Dean Attali](https://deanattali.com/shiny/)'s tip
to put `session$onSessionEnded(stopApp)` in your `server` function, which lets you ["[a]utomatically stop a Shiny app when closing the browser tab."](https://github.com/daattali/advanced-shiny/tree/master/auto-kill-app)
* MarkeD's answer to on the [Best Practices: Shiny Development](https://community.rstudio.com/t/best-practices-shiny-development/1694/3) on the R Studio community discussion board has good suggestions.

### DataTables

* [DT: An R Interface to the DataTables Library](https://rstudio.github.io/DT/)

### Profiling

* [Profiling a Shiny App](https://rstudio.github.io/profvis/examples.html#example-3---profiling-a-shiny-application) using [`profvis`](https://rstudio.github.io/profvis/index.html)

* Hadley's chapters on [Measuring Performance](https://adv-r.hadley.nz/perf-measure.html) and [Improving Performance](https://adv-r.hadley.nz/perf-improve.html) of R code in Advanced R will be helpful here.
* [Speed Up Shiny Coding with Data](https://roh.engineering/post/speeding-up-shiny-coding-with-data/)

### Shiny Modules

* [The Shiny Module Design Pattern](https://drdoane.com/the-shiny-module-design-pattern/)
* [Writing Big Apps: How to Use Shiny Modules](https://resources.rstudio.com/shiny-developer-conference/shinydevcon-modules-garrettgrolemund-1080p)
* [Effective Use of Shiny Modules in Application Development](https://resources.rstudio.com/rstudio-conf-2019/effective-use-of-shiny-modules-in-application-development)
* [Reproducible Shiny App Development with Modules](https://www.blog.cultureofinsight.com/2018/01/reproducible-shiny-app-development-with-modules/)
* [Communication between Modules and Its Whims](https://rtask.thinkr.fr/communication-between-modules-and-its-whims/)

### Asynchronous Programming

* [Async in R and Shiny](https://medium.com/@joe.cheng/async-programming-in-r-and-shiny-ebe8c5010790)
* [An Informal Intro to Async Shiny](https://medium.com/@joe.cheng/an-informal-intro-to-async-shiny-cbf01c85c4c5)

### Visualization

* [Interactive Web-Based Data Visualization with R, Plotly, and Shiny](https://plotly-r.com/)
* [R Graphics Cookbook (2nd Edition)](https://r-graphics.org/)


### Building Production-Grade Shiny Apps

> <sup>What is "production"? Software environments that are used and
relied on by real users, with real consequences if things go wrong.
([Joe Cheng](https://speakerdeck.com/jcheng5/shiny-in-production?slide=6))</sup>

* [Shiny in Production with AWS](https://business-science.github.io/shiny-production-with-aws-book/) is a free book that covers "[t]he enterprise-grade process for deploying, hosting, and maintaining Shiny web applications using AWS, Docker, and git."
* [Engineering Production-Grade Shiny Apps](https://thinkr-open.github.io/building-shiny-apps-workflow/) is another WIP book by the authors of the [`{golem}`](https://thinkr-open.github.io/golem/) package.
* Joe Cheng's [Shiny in Production: Principles, Practices, and Tools](https://resources.rstudio.com/rstudio-conf-2019/shiny-in-production-principles-practices-and-tools-joe-cheng) presentation at rstudio::conf 2019
* [Packaging Shiny Applications: A Deep Dive](https://www.mango-solutions.com/packaging-shiny-applications-a-deep-dive/)
* [Building a Shiny App as a Package](https://rtask.thinkr.fr/building-a-shiny-app-as-a-package/)
* [`shinyApp()`, `runApp()`, `shinyAppDir()`, and a Fourth Option](https://rtask.thinkr.fr/shinyapp-runapp-shinyappdir-difference/)
* [Dockerized Shiny App Development](http://tamaszilagyi.com/blog/2018/2018-01-16-shiny_docker/)


### Security

* [Securing Shiny Apps](https://globalparametrics.github.io/SecuringShiny/) provides "[a] summary of free/open source ways of securing Shiny."


### Testing

* [Using `shinytest` with R Packages](https://rstudio.github.io/shinytest/articles/package.html)
* [Testing in Depth](https://rstudio.github.io/shinytest/articles/in-depth.html)
* [Using `shinytest` with Continuous Integration](https://rstudio.github.io/shinytest/articles/ci.html)

## Docker and AWS

If you need a quickstart guide to Docker, [R Docker Tutorial](https://ropenscilabs.github.io/r-docker-tutorial/) is a (non-Shiny-specific) tutorial on Docker for R users that may be helpful.

* [R Shiny on AWS Using Docker: Part 1](https://www.bryanwhiting.com/2019/02/rshiny-on-docker-part1/)
* [R Shiny on AWS Using Docker: Part 2](https://www.bryanwhiting.com/2019/02/rshiny-on-docker-part2/)

DataCamp's [EC2 Tutorial for Beginners](https://www.datacamp.com/community/tutorials/aws-ec2-beginner-tutorial) is a good quickstart if you need some basic training with that service.

* [How to User Rocker (R + Docker) to Containerize an Application Consist of Both R and Shiny Python Libraries](https://towardsdatascience.com/rocker-r-docker-to-containerize-an-application-consist-of-both-r-shiny-and-python-libraries-821c8c54bcee)

## HTML, CSS, and JavaScript

Some familiarty with web development languages will come in handy, especially when utilizing [Advanced UI](https://mastering-shiny.org/advanced-ui.html) features and [`shinyjs`](https://github.com/daattali/shinyjs).

Mozilla's [MDN web docs](https://developer.mozilla.org/en-US/) has excellent documentation on these technologies written "by developers, for developers."

* [HTML: Hypertext Markup Language](https://developer.mozilla.org/en-US/docs/Web/HTML)
* [CSS: Cascading Style Sheets](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

[Introduction to Data Technologies](https://www.stat.auckland.ac.nz/~paul/ItDT/) also has a useful introduction to HTML and CSS.

Other resources worth a read:

* [7 Easy Steps to Custom Inputs in Shiny](https://mail-wolf.de/?p=4357)
* [Build Your Entire UI with HTML](https://shiny.rstudio.com/articles/html-ui.html) from the official R Studio Shiny documentation
* [HTML Templates](https://shiny.rstudio.com/articles/templates.html) from the official R Studio Shiny documentation
* [Web Fundamentals](https://developers.google.com/web/fundamentals), "Google's opinionated reference for building amazing web experiences"


## Shiny and R Markdown

* The [Shiny Documents](https://bookdown.org/yihui/rmarkdown/shiny-documents.html) chapter in[R Markdown: The Definitive Guide](https://bookdown.org/yihui/rmarkdown/)
is worth a read.
* [Generating Downloadable Reports](https://shiny.rstudio.com/articles/generating-reports.html) from the official R Studio Shiny documentation


## Application Layout Ideas and Inspiration

* [Application Layout Guide](https://shiny.rstudio.com/articles/layout-guide.html) from the official docs
* R Studio's [Gallery](https://shiny.rstudio.com/gallery/) of Shiny applications is a
great source of ideas and inspiration when designing an app.
* [Grid Style Sheets](https://rstudio.com/resources/videos/grid-style-sheets/) "are a radical approach to doing app-style layouts in a browser. It is a JavaScript library that replaces the browser’s built-in layout engine with one based on a constraint solving algorithm. The result is that some layouts that are incredibly tricky in CSS are completely natural to implement in GSS. This talk will demonstrate an experimental R library that makes it simple for any Shiny developer to take advantage of CSS. 12:56."
* [RinteRface](https://github.com/RinteRface), a "collection of outstanding APIs for R Shiny"


## General R Programming

Being fluent in R as a programming language (as opposed to a tool and interactive
environment for data analysis) goes a long way when building Shiny apps.

The [Functional Programming](https://adv-r.hadley.nz/fp.html) chapters in Hadley Wickham's
[Advanced R (2nd Edition)](https://adv-r.hadley.nz/) are good for learning an approach to
R programming that will help you write app code that follows the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principle.

* [Create a Dynamic Number of UI Elements in Shiny with `purrr`](https://tbradley1013.github.io/2018/08/10/create-a-dynamic-number-of-ui-elements-in-shiny-with-purrr/)
* [Generate Custom HTML per Row of a Data Frame with `pmap`](https://adamgruer.rbind.io/post/create-html-per-row-of-a-dataframe-with-pmap/)


## Dog's Breakfast

These are good but I haven't decided where to put these yet. Thus, the [terrible section name](https://www.merriam-webster.com/dictionary/dog%27s%20breakfast)...

* [Shiny Developer Series](https://shinydevseries.com/) is a series of webinars that are worth watching.
* [How can I insert an image into the navbar on a shiny navbarPage()?](https://stackoverflow.com/questions/24705431/how-can-i-insert-an-image-into-the-navbar-on-a-shiny-navbarpage) answer on Stack Overflow
* [In R Shiny, When Is an Error Really an Error?](https://towardsdatascience.com/in-r-shiny-when-is-an-error-really-an-error-702205ebb5d5)
* [Use `shinydashboard` in `shiny`](https://dreamrs.github.io/shinyWidgets/reference/useShinydashboard.html) shows how to use a [`valueBox()`](https://rstudio.github.io/shinydashboard/structure.html#valuebox) in a Shiny app (cf. a Shiny dashboard) via the `shinyWidgets::useshinydashboard()` function.
* [Using Cookie Based Authentication with Shiny](https://calligross.de/post/using-cookie-based-authentication-with-shiny/)
