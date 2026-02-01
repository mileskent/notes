
Category Theory is the study of *abstractions of composition*.

```tikz
\usepackage{tikz-cd}
\begin{document}
\begin{tikzcd}[column sep=large, row sep=huge]
\textrm{People} \arrow[r, "\textcolor{red}{\textrm{Age}}", yellow!80!orange, thick] 
                \arrow[rd, "\textcolor{blue}{\ge 18?} \circ \textcolor{red}{\textrm{Age}}"', yellow!80!orange, thick] 
& \textrm{Integers} \arrow[d, "\textcolor{blue}{\ge 18?}", yellow!80!orange, thick] \\
& \{\textrm{True, False}\}
\end{tikzcd}
\end{document}
```
