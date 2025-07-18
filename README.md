# 🧼 ClearVision: Deep Image Denoising with VQ-VAE and Perceptual Losses

> A complete deep learning pipeline for restoring **noisy or degraded images** using a VQ-VAE architecture with perceptual loss. The project includes image scraping, degradation simulation, and model training for high-quality image restoration.

---

## 🌟 Key Features

- 🧠 **VQ-VAE-based Restoration**: Learns to reconstruct clean images from corrupted ones.
- 🏗️ **UNet Decoder**: Improves reconstruction using skip connections.
- 📉 **Perceptual Losses**: Combines L1, L2, LPIPS, SSIM, and PSNR for better visual quality.
- 🖼️ **Image Scraper**: Automatically downloads images from Unsplash.
- 💥 **Image Degrador**: Simulates real-world noise like blur, JPEG compression, and occlusion.
- 🔄 **Codebook Usage Tracking**: Measures and logs code usage for efficient quantization.
- 🧪 **Validation Tools**: Live visualization of reconstruction and statistics.

---

## 🧱 Architecture
-------------------------------------------------------------------------------

- Clean Images      →  Scraper
- Corrupted Images  ←  Degrador
- Model Input  →  Encoder → Vector Quantizer → UNet Decoder → Reconstructed Output

-------------------------------------------------------------------------------
### 📦 Components

- **Encoder:** Encodes input image into latent vector z
- **Quantizer:** Discretizes z using nearest embedding from codebook
- **UNet Decoder:** Reconstructs clean image from quantized z (uses skip connections)
- **Loss:** Weighted combination of MSE, L1, LPIPS, and optionally SSIM/PSNR
---

## 🧪 Loss Functions

- **L1 Loss**: Mean absolute error
- **L2 (MSE) Loss**: Mean squared error
- **LPIPS**: Learned perceptual similarity via pretrained VGG or AlexNet
- **SSIM**: Structural similarity index
- **PSNR**: Peak Signal-to-Noise Ratio

These are combined to form a weighted total loss optimized during training.

---

## 📦 Installation

```bash
git clone https://github.com/akgWindward/Clear-Vision.git
cd Clear-Vision
pip install -r requirements.txt

