# 📚 ANCE-PRF Interactive IR System

Proyek ini merupakan implementasi sistem *Information Retrieval* berbasis **ANCE** (Approximate Nearest Neighbor for Contextualized Embeddings) yang dipadukan dengan metode **Pseudo Relevance Feedback (PRF)** untuk meningkatkan kualitas pencarian informasi. Sistem dibangun dengan antarmuka pengguna menggunakan **Streamlit**, dan mengadaptasi pendekatan dari artikel *"Improving Retrieval : Improving Query Representations for Dense Retrieval with Pseudo Relevance Feedback"*.

---

## 🚀 Fitur Utama

- ✅ Input query dari pengguna
- 🔍 Proses retrieval awal menggunakan model dense retriever (ANCE-style)
- 📈 Peningkatan query menggunakan PRF (Pseudo Relevance Feedback)
- 💡 Menampilkan hasil pencarian sebelum & sesudah PRF
- 📊 Evaluasi metrik performa (MRR@10, nDCG@10, Recall@1000)
- 🎯 Query dinilai terhadap ground truth (qrels) dari dataset MS MARCO

---

## 🧠 Arsitektur Sistem

```mermaid
flowchart TD
    A["Input Query dari User"] --> B["Encode Query"]
    B --> C["Retrieval Awal (Top-K)"]
    C --> D["Hitung PRF Vector (mean of top-K)"]
    D --> E["Enhanced Query"]
    E --> F["Retrieval Ulang (Top-K)"]
    F --> G["Tampilkan Hasil + Evaluasi Metrik"]
