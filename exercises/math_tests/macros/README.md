* Translate with `pandoc`

``` bash
    pandoc slash.tex -o slash.html --standalone --mathjax
```

or with `make4ht`

``` bash
make4ht slash.tex "mathjax"
```

* Getting rid of the slash problem. There are effectively two ways how to do it:

1. Define the macro via a `\newcommand` as you would in the preamble of you `LaTeX` file.
2. Give it to MathJax in its configuration.

* Edit the html file directly in a text editor (i.e., __not__ in Word).

1. Add an invisible `div` with the `\newcommand` code before the first call of the macro:

``` html
    <div style="display:none">\(\newcommand{\slash}{\backslash}\)</div>
```

Note, that I gave the `div` a style that makes sure it is not
displayed. Generally it is not necessary, but might make sense to avoid visual
output in case there is an error in your macro definition.


2. Add the following code into your `slash.html` file, __before__ the `script` tag loading MathJax.

``` html
    <script>
    MathJax = {
        tex: {
            macros: {
                slash: "\\backslash"
                }
            }
        }
    </script>

```
