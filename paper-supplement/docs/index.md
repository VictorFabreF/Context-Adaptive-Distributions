---
title: Supplement – Context-Adaptive Distributions for Neural-Based Lossless Image Compression
---

# Context-Adaptive Distributions for Neural-Based Lossless Image Compression

**Authors:**  
Victor Fabre Figueiredo (Student Member, IEEE),  
Lucas S. Lopes (Member, IEEE),  
Ricardo L. de Queiroz (Fellow, IEEE),  
Philip A. Chou (Fellow, IEEE)

!!! abstract "Abstract"
    We present an innovative method for lossless coding using prediction and context-adaptive Laplacian modeling to code the residuals.  
    Given a causal context, one lightweight neural network predicts the signal mean, while another estimates the scale of the prediction residual, assuming a zero-mean Laplacian density for the residual.  
    The density is integrated to estimate a probability of the quantized residual, which drives an adaptive arithmetic coder to code the quantized residual.  
    We show that with suitable quantization of the residual, this method is equivalent to using a shifted Laplacian to drive an arithmetic coder to code the original quantized signal.  
    The networks are jointly trained to minimize the resulting bit rate.  
    We instantiate different architectures to evaluate the method on 4K frames from the Ultra Video Group (UVG) dataset, and compare to High Efficiency Video Coding (HEVC) Intra Lossless, Free Lossless Image Format (FLIF), Context-Adaptive Lossless Image Compression (CALIC), and Context-based Bit-plane Codec (CBPNNv).  
    Results show that the best architecture variant (a multi-layer perceptron) outperforms the competition, reducing the average bit rate by **30.58%** relative to HEVC Intra Lossless and outperforming the state-of-the-art, CBPNNv, on average, while remaining shallow enough for real-time operation.  
    These results indicate that jointly predicting the mean of the signal and scale of the prediction residuals enables efficient lossless coding.

---

## Quick Links
- 📊 **Results table:** [Results](results/)
- 📄 **Paper PDF:** _add link here_  
- 💾 **Code:** _add link here_  
- 🧪 **Dataset (UVG 4K frames):** _add link or citation here_  

---

## Reproducibility (optional)
Use this section to point to code, checkpoints e instruções para replicar os experimentos.

- **Environment:** brief specs / Python version.  
- **Training:** joint training of mean–scale networks minimizing estimated bitrate.  
- **Evaluation:** UVG 4K; competitors: HEVC Intra Lossless, FLIF, CALIC, CBPNNv.

??? note "BibTeX (placeholder — substitua quando o DOI estiver disponível)"
    ```bibtex
    @misc{fabre2025contextadaptive,
      title   = {Context-Adaptive Distributions for Neural-Based Lossless Image Compression},
      author  = {Victor Fabre Figueiredo and Lucas S. Lopes and Ricardo L. de Queiroz and Philip A. Chou},
      year    = {2025},
      note    = {Supplementary material},
      howpublished = {\url{https://<usuario>.github.io/paper-supplement}}
    }
    ```

---

### Acknowledgments (optional)
Add funding, grants, or institutional acknowledgments here.
