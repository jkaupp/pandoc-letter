# A simple letter template for Pandoc

This template allows you to write letters in Markdown and convert them to nice looking PDFs using [Pandoc][] and [LaTeX][]. It's basically just a copy of Pandoc's [default LaTeX template][latex-template], slightly modified to accept arguments used in the LaTeX letter class, including:

* opening
* closing
* address
* return-address

All of which can be specified in a YAML metadata block. For example:

	---
	author: You
	opening: To whom it may concern,
	closing: Sincerely,
	address: 
	 - Address 1
	 - Address 2
	return-address: 
	 - Address 1
	 - Address 2
	 - Address 3
	...

Note that each address component should start with a hypen. The provided example letter can be compiled with the following command (xelatex option included for different fonts/sizes):

```
pandoc --template=template-letter.tex letter.md -o letter.pdf --latex-engine=xelatex
```

## Extra features

`-V blockquote`
:   Nice looking blockquotes à la [bootstrap][]

`-V date=CUSTOMDATE`
:    Insert a custom date in place of today's date


[Pandoc]: http://johnmacfarlane.net/pandoc/
[LaTeX]: http://www.latex-project.org/
[latex-template]: https://github.com/jgm/pandoc-templates
[bootstrap]: http://getbootstrap.com/css/#type-blockquotes