# icml

\documentclass{article}
\usepackage{booktabs} % 用于更美观的表格线条
\usepackage[margin=1in]{geometry} % 设置页边距，可选

\begin{document}

\begin{table}[htbp]
\centering
\begin{tabular}{lcccc}
\toprule
Methods         & Exp-1 & Exp-2 & Exp-3 & Avg $\pm$ std \\
\midrule
Random          & 68.76 & 68.83 & 69.17 & 68.92 (0.22) \\
Avg-sim         & 70.08 & 70.24 & 70.73 & 70.35 (0.34) \\
Perplexity      & 63.98 & 64.97 & 64.61 & 64.52 (0.50) \\
Influence       & 65.33 & 65.25 & 65.02 & 65.20 (0.16) \\
Rewriting       & 64.38 & 64.56 & 64.49 & 64.47 (0.09) \\
Perplexity-MAB  & 65.19 & 65.35 & 65.30 & 65.28 (0.08) \\
Influence-MAB   & 68.49 & 67.68 & 67.17 & 67.78 (0.67) \\
EQUAL(ours)     & 72.51 & 72.70 & 73.78 & 73.01 (0.69) \\
\bottomrule
\end{tabular}
\label{tab:experiment_results}
\end{table}

\end{document}
