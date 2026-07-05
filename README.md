# Streamlit Chatbot Project

Materi belajar membangun chatbot berbasis LLM (Google Gemini) menggunakan [Streamlit](https://streamlit.io).

## Struktur Proyek

```
.
├── app/
│   ├── streamlit_app_basic.py   # Demo komponen dasar Streamlit
│   └── streamlit_chat_app.py    # Chatbot Gemini menggunakan Streamlit
├── notebooks/
│   └── Streamlit_for_Chatbot.ipynb  # Notebook materi training (versi Colab)
├── requirements.txt
└── README.md
```

## Menjalankan Secara Lokal

1. Buat virtual environment (opsional tapi disarankan):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Jalankan salah satu app:
   ```bash
   streamlit run app/streamlit_app_basic.py
   # atau
   streamlit run app/streamlit_chat_app.py
   ```
4. Untuk chatbot Gemini, masukkan **Google AI API Key** kamu di sidebar saat app terbuka.
   Dapatkan API key gratis di [Google AI Studio](https://aistudio.google.com/apikey).

> ⚠️ Jangan pernah commit API key atau token apa pun ke repo ini. Gunakan input di sidebar
> atau environment variable / `st.secrets` untuk kredensial.

## Menjalankan di Google Colab

Notebook `notebooks/Streamlit_for_Chatbot.ipynb` berisi versi interaktif materi ini,
lengkap dengan setup ngrok agar app Streamlit bisa diakses lewat URL publik dari Colab.

## Ringkasan Konsep

| Konsep | Penjelasan |
|---|---|
| `%%writefile` | Magic command Colab untuk menulis konten cell ke file di disk |
| `subprocess.Popen` | Menjalankan proses (Streamlit) di background tanpa memblokir notebook |
| `ngrok.connect()` | Membuat URL publik yang mengarah ke port lokal |
| `st.session_state` | Dictionary yang nilainya bertahan meskipun skrip dijalankan ulang |
| `st.chat_message()` | Membuat bubble chat dengan role user/assistant |
| `st.chat_input()` | Kotak input yang muncul di bagian bawah halaman |
| `st.stop()` | Menghentikan eksekusi skrip di titik tersebut |
| `st.rerun()` | Memaksa Streamlit me-refresh halaman dari awal |

## Referensi

- [Dokumentasi Streamlit](https://docs.streamlit.io)
- [Streamlit Chat Elements](https://docs.streamlit.io/develop/api-reference/chat)
- [Session State](https://docs.streamlit.io/develop/api-reference/caching-and-state/st.session_state)
- [Repo Demo Asli](https://github.com/adiptamartulandi/chatbot-streamlit-demo)
