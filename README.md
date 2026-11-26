# Belajar Programming

Repositori ini berisi modul pembelajaran pemrograman yang terorganisir ke dalam tiga **GitBook Spaces** terpisah, masing-masing dengan struktur dan navigasi sendiri.

---

## 📚 Daftar Modul

| Modul | Deskripsi | Status |
|-------|-----------|--------|
| **[🐍 Belajar Python](./python)** | Dasar Python, OOP, modules, hingga project cybersecurity (packet sniffer, port scanner, wordlist generator) | ✅ Ada materi |
| **[🟨 Belajar JavaScript](./javascript)** | Dasar JavaScript, DOM, Async/Await, ES6+, Modules, Node.js, Express, REST API | 🚧 Placeholder |
| **[🌐 Belajar HTML & CSS](./html-css)** | Semantic HTML, Forms, Accessibility, CSS Box Model, Flexbox/Grid, Animations, Responsive Design, Projects | 🚧 Placeholder |

---

## 🗂️ Struktur Repository

```
Belajar-python/
├── gitbook-docs.yaml          # Konfigurasi multi-space GitBook
├── README.md                  # File ini
├── LICENSE
├── assets/                    # Asset bersama (logo, dsb)
│
├── python/                    # 🐍 MODUL PYTHON
│   ├── gitbook.yaml           # Config space Python
│   ├── SUMMARY.md             # Table of Contents Python
│   ├── fundamentals/          # Dasar-dasar Python (menunggu materi)
│   │   ├── 01-basics.md
│   │   ├── 02-control-flow.md
│   │   ├── 03-functions.md
│   │   ├── 04-oop.md
│   │   └── 05-modules-packages.md
│   ├── cybersecurity/         # Project cybersecurity (existing)
│   │   ├── 01-python-fundamentals.md
│   │   ├── 02-network-programming.md
│   │   ├── 03-project-packet-sniffer.md
│   │   ├── 04-project-port-scanner.md
│   │   ├── 05-project-wordlist-generator.md
│   │   └── 06-final-challenge.md
│   └── assets/
│
├── javascript/                # 🟨 MODUL JAVASCRIPT
│   ├── gitbook.yaml
│   ├── SUMMARY.md
│   ├── fundamentals/
│   │   ├── 01-basics.md
│   │   ├── 02-dom-manipulation.md
│   │   ├── 03-async-await.md
│   │   ├── 04-es6+.md
│   │   └── 05-modules.md
│   ├── nodejs/
│   │   ├── 01-intro.md
│   │   ├── 02-express.md
│   │   └── 03-api-building.md
│   └── assets/
│
└── html-css/                  # 🌐 MODUL HTML & CSS
    ├── gitbook.yaml
    ├── SUMMARY.md
    ├── html/
    │   ├── 01-semantic-html.md
    │   ├── 02-forms.md
    │   └── 03-accessibility.md
    ├── css/
    │   ├── 01-box-model.md
    │   ├── 02-flexbox-grid.md
    │   ├── 03-animations.md
    │   └── 04-responsive.md
    ├── projects/
    │   ├── 01-landing-page.md
    │   └── 02-dashboard.md
    └── assets/
```

---

## 🚀 Cara Akses di GitBook

Setelah repo di-import ke GitBook, akan muncul **3 Spaces** di sidebar kiri:

1. **Belajar Python** (default) — `/python`
2. **Belajar JavaScript** — `/javascript`
3. **Belajar HTML & CSS** — `/html-css`

Setiap space punya navigasi sendiri (`SUMMARY.md`) dan config sendiri (`gitbook.yaml`).

---

## 📝 Catatan Pengembangan

- **Python**: Materi cybersecurity sudah ada (6 file). Folder `fundamentals/` masih kosong — menunggu materi dasar Python.
- **JavaScript & HTML/CSS**: Hanya struktur folder + placeholder `SUMMARY.md`. Materi akan ditambahkan setelah sumber disediakan.
- Setiap modul terpisah total — bisa dikembangkan paralel tanpa konflik.

---

## 🤝 Kontribusi

1. Fork repository ini
2. Tambah/edit materi di folder modul yang sesuai
3. Update `SUMMARY.md` modul terkait jika menambah file baru
4. Buat Pull Request

---

## 📄 Lisensi

Lihat file [LICENSE](./LICENSE).