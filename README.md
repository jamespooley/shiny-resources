# Shiny Resources

Shiny is a great tool for the working data scientist that needs to quickly build an MVP data
product, but also wants to build a long-lasting "productized" application.

The following is a compendium of books, help documents, blog posts, etc. that I've found
helpful when building Shiny apps.

## Foundations

* [Mastering Shiny](https://mastering-shiny.org/) is a WIP book by R hero Hadley Wickham.
* The official R Studio Shiny [documentation](https://shiny.rstudio.com/articles)

### Reactive Programming

Joe Cheng's two presentations on reactivity from [Shiny DevCon 2016](https://resources.rstudio.com/shiny-developer-conference) are excellent
places to start to learn about the programming model used by Shiny.

* [Reactivity: Part 1](https://resources.rstudio.com/shiny-developer-conference/shinydevcon-reactivity-joecheng-part-1-1080p)
* [Reactivity: Part 2](https://resources.rstudio.com/shiny-developer-conference/shinydevcon-reactivity-joecheng-part-2-1080p)

### Profiling

* [Profiling a Shiny App](https://rstudio.github.io/profvis/examples.html#example-3---profiling-a-shiny-application) using [`profvis`](https://rstudio.github.io/profvis/index.html)

### Shiny Modules

* [The Shiny Module Design Pattern](https://drdoane.com/the-shiny-module-design-pattern/)

## Visualization

* [Interactive Web-Based Data Visualization with R, Plotly, and Shiny](https://plotly-r.com/)
* [R Graphics Cookbook (2nd Edition)](https://r-graphics.org/)


## Building Production-Grade Shiny Apps

* [Shiny in Production with AWS](https://business-science.github.io/shiny-production-with-aws-book/) is a free book that covers "[t]he enterprise-grade process for deploying, hosting, and maintaining Shiny web applications using AWS, Docker, and git."
* [Engineering Production-Grade Shiny Apps](https://thinkr-open.github.io/building-shiny-apps-workflow/) is another WIP book by the authors of the [`{golem}`](https://thinkr-open.github.io/golem/) package.
* Joe Cheng's [Shiny in Production: Principles, Practices, and Tools](https://resources.rstudio.com/rstudio-conf-2019/shiny-in-production-principles-practices-and-tools-joe-cheng) presentation at rstudio::conf 2019

## HTML, CSS, and JavaScript

Some of the more advanced usage of Shiny requires some familiarty with web development
languages.  Mozilla's [MDN web docs](https://developer.mozilla.org/en-US/) has excellent documentation on these technologies written "by developers, for developers."

* [HTML: Hypertext Markup Language](https://developer.mozilla.org/en-US/docs/Web/HTML)
* [CSS: Cascading Style Sheets](https://developer.mozilla.org/en-US/docs/Web/CSS)
* [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)


## Ideas and Inspiration

* R Studio's [Gallery](https://shiny.rstudio.com/gallery/) of Shiny applications is a
great source of ideas and inspiration when designing an app.


## General R Programming

Being fluent in R as a programming language (as opposed to a tool and interactive
environment for data analysis) goes a long way when building Shiny apps.

The [Functional Programming](https://adv-r.hadley.nz/fp.html) chapters in Hadley Wickham's
[Advanced R (2nd Edition)](https://adv-r.hadley.nz/) are good for learning an approach to
R programming that will help you write app code that follows the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principle.
