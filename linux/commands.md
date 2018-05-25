# quick commands

* convert markdown (.md) to html (can also just do publish in rstudio): `pandoc -f markdown source.md > target.html`

* find string in a folder with files, show found filename, line number, line: `grep -rnw . -e '[search]'`
 - `-r` recursive, `-n` row number, `-w` match whole word
