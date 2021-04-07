* Translate with `pandoc`

``` bash
pandoc reflow.tex -o reflow.html --standalone --mathjax
```

* The resulting document does not reflow. This is due to the CSS command that
  restricts the page width. We can get rid of it in the `reflow.html` file.

First remove

``` html
      max-width: 40em;
```

The document should now reflow. There are still a number of padding elements
which might be annoying. We can remove those now too:

``` html
      padding-left: 50px;
```

Removes the padding on the left hand side.


``` html
      padding-right: 50px;
```

Removes the padding on the right hand side.

* Note, that if you do the conversion with `make4ht` a lot less styling will be
  added by default. While this makes it somewhat less pretty, it ensures more flexibility.
