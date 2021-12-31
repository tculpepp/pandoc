# Creating a custom Pandoc template

I'm working to create a custom [Pandoc](https://github.com/jgm/pandoc) template that meets the paper requirements for [Trident University](https://www.trident.edu/). (I'll list those requirements here at a later date...)

I'm building off the work of a few other people:

- [The Eisvogel Template](https://github.com/Wandmalfarbe/pandoc-latex-template) by [
Pascal Wagler](https://github.com/Wandmalfarbe)
- [This Pandoc-APA template](https://github.com/iamamutt/pandoc-apa) by [
Joseph M. Burling](https://github.com/iamamutt)
- Of course the default template from [Pandoc](https://github.com/jgm/pandoc) by [John McFarlane](https://github.com/jgm)

I am currently using a modified version of the Pandoc-APA template and it meets *most* of my needs, but it didn't do so well when I tried adding code blocks to my papers. 

## Template Goals

- Meet Trident paper requirements guidelines
- create legible and attractive code blocks (sometimes multi-page)
- Auto citations from bibtex