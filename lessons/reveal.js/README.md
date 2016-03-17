# reveal.js

- **Author**: Chris Holden
- **Research field**: Geography
- **Lesson Topic**: HTML-based slide shows using `reveal.js`

## Requirements

This lesson is split into two parts to demonstrate two methods for creating presentations using `reveal.js`:
1. Write HTML to add content to your slides
2. Write a Markdown document and convert it to `reveal.js` HTML using `pandoc`

To follow along with the first method, you will need:
1. A copy of `reveal.js`
    * https://github.com/hakimel/reveal.js/releases
    * e.g., `git clone https://github.com/hakimel/reveal.js.git`
2. A text editor

To follow along with the second method, you will also need:
1. Pandoc
    * http://pandoc.org/installing.html

## Reveal.js: Writing HTML

The author of `reveal.js` has done a better job of documenting and explaining how to write a `reveal.js` in HTML better than I could ever do. Thus, we will follow along with the instructions linked below for this section of the lesson:

[hakimel's `reveal.js` lesson](https://github.com/hakimel/reveal.js#revealjs-)

This lesson includes an empty HTML slideshow file complete with all of the setup code for `reveal.js` to function that you can add slide and sub-slides to. This file is: `blank_revealjs_slideshow.html`.

## Reveal.js: Writing Markdown (with `pandoc`)

### Writing your slideshow

We will follow along with the [slide show documentation from `pandoc`](http://pandoc.org/README.html#producing-slide-shows-with-pandoc).

Content can be added easily by writing Markdown as you would anywhere else. Elements like tables, bulleted or numbered lists, URLs, or images can be added to your slides using Markdown syntax.

Pandoc interprets Markdown headings as instructions to construct a slide or a sub-slide. From [the tutorial](http://pandoc.org/README.html#producing-slide-shows-with-pandoc):

> The document is carved up into slides according to the following rules:
>
> * A horizontal rule always starts a new slide.
> * A header at the slide level always starts a new slide.
> * Headers below the slide level in the hierarchy create headers within a slide.
> * Headers above the slide level in the hierarchy create “title slides,” which just contain the section title and help to break the slide show into sections.
> * A title page is constructed automatically from the document’s title block, if present. (In the case of beamer, this can be disabled by commenting out some lines in the default template.)

Walk through the tutorial and add a few slides and sub-slides. For example:

    % Tutorial
    % Chris Holden
    % March 17, 2016

    # My Presentation

    # A new slide

    ## A sub-slide

    Content:

    * A list element
    * Another one

### Building

We will use `pandoc` to convert our example Markdown document into a HTML slideshow. First, locate the root directory of your copy of `reveal.js` relative to the location of your slides. We will need to point `pandoc` to the copy of `reveal.js` for the slides to work. The example below will assume that you cloned `reveal.js` into the same directory containing your Markdown slides.

With our copy of `reveal.js` located and a Markdown document to convert, we can use `pandoc` to convert our slides:

```
pandoc -t revealjs -V revealjs-url=reveal.js --standalone -i -o example_slideshow.html example_slideshow.md
```

You can open this output `example_slideshow.html` in your web-browser to see what the slideshow looks like.

Argument explanation:
* The `-t revealjs` option specifies the format
* The `-V` flag defines [a variable for the slideshow](http://pandoc.org/README.html#variables-for-slides)
* The `-V revealjs-url=[URL]` tells `pandoc` where to look for the `reveal.js` installation
* The `--standalone` option will embed the Javascript required for `revea.js` to run inside the output HTML document
* The `-i` makes list items appear incrementally (e.g., as `fragments`)
* The `-o example_slideshow.html` is how we specify the output filename (`example_slideshow.html`)
* Finally, we point `pandoc` to our Markdown document, `example_slideshow.md`

We can change the styling, slide transition method, and other customizations by passing [`reveal.js` configuration variables](https://github.com/hakimel/reveal.js#configuration) to `pandoc`:

``` bash
pandoc -t revealjs --standalone \
    -V revealjs-url=reveal.js \
    -V theme=beige \
    -V transition=zoom \
    -V slideNumber=true \
    -V center=true \
    -V hlss=zenburn \
    -o example_slideshow.html \
    example_slideshow.md
```

### Advanced

You can alter the styling of your slide shows by changing the `reveal.js` CSS files for the theme of your choosing.

For more advanced customization options, you may wish to alter the `reveal.js` template that `pandoc` uses. The default template for `reveal.js` is included with `pandoc`, but you can also [download a template from `jgm/pandoc-templates` repository](https://github.com/jgm/pandoc-templates).

To change the template used with `pandoc`, specify the filename of the template with the `--template=[FILENAME]` option to `pandoc`.
