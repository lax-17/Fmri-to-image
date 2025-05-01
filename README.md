
---

## 🧪 Datasets

- **Dataset:** [Algonauts 2023](https://algonauts.csail.mit.edu/)
- **Subject:** 1 (Left Hemisphere only)
- **Input:** PCA-reduced fMRI data (N = 256 or 1024 components)
- **Target:** 64×64 natural images (normalized to [-1, 1])

---

## 📊 Models & Losses

| Model                     | Conditioning | Loss Function | Notes                          |
|--------------------------|--------------|----------------|--------------------------------|
| StyleGAN2 + Mapper       | PCA → W+     | MSE            | Domain mismatch (face generator) |
| cDCGAN                   | PCA + noise  | BCE, LSGAN     | Generator easily overpowered   |
| cSAGAN                   | PCA + noise  | LSGAN          | Training instability           |
| U-Net + PatchGAN         | PCA only     | LSGAN          | Most stable adversarial model  |
| Supervised U-Net Decoder | PCA only     | L1 loss        | Best structure; blurry results |

---

## 🧠 Key Findings

- Standard GANs (especially with BCE loss) suffer from instability and vanishing gradients.
- LSGAN improves training stability but not visual fidelity significantly.
- Pretrained StyleGAN2 models require careful domain alignment (e.g., faces vs. scenes).
- Supervised U-Net models are more robust, although outputs are blurry due to pixel-wise loss.
- Future directions include VQ-based models, IC-GANs, and CLIP-conditioned diffusion models.

---

## 🛠 Dependencies

These notebooks were developed in **Google Colab Pro** and **Kaggle** using:
- Python 3.9+
- PyTorch 1.12+
- NumPy, Matplotlib, Scikit-learn
- torchvision, tqdm, etc.

---

## 📌 Notes

- Some notebooks (e.g., `cSAGAN_with_LSGAN`) may not render on GitHub due to metadata issues. Open them directly in [Google Colab](https://colab.research.google.com/) for full interactivity.
- fMRI preprocessing and PCA are assumed to be precomputed. Include `.npz` or `.npy` files as needed.

---

## 📄 License

This project is for academic and research purposes. Please cite the original datasets and models used in your own work.

---

## 🙋‍♂️ Author

**Laxmikant Jaynarayan Nishad**  
MSc Artificial Intelligence — Sheffield Hallam University  
Email: `LaxmikantJaynarayanbhai.J.Nishad@student.shu.ac.uk`

---

## 🌐 Related Links

- [Algonauts Project 2023](https://algonauts.csail.mit.edu/)
- [StyleGAN2 (Karras et al.)](https://github.com/NVlabs/stylegan2)
- [Self-Attention GAN (SAGAN)](https://arxiv.org/abs/1805.08318)
- [U-Net Architecture](https://arxiv.org/abs/1505.04597)


