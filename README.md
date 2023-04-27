# Python Learning Project

N.B add new content by adding new ipynb files to the doc folder. New rendered website should appear in https://cisreg.ca/plp/lab/index.html 

## Markdown file conversion
In order to convert markdown files from Notion: use the notedown Python package.

`pip install notedown`

 Then you can use it to convert the markdown file to jupyter notebook format *ipynb as follows:

 `notedown markdown/m1_variables.md   --to notebook --output variables_markdown.ipynb` 
 
 The conversion works perfectly most of the time, but we still need to inspect the resulting notebook file and fix any remaining issues.