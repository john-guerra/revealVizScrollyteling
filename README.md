# RevealVizScroll

A Reveal.js plugin for faking visualization scrollyteling. It lets you create incremental visualizations that stay on the screen between slides

Demo

## Usage

1) Create your typical reveal.js presentation, then include revealVizScroll.css and d3.v4.js
2) Add the *scroll* class to the sections you want to scroll, with two additional attributes *scrollable* with an id of the viz, and step with the id of the step.
3) Add the library revealVizScroll.js to Reveal.js dependencies, with a callback that creates your scrollables


## Basic Example

<html>
  <head>
    <link rel="stylesheet" href="css/reveal.css">
    <link rel="stylesheet" href="css/theme/white.css">
    <link rel="stylesheet" href="../revealVizScroll.css">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, minimal-ui">
  </head>
  <body>
    <div class="reveal">
      <div class="slides">
        <section>
          <section>
            <h1>No Scrolling</h1>
          </section>
          <section class="scroll" scrollable="demo" step="step 0" >
            <h2>Step 0 text</h2>
          </section>
          <section class="scroll" scrollable="demo" step="step 1" >
            <h2>Step 1 text</h2>
          </section>
          <section>
            <h2>No scrolling again</h2>
          </section>
        </section>
      </div>
    </div>
    <script src="js/head.min.js"></script>
    <script src="js/reveal.js"></script>
    <script src="js/d3.v4.min.js"></script>
    <script>
      Reveal.initialize({
        dependencies: [
          { src : "../revealVizScroll.js",
            async: false,
            callback: function () {
              revealVizScroll.makeScrollable("demo");
            }
          }
        ],

      });
    </script>
  </body>
</html>


