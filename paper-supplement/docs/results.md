---
title: Results – Context-Adaptive Distributions for Neural-Based Lossless Image Compression
---

# Context-Adaptive Distributions for Neural-Based Lossless Image Compression

**Authors:** Victor Fabre Figueiredo (Student Member, IEEE), Lucas S. Lopes (Member, IEEE),  
Ricardo L. de Queiroz (Fellow, IEEE), Philip A. Chou (Fellow, IEEE)

!!! abstract "Abstract"
    We present an innovative method for lossless coding using prediction and context-adaptive Laplacian modeling to code the residuals.
    Given a causal context, one lightweight neural network predicts the signal mean, while another estimates the scale of the prediction residual, assuming a zero-mean Laplacian density for the residual.
    The density is integrated to estimate a probability of the quantized residual, which drives an adaptive arithmetic coder to code the quantized residual.
    We show that with suitable quantization of the residual, this method is equivalent to using a shifted Laplacian to drive an arithmetic coder to code the original quantized signal.
    The networks are jointly trained to minimize the resulting bit rate.
    We instantiate different architectures to evaluate the method on 4K frames from the Ultra Video Group (UVG) dataset, and compare to High Efficiency Video Coding (HEVC) Intra Lossless, Free Lossless Image Format (FLIF), Context-Adaptive Lossless Image Compression (CALIC), and Context-based Bit-plane Codec (CBPNNv).
    Results show that the best architecture variant (a multi-layer perceptron) outperforms the competition, reducing the average bit rate by 30.58% relative to HEVC Intra Lossless and outperforming the state-of-the-art, CBPNNv, on average, while remaining shallow enough for real-time operation.
    These results indicate that jointly predicting the mean of the signal and scale of the prediction residuals enables efficient lossless coding.

---

## Bit-rate Results

> Bit-rate savings (in %) are reported **relative to HEVC Intra Lossless**. Values are in bpp; parentheses show savings vs HEVC.

<style>
  .table-wrap { overflow-x: auto; }
  table.wide-table { width: 100%; border-collapse: collapse; font-variant-numeric: tabular-nums; }
  .wide-table caption { caption-side: top; text-align: left; font-weight: 600; padding: .25rem 0 .5rem; }
  .wide-table th, .wide-table td { border: 1px solid var(--md-default-fg-color--lightest); padding: .5rem .6rem; text-align: center; }
  .wide-table thead th { background: var(--md-accent-fg-color--transparent); }
  .wide-table tbody tr:nth-child(even) { background: var(--md-default-fg-color--ultra-light); }
  .wide-table th[rowspan] { vertical-align: middle; }
  .wide-table td:first-child, .wide-table th:first-child { text-align: left; }
  .wide-table tfoot td { font-style: italic; font-weight: 600; }
</style>

<div class="table-wrap">

<table class="wide-table" aria-label="Bit-rate results">
  <caption>Bit-rate results. Bit-rate savings (in %) against HEVC Intra Lossless also indicated.</caption>
  <thead>
    <tr>
      <th rowspan="2">Video Sequence</th>
      <th colspan="4"><strong>State-of-the-art codecs</strong></th>
      <th colspan="3"><strong>Proposed method</strong></th>
    </tr>
    <tr>
      <th>HEVC Intra Lossless</th>
      <th>FLIF</th>
      <th>CALIC</th>
      <th>CBPNNv</th>
      <th>CNN</th>
      <th><strong>MLP</strong></th>
      <th>Transformer</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Beauty</td>
      <td>3.76</td>
      <td>3.45 (8.14%)</td>
      <td>3.42 (8.91%)</td>
      <td>3.40 (9.61%)</td>
      <td>2.22 (41.06%)</td>
      <td><strong>2.08 (44.56%)</strong></td>
      <td>3.39 (9.81%)</td>
    </tr>
    <tr>
      <td>Bosphorus</td>
      <td>3.12</td>
      <td>2.48 (20.65%)</td>
      <td>2.43 (22.15%)</td>
      <td>2.38 (23.73%)</td>
      <td>2.90 (7.08%)</td>
      <td><strong>2.37 (23.91%)</strong></td>
      <td>2.92 (6.45%)</td>
    </tr>
    <tr>
      <td>HoneyBee</td>
      <td>3.57</td>
      <td>3.01 (15.62%)</td>
      <td>2.97 (16.69%)</td>
      <td>2.94 (17.44%)</td>
      <td>2.70 (24.25%)</td>
      <td><strong>2.59 (27.48%)</strong></td>
      <td>2.94 (17.63%)</td>
    </tr>
    <tr>
      <td>Jockey</td>
      <td>3.18</td>
      <td>2.76 (13.10%)</td>
      <td>2.75 (13.39%)</td>
      <td>2.71 (14.80%)</td>
      <td>2.51 (20.87%)</td>
      <td><strong>2.38 (25.15%)</strong></td>
      <td>2.73 (13.94%)</td>
    </tr>
    <tr>
      <td>ReadySteadyGo</td>
      <td>3.47</td>
      <td>2.75 (20.70%)</td>
      <td>2.68 (22.72%)</td>
      <td>2.62 (24.62%)</td>
      <td>2.85 (17.77%)</td>
      <td><strong>2.33 (32.82%)</strong></td>
      <td>2.63 (24.24%)</td>
    </tr>
    <tr>
      <td>ShakeNDry</td>
      <td>4.16</td>
      <td>3.23 (22.31%)</td>
      <td>3.15 (24.28%)</td>
      <td>3.15 (24.25%)</td>
      <td>2.67 (35.80%)</td>
      <td><strong>2.65 (36.22%)</strong></td>
      <td>3.07 (26.19%)</td>
    </tr>
    <tr>
      <td>YachtRide</td>
      <td>3.41</td>
      <td>2.65 (22.19%)</td>
      <td>2.56 (24.89%)</td>
      <td><strong>2.51 (26.53%)</strong></td>
      <td>3.14 (7.99%)</td>
      <td>2.59 (23.94%)</td>
      <td>3.18 (6.88%)</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td><em><strong>Average bpp</strong></em></td>
      <td><em>3.52</em></td>
      <td><em>2.90 (17.53%)</em></td>
      <td><em>2.85 (19.00%)</em></td>
      <td><em>2.81 (20.14%)</em></td>
      <td><em>2.71 (22.12%)</em></td>
      <td><em><strong>2.43 (30.58%)</strong></em></td>
      <td><em>2.98 (15.02%)</em></td>
    </tr>
  </tfoot>
</table>

</div>

---

### Notes
- **Dataset:** UVG (4K frames).  
- **Competitors:** HEVC Intra Lossless, FLIF, CALIC, CBPNNv.  
- **Proposed variants:** CNN, **MLP** (best), Transformer.

??? info "LaTeX (para copiar e colar no paper)"
    ```latex
    \begin{table*}[t]
    \centering
    \caption{Bit-rate results. Bit-rate savings (in \%) against HEVC Intra Lossless also indicated.}
    \resizebox{\textwidth}{!}{
    \begin{tabular}{l|ccccccc|}
    \cline{2-8}
                                                                    & \multicolumn{4}{c|}{\textbf{State-of-the-art codecs}}                                                                                                           & \multicolumn{3}{c|}{\textbf{Proposed method}}                                        \\ \hline
    \multicolumn{1}{|l|}{\textbf{Video Sequence}}                   & \multicolumn{1}{c}{\textbf{HEVC Intra Losless}} & \multicolumn{1}{c}{\textbf{FLIF}} & \multicolumn{1}{c}{\textbf{CALIC}} & \multicolumn{1}{c|}{\textbf{CBPNNv}} & \textbf{CNN}            & \multicolumn{1}{c}{\textbf{MLP}} & \multicolumn{1}{c|}{\textbf{Transformer}} \\ \hline
    \multicolumn{1}{|l|}{Beauty}                                    & 3.76                                            & 3.45 (8.14\%)                     & 3.42 (8.91\%)                      & 3.40 (9.61\%)                        & 2.22 (41.06\%)               & \textbf{2.08 (44.56\%)}      & 3.39 (9.81\%)                        \\
    \multicolumn{1}{|l|}{Bosphorus}                                 & 3.12                                            & 2.48 (20.65\%)                    & 2.43 (22.15\%)                     & 2.38 (23.73\%)                       & 2.90 (7.08\%)                & \textbf{2.37 (23.91\%)}      & 2.92 (6.45\%)                        \\
    \multicolumn{1}{|l|}{HoneyBee}                                  & 3.57                                            & 3.01 (15.62\%)                    & 2.97 (16.69\%)                     & 2.94 (17.44\%)                       & 2.70 (24.25\%)               & \textbf{2.59 (27.48\%)}      & 2.94 (17.63\%)                        \\
    \multicolumn{1}{|l|}{Jockey}                                    & 3.18                                            & 2.76 (13.10\%)                    & 2.75 (13.39\%)                     & 2.71 (14.80\%)                       & 2.51 (20.87\%)               & \textbf{2.38 (25.15\%)}      & 2.73 (13.94\%)                        \\
    \multicolumn{1}{|l|}{ReadySteadyGo}                             & 3.47                                            & 2.75 (20.70\%)                    & 2.68 (22.72\%)                     & 2.62 (24.62\%)                       & 2.85 (17.77\%)               & \textbf{2.33 (32.82\%)}      & 2.63 (24.24\%)                        \\
    \multicolumn{1}{|l|}{ShakeNDry}                                 & 4.16                                            & 3.23 (22.31\%)                    & 3.15 (24.28\%)                     & 3.15 (24.25\%)                       & 2.67 (35.80\%)               & \textbf{2.65 (36.22\%)}      & 3.07 (26.19\%)                        \\
    \multicolumn{1}{|l|}{YachtRide}                                 & 3.41                                            & 2.65 (22.19\%)                    & 2.56 (24.89\%)                     & \textbf{2.51 (26.53\%)}              & 3.14 (7.99\%)               & 2.59 (23.94\%)               & 3.18 (6.88\%)                        \\ \hline
    \multicolumn{1}{|l|}{\textit{\textbf{Average bpp }}} & \textit{3.52}                                   & \textit{2.90 (17.53\%)}           & \textit{2.85 (19.00\%)}            & \textit{2.81 (20.14\%)}              & \textit{2.71 (22.12\%)} & \textbf{2.43 (30.58\%)} & \textit{2.98 (15.02\%)}                   \\ \hline
    \end{tabular}
    }
    \label{tab:CNN-lossless}
    \end{table*}
    ```
