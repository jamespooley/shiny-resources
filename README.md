# ✨ Shiny Resources

Shiny is a great tool for the working data scientist that needs to quickly build an MVP data
product, but also wants to build a long-lasting "productized" application.

The following is a (perpetually WIP) compendium of books, help documents, blog posts, etc. that I've found
helpful when building Shiny apps.

As always, R Studio has a very helpful Shiny [cheat sheet](https://shiny.rstudio.com/articles/cheatsheet.html).

### Table of Contents

* [Foundations](#foundations)
* [Advanced](#advanced)
* [Reactive Programming](#reactive)
* [Development Workflow](#workflow)
* [Data Visualization](#dataviz)
* [Shiny in Production](#production)
* [Docker and AWS](#docker)
* [HTML, CSS, and JavaScript](#webtech)


<a name="foundations"/>

### Foundations

* [Mastering Shiny](https://mastering-shiny.org/) is a WIP book by R hero Hadley Wickham.
* The official R Studio Shiny [documentation](https://shiny.rstudio.com/articles)
* [R Powered Web Applications with Shiny: A Tutorial and Cheat Sheet with 40 Example Apps](http://zevross.com/blog/2016/04/19/r-powered-web-applications-with-shiny-a-tutorial-and-cheat-sheet-with-40-example-apps/)
* [How to Build a Shiny App from Scratch](https://bookdown.org/hadrien/how_to_build_a_shiny_app_from_scratch/)


<a name="advanced"/>

### Advanced Shiny

* [Advanced Shiny: tips and Tricks for Improving Your Apps and Solving Common Problems](https://github.com/daattali/advanced-shiny)


<a name="reactive"/>

### Reactive Programming

* [Maintaining State with `reactiveValues()`](https://www.oreilly.com/learning-paths/learning-path-introduction/9781491987209/9781491959558-video245646)
* The **`observe()` vs. `observeEvent()`** section of the
[Common Application Caveats](https://engineering-shiny.org/optim-caveat.html) chapter of [Engineering Production-Grade Shiny Apps](https://engineering-shiny.org/) provides a lucid comparison of these functions

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


I found the following article to be especially clear at comparing
reactive expressions and observers:

* [`reactive`, `reactiveValue`, and `eventReactive`, `observe` and `observeEvent` in Shiny](https://shiny.programmingpedia.net/en/tutorial/10787/reactive-reactivevalue-and-eventreactive-observe-and-observeevent-in-shiny)

[The Introduction to Reactive Programming You've Been Missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) sounds relevant, but have not read it ... yet.


<a name="workflow"/>

### Development Workflow

* The [Workflow](https://mastering-shiny.org/action-workflow.html) chapter in Hadley Wickham's
Mastering Shiny has a lot of good advice. In particular, the part of [Shiny apps in background jobs](https://github.com/sol-eng/background-jobs/tree/master/shiny-job) when using R Studio.
* A simple change that works for me is [Dean Attali](https://deanattali.com/shiny/)'s tip
to put `session$onSessionEnded(stopApp)` in your `server` function, which lets you ["[a]utomatically stop a Shiny app when closing the browser tab."](https://github.com/daattali/advanced-shiny/tree/master/auto-kill-app)
* MarkeD's answer to on the [Best Practices: Shiny Development](https://community.rstudio.com/t/best-practices-shiny-development/1694/3) on the R Studio community discussion board has good suggestions.
* [A Minimal Reprex for a Shiny App](https://www.youtube.com/watch?v=9w8ANOAlWy4)

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
* [Improving Scalability with Async Programming](https://shiny.rstudio.com/articles/async.html)
* [Using Promises with Shiny](https://rstudio.github.io/promises/articles/shiny.html)

<a name="dataviz"/>

### Visualization

* [Interactive Web-Based Data Visualization with R, Plotly, and Shiny](https://plotly-r.com/)
* [R Graphics Cookbook (2nd Edition)](https://r-graphics.org/)


<a name="production"/>

### Shiny in Production

> What is "production"? Software environments that are used and
> relied on by real users, with real consequences if things go wrong.
>
>  --- [Joe Cheng](https://speakerdeck.com/jcheng5/shiny-in-production?slide=6)

* [Shiny in Production with AWS](https://business-science.github.io/shiny-production-with-aws-book/) is a free book that covers "[t]he enterprise-grade process for deploying, hosting, and maintaining Shiny web applications using AWS, Docker, and git."
* [Engineering Production-Grade Shiny Apps](https://thinkr-open.github.io/building-shiny-apps-workflow/) is another WIP book by the authors of the [`{golem}`](https://thinkr-open.github.io/golem/) package.
* Joe Cheng's [Shiny in Production: Principles, Practices, and Tools](https://resources.rstudio.com/rstudio-conf-2019/shiny-in-production-principles-practices-and-tools-joe-cheng) presentation at rstudio::conf 2019
* [Packaging Shiny Applications: A Deep Dive](https://www.mango-solutions.com/packaging-shiny-applications-a-deep-dive/)
* [Building a Shiny App as a Package](https://rtask.thinkr.fr/building-a-shiny-app-as-a-package/)
* [`shinyApp()`, `runApp()`, `shinyAppDir()`, and a Fourth Option](https://rtask.thinkr.fr/shinyapp-runapp-shinyappdir-difference/)
* [Dockerized Shiny App Development](http://tamaszilagyi.com/blog/2018/2018-01-16-shiny_docker/)
* [Demonstration of the `{golem}` Package](https://www.youtube.com/watch?v=3-p9XLvoJV0) is a nice quickstart webinar on using the `{golem}` package.
* [Bring Your Favorite Fonts to Reports Running in Docker](https://medium.com/@vladimirsalin/bring-your-favourite-fonts-to-reports-running-in-docker-9fc2d24e2b03)
* [R Shiny in Production](https://medium.com/inlocotech/r-shiny-in-production-e2fb6a577fe0)
* [Debugging Shiny Applications](https://shiny.rstudio.com/articles/debugging.html)
* [Shiny Server Administrator's Guide](https://support.rstudio.com/hc/en-us/articles/214771447-Shiny-Server-Administrator-s-Guide)
* [What Does "Disconnected from Server" Mean in shinyapps.io?](https://support.rstudio.com/hc/en-us/articles/220339568-What-does-Disconnected-from-Server-mean-in-shinyapps-io-)

#### Shiny Proxy

> ShinyProxy is your favourite way to deploy Shiny apps in an
> enterprise context. It has built-in functionality for LDAP
> authentication and authorization, makes securing Shiny traffic
> (over TLS) a breeze and has no limits on concurrent usage of a
> Shiny app. 

* [Shiny in Production with ShinyProxy, Docker, and Debian](https://rtask.thinkr.fr/shiny-application-in-production-with-shinyproxy-docker-and-debian/)
* [ShinyProxy](https://www.shinyproxy.io/) official docs

The team at Appsilon has a five-part series of posts on
"Super Solutions for Shiny Architecture" covering:

1. [Using Session Data](https://appsilon.com/super-solutions-for-shiny-architecture-1-of-5-using-session-data/)
2. [JavaScript Is Your Friend](https://appsilon.com/super-solutions-for-shiny-architecture-2-javascript-is-your-friend/)
3. [Softcoding Constants in the App](https://appsilon.com/super-solutions-for-shiny-architecture-3-5-softcoding-constants-in-the-app/)
4. [Using R6 Classes](https://appsilon.com/super-solutions-for-shiny-apps-using-r6-classes/)
5. [Automated Tests](https://appsilon.com/super-solutions-for-shiny-architecture-5-automated-tests/)

In terms of getting R to play nice with Airflow, the following provide some
guidance:

* [Executing an R Script from Airflow](https://community.rstudio.com/t/executing-an-r-script-from-airflow/18421)
* [Running R Scripts in Airflow?](https://stackoverflow.com/questions/45825146/running-r-scripts-in-airflow)
* [\[AIRFLOW-2193\] Add ROperator for using R #3115](https://github.com/apache/airflow/pull/3115) is a (closed) pull request about this
* [Deploying R Models in Production with Apache Airflow and AWS Batch](https://medium.com/bbc-data-science/deploying-r-models-in-production-with-apache-airflow-and-aws-batch-9182b0c8ed83), even though this doesn't mention Shiny


#### Security

Two posts on the [Auth0](https://auth0.com) blog cover addtion authentication to Shiny:

* [Adding Authentication to Shiny Open Source Edition](https://auth0.com/blog/adding-authentication-to-shiny-open-source-edition/)
* [Adding Authentication to Shiny Server in 4 Simple Steps](https://auth0.com/blog/adding-authentication-to-shiny-server/)

In terms of password-protection for Shiny apps:

* The [`shinymanager`](https://datastorm-open.github.io/shinymanager/) package provides
"simple and secure authentication for single Shiny applications," with the encrypted credentials 
stored in a SQLite database
* [Password Protect Shiny Apps](https://www.r-bloggers.com/password-protect-shiny-apps/) covers,
as one would expect, how to add password protection to your apps.


### Security

* [Securing Shiny Apps](https://globalparametrics.github.io/SecuringShiny/) provides "[a] summary of free/open source ways of securing Shiny."


### Testing

* [Using `shinytest` with R Packages](https://rstudio.github.io/shinytest/articles/package.html)
* [Testing in Depth](https://rstudio.github.io/shinytest/articles/in-depth.html)
* [Using `shinytest` with Continuous Integration](https://rstudio.github.io/shinytest/articles/ci.html)
* [Testing Shiny Apps](https://cran.r-project.org/web/packages/RSelenium/vignettes/shinytesting.html) goes into "how one might approach 'testing' a Shiny app" using [RSelenium](https://github.com/ropensci/RSelenium).
* [Developing Robust Shiny Apps with Regression Testing](https://resources.rstudio.com/rstudio-conf-2018/shiny-developing-robust-shiny-apps-with-regression-testing-winston-chang)


<a name="docker"/>

## Docker and AWS

If you need a quickstart guide to Docker, [R Docker Tutorial](https://ropenscilabs.github.io/r-docker-tutorial/) is a (non-Shiny-specific) tutorial on Docker for R users that may be helpful.

* [R Shiny on AWS Using Docker: Part 1](https://www.bryanwhiting.com/2019/02/rshiny-on-docker-part1/)
* [R Shiny on AWS Using Docker: Part 2](https://www.bryanwhiting.com/2019/02/rshiny-on-docker-part2/)

DataCamp's [EC2 Tutorial for Beginners](https://www.datacamp.com/community/tutorials/aws-ec2-beginner-tutorial) is a good quickstart if you need some basic training with that service.

* [How to User Rocker (R + Docker) to Containerize an Application Consist of Both R and Shiny Python Libraries](https://towardsdatascience.com/rocker-r-docker-to-containerize-an-application-consist-of-both-r-shiny-and-python-libraries-821c8c54bcee)
* [How to Deploy Shiny Server with AWS](https://www.youtube.com/watch?v=0h9VOQZX6QM)
* [Deploying a Shiny App with Shiny Server on an AWS EC2 Instance](https://abndistro.com/post/2019/07/06/deploying-a-shiny-app-with-shiny-server-on-an-aws-ec2-instance/)


<a name="webtech"/>

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
* [Bang Bang: How to Program with `dplyr`](https://www.r-craft.org/r-news/bang-bang-how-to-program-with-dplyr/) has some stuff on Shiny.


## Dog's Breakfast

These are good but I haven't decided where to put these yet. Thus, the [terrible section name](https://www.merriam-webster.com/dictionary/dog%27s%20breakfast)...

* [The Subtleties of Shiny Reactive Programming: `lapply` and `for` Loops](https://chasemc.github.io/post/the-subtleties-of-shiny-reactive-programming-lapply-and-for-loops/)
* [Persistent Data Storage in Shiny Apps](https://shiny.rstudio.com/articles/persistent-data-storage.html)
* [Shiny Developer Series](https://shinydevseries.com/) is a series of webinars that are worth watching.
* [How can I insert an image into the navbar on a shiny navbarPage()?](https://stackoverflow.com/questions/24705431/how-can-i-insert-an-image-into-the-navbar-on-a-shiny-navbarpage) answer on Stack Overflow
* [In R Shiny, When Is an Error Really an Error?](https://towardsdatascience.com/in-r-shiny-when-is-an-error-really-an-error-702205ebb5d5)
* [Use `shinydashboard` in `shiny`](https://dreamrs.github.io/shinyWidgets/reference/useShinydashboard.html) shows how to use a [`valueBox()`](https://rstudio.github.io/shinydashboard/structure.html#valuebox) in a Shiny app (cf. a Shiny dashboard) via the `shinyWidgets::useshinydashboard()` function.
* [Using Cookie Based Authentication with Shiny](https://calligross.de/post/using-cookie-based-authentication-with-shiny/)
* If you need a WYSIWYG text editor in your app, check out [`shinyMCE`](https://github.com/mul118/shinyMCE).
* [`shinyAce`](https://github.com/trestletech/shinyAce) is another text editor option.
* [Long Running Tasks with Shiny: Challenges and Solutions](http://blog.fellstat.com/?p=407)
* [Shiny Database App (CRUD)](https://ipub.com/shiny-crud-app/)
* [Exploring `yonder` with Nathan Teetor](https://www.youtube.com/watch?v=TWqfik2INEQ)
* [Managing App Dependencies in Packages](https://irudnyts.github.io//managing-dependencies-in-packages/)
* [Styling Shiny Apps with Sass and Bootstrap 4](https://rstudio.com/resources/rstudioconf-2020/styling-shiny-apps-with-sass-and-bootstrap-4/)
* [Fetch API Results from the Browser and Send Them to Shiny](https://colinfay.me/api-from-client-shiny/)
* [`chuck`: A Training Tool for Deploying Shiny Apps](https://colinfay.me/chuck-deployment-shiny-docker-kubernetes/)
* [Client-Side Interactivity: Do More with Crosstalk](https://themockup.blog/posts/2020-05-29-client-side-interactivity-do-more-with-crosstalk/)
* [Creating Interactive Dashboards in R Shiny Using Python Scripts as the Backend](https://towardsdatascience.com/creating-interactive-dashboards-in-r-shiny-using-python-scripts-as-the-backend-aed40e18fb3f)
* [Reticulated Shiny](https://rviews.rstudio.com/2018/04/17/reticulated-shiny/)
* [Tutorial: Using Shiny + Reticulate to Create Apps with R and Python 3](https://github.com/ranikay/shiny-reticulate-app)
* Keep an eye on [questions tagged `shiny`](https://stackoverflow.com/questions/tagged/shiny) on Stack Overflow
* [Dash with `golem`: First Contact](https://rtask.thinkr.fr/dash-with-golem-the-beginning/)
* [`reactable`: An Interactive Tables Guide](https://themockup.blog/posts/2020-05-13-reactable-tables-the-rest-of-the-owl/)
