
* markdown source from peterkrautzberger.org (cc-by, Peter Krautzberger)
* convert markdown to html:

``` bash
    pandoc word.md -o word.html --standalone --mathjax
```

* convert markdown to docx:
  $ pandoc word.md -o word.docx
* edit word document in windows (I stripped some extraneous content)
  * => saved as word_edited.docx
* convert word_edited.doc
  pandoc word_edited.docx -o word_edited.html --standalone --mathjax
