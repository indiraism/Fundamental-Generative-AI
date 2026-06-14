# 🎨 Belajar Fundamental Generative AI

Submission project untuk kursus **Belajar Fundamental Generative AI** — mengimplementasikan pipeline image generation berbasis Stable Diffusion menggunakan library Diffusers dari Hugging Face, serta membangun aplikasi interaktif dengan Streamlit.

---

## 🚀 Fitur yang Diimplementasikan

### 📓 Notebook 1 — Image Generation Pipeline

| Kriteria      | Fitur                                                                                  |
| ------------- | -------------------------------------------------------------------------------------- |
| ✅ Kriteria 1 | **Text-to-Image** — Generate gambar dari teks prompt menggunakan Stable Diffusion v1.5 |
| ✅            | Perbandingan **Guidance Scale** (2.0 vs 15.0)                                          |
| ✅            | Perbandingan **Inference Steps** (5 vs 50)                                             |
| ✅            | **Batch Inference** dari satu prompt dengan berbagai seed                              |
| ✅ Kriteria 2 | **Image-to-Image** — Transformasi gambar dengan prompt baru                            |
| ✅            | Perbandingan **Strength** parameter                                                    |
| ✅ Kriteria 3 | **Scheduler Comparison** — PNDM, DDIM, DPM++, Euler                                    |
| ✅ Kriteria 4 | **Inpainting** — Edit area spesifik pada gambar menggunakan mask manual                |
| ✅            | **Auto-masking** menggunakan Segformer (segmentasi semantik)                           |
| ✅ Kriteria 5 | **Outpainting** — Ekspansi gambar ke luar batas aslinya                                |
| ✅            | **Outpainting Zoom Out** — Memperluas scene secara bertahap                            |

### 🖥️ Notebook 2 — Streamlit Application

Aplikasi web interaktif dengan fitur:

- **Text-to-Image** generation dengan kontrol parameter lengkap (seed, steps, CFG scale, scheduler)
- **Batch generation** dari satu prompt
- **Inpainting** dengan drawable canvas (gambar mask langsung di browser)
- **Outpainting** / zoom out otomatis
- Manajemen memori GPU (`flush_memory`)
- Pilihan scheduler: Euler A, DPM++, DDIM

---

## 🧰 Tech Stack

| Library                     | Versi        | Fungsi                         |
| --------------------------- | ------------ | ------------------------------ |
| `torch`                     | 2.11.0+cu128 | Deep learning framework (CUDA) |
| `diffusers`                 | 0.37.1       | Pipeline Stable Diffusion      |
| `streamlit`                 | 1.57.0       | Web UI                         |
| `streamlit_drawable_canvas` | 0.8.0        | Drawing tool untuk masking     |
| `Pillow`                    | 12.2.0       | Image processing               |
| `numpy`                     | 2.4.6        | Array operations               |

---

## ⚙️ Cara Menjalankan

### 1. Clone Repository

```bash
git clone https://github.com/indiraism/Fundamental-Generative-AI.git
cd Fundamental-Generative-AI
```

### 2. Install Dependensi

```bash
pip install -r requirements.txt
```

> **Catatan:** Pastikan CUDA sudah terinstall dan kompatibel dengan PyTorch `cu128`. Disarankan menggunakan GPU dengan VRAM minimal 6GB.

### 3. Jalankan Notebook Pipeline

Buka `notebooks/Pipeline_submission_BFGAI_Indira_Aline.ipynb` di Jupyter atau Google Colab (GPU runtime).

### 4. Jalankan Aplikasi Streamlit

Buka `notebooks/Streamlit_submission_BFGAI_Indira_Aline.ipynb` — notebook ini akan:

1. Membuat file `logic.py` dan `app.py`
2. Menjalankan Streamlit melalui `pyngrok` dengan public URL

---

## 🎯 Model yang Digunakan

- **[runwayml/stable-diffusion-v1-5](https://huggingface.co/runwayml/stable-diffusion-v1-5)** — Base model untuk Text-to-Image dan Image-to-Image
- **[runwayml/stable-diffusion-inpainting](https://huggingface.co/runwayml/stable-diffusion-inpainting)** — Model khusus Inpainting & Outpainting
- **[nvidia/segformer-b2-finetuned-ade-512-512](https://huggingface.co/nvidia/segformer-b2-finetuned-ade-512-512)** — Segmentasi semantik untuk auto-masking

---

## 👩‍💻 Author

**Indira Aline**  
Submission — Belajar Fundamental Generative AI  
Dicoding Indonesia
