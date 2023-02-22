---
title: "How to Set Up Tailwind CSS in a SPFx Project"
date: 2021-05-01T01:48:00-04:00
author: "Ari Gunawan"
githubname: AriGunawan
categories: ["Community post"]
images:
- images/State of CSS 2020 Survey.png
tags: ["SharePoint Framework (SPFx)"]
type: "regular"
---

In the [State of CSS 2020
survey](https://2020.stateofcss.com/en-US/technologies/css-frameworks/), the [Tailwind
CSS](https://tailwindcss.com/)
becomes the number 1 CSS Framework in terms of **Satisfaction** and
**Interest** in the last 2 years. It also gets the awards for **The Most
Adopted Technology**. It seems a lot of developers like this framework.
Based on my experience, this framework can help us rapidly build UI by
reducing complexity when styling the UI.

![](images/State of CSS 2020 Survey.png)

In this article, I will share my setup to use the Tailwind CSS in a
SharePoint Framework (SPFx) project.
**Prepare the SPFx Project**

Prepare your SPFx project. I use a newly generated [SPFx
project](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/build-a-hello-world-web-part) (v1.11) but you can also use your existing SPFx
project.
**Install Modules**

Install all modules needed by executing the command below:

``` {.graf .graf--pre}
npm install tailwindcss@1.9.6 postcss postcss-cli postcss-import @fullhuman/postcss-purgecss gulp-postcss autoprefixer@9.8.6 -D
```

**Initialize Tailwind CSS and PostCSS**

Initialize Tailwind CSS by executing the command below:

``` {.graf .graf--pre}
npx tailwind init -p --full
```

The command will create the *tailwind.config.js* in the project's base
directory. The file contains the configurations, such as colors, themes,
media queries, and so on.

The command will also create the *postcss.config.js* file. We need
PostCSS because we will use Tailwind CSS as a PostCSS plugin.
**Inject Tailwind CSS Components and Utilities**

We need to create a CSS file that will be used to import Tailwind CSS
styles.

-   Create an a*ssets* folder in the project's base directory
-   Create a *tailwind.css* file in the *assets* folder
-   Add the following lines of code to the file:

``` {.graf .graf--pre}
@import "tailwindcss/components";
@import "tailwindcss/utilities";
```

**Add Gulp Subtask for Processing Tailwind CSS**

We need to add the Tailwind CSS build process to our SPFx build process.

-   Open the *gulpfile.js*
-   Add the following lines of code to the file (before the
    *build.initialize(require('gulp'));* line):

``` {.graf .graf--pre}
const postcss = require("gulp-postcss");
const atimport = require("postcss-import");
const purgecss = require("@fullhuman/postcss-purgecss");
const tailwind = require("tailwindcss");
```

``` {.graf .graf--pre}
const tailwindcss = build.subTask(
   "tailwindcss",
   function (gulp, buildOptions, done) {
      gulp
         .src("assets/tailwind.css")
         .pipe(
            postcss([
               atimport(),
               tailwind("./tailwind.config.js"),
               ...(buildOptions.args.ship
                  ? [
                       purgecss({
                          content: ["src/**/*.tsx"],
                          defaultExtractor: (content) =>
                             content.match(/[\w-/:]+(?<!:)/g) || [],
                       }),
                    ]
                  : []),
            ])
         )
         .pipe(gulp.dest("assets/dist"));
      done();
   }
);
build.rig.addPreBuildTask(tailwindcss);
```

The code will add the *tailwindcss* subtask to the SPFx Gulp Build task.
It will also purge (remove unused styles) the Tailwind CSS for build
with *ship* flag:

``` {.graf .graf--pre}
gulp build --ship
```

or

``` {.graf .graf--pre}
gulp bundle --ship
```

**Add Reference to The Generated Tailwind CSS**

We need to add reference the generated Tailwind CSS by adding the import
code in your main *.ts* webpart file:

``` {.graf .graf--pre}
import '../../../assets/dist/tailwind.css';
```

**That's it!**

Now you can use Tailwind CSS utilities in your SPFx project.
**Result**

You might be familiar with the below result except it's not using styles
from the 74-lines scss/css file anymore.

![](images/REsult.png)
