<div align="center">   

# SORA: Free Second-Order Attacks in Fast Adversarial Training

</div>

Official implementation of SORA: Free Second-Order Attacks in Fast Adversarial Training (ICML 2026).

**Code maintainers:**  
[Mazdak Teymourian](https://github.com/MazMazTey) · [Ramtin Moslemi](https://github.com/RamtinMoslemi)


## Abstract
Adversarial Training (AT) is a leading defense against adversarial examples but often suffers from *Catastrophic Overfitting* (CO) in efficient single-step variants, where robustness to multi-step attacks collapses despite high single-step performance.  

We address this failure mode with two contributions.  
1. We identify *Epsilon Overfitting* (EO), a previously overlooked phenomenon in which fixed perturbation magnitudes exacerbate CO, and show that introducing perturbation variability significantly improves robust
generalization across different architectures and datasets.  
2. We propose **PertAlign** (Perturbation Alignment), a theoretically grounded, computationally negligible metric that predicts CO onset by measuring gradient alignment across attack stages.  

Leveraging these insights, we introduce **SORA**, an adaptive step-size adversarial training method that dynamically adjusts perturbations based on loss surface geometry. SORA consistently prevents CO, achieves state-of-the-art robustness and clean accuracy, and generalizes across datasets and architectures using a single fixed set of hyperparameters.  

Extensive experiments on diverse datasets and architectures show that SORA matches or surpasses the robustness of prior methods while delivering higher clean accuracy and superior efficiency.

---

## Environment Setup

Clone the repository:
```bash
cd 2026_ICML_SORA

conda env create -f environment.yml
conda activate cenv
cd src
```

## Training

```
python main.py \\
    --root_path "path/to/results/root" \\
    --attack SORA \\
    --epsilon 8 \\
    --model PreActResNet18 \\
    --dataset CIFAR10 \\
    --epochs 30 \\
    --track_alignment \\
    --normalize_dataset
```


## Citation
If you use this code in your own work, please cite our paper:
```
@inproceedings{
    teymourian2026sora,
    title={{SORA}: Free Second-Order Attacks in Fast Adversarial Training},
    author={Teymourian, Mazdak and Moslemi, Ramtin and Rahmani, Farzan and Rohban, Mohammad Hossein},
    booktitle={Proceedings of the 43rd International Conference on Machine Learning},
    publisher={PMLR},
    year={2026},
    doi={},
    url={https://openreview.net/forum?id=uynAkGdnmj},
    note={accepted}
}
```

## License
The majority of this repository is licensed under CC-BY-NC 4.0 (Creative Commons Attribution-NonCommercial 4.0 International License).
