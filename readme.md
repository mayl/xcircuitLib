# My Xcircuits libraries

# Some workflow notes
Although I generally enjoy the asthetic of `Xcircuit`'s output, it can be quite esoteric sometimes and assumes a fluency with `LaTeX` which I don't quite have.  These are some workflow notes I'm keeping as I figure things out.

* `xcircuit` has a `LaTeX` mode (under the `text` menu) which when turned on generates a `*.tex` to go along with the normal `*.ps` (postscript) output.  This `.tex` file is designed to be used in a larger `.tex` document and allows the main `tex` environment to choose fonts and do the typesetting of text inside the `xcircuit` figure via the `epsfig` package.  An example of using an `xcircuit` figure named `test` which lives in the `../figs/testFig` subdirectory would work like so:
    ```latex
    \documentclass{article}
    \usepackage{epsfig}
    \graphicspath{{./figs}}

    \begin{document}
    \input{./figs/testFig/test.tex}
    \end{document}
    ```
    
    * The `tex` output from `xcircuit` doesn't seem to play well with `latexmk -pdf` but does work with `latexmk --pdfdvi`
    * Running `latexmk -pdfdvi -pvc` (__p__re-__v__iew __c__ontinuous) opens an auto-updating preview which will pickup when you re-write out from `xcircuit`

