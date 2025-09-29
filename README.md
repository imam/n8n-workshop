# N8N Tutorial Slides

Tutorial slides untuk belajar N8N automation platform menggunakan Reveal.js.

## 🚀 Quick Start

### Prerequisites
- Node.js (v14 atau lebih baru)
- npm atau yarn

### Installation & Setup

1. **Clone atau download repository ini**
```bash
git clone [repository-url]
cd n8n-tutorial
```

2. **Install dependencies**
```bash
npm install
```

3. **Jalankan development server**
```bash
npm start
```

4. **Buka browser ke** `http://localhost:8080`

## 📁 Struktur Repository

```
n8n-tutorial/
├── package.json                # Dependencies dan scripts
├── README.md                   # File ini
├── index.html                  # Main presentation file
├── day-1/
│   ├── slides.md              # Day 1 slides content
│   └── images/                # Day 1 specific images
├── assets/
│   ├── css/
│   │   └── custom.css         # Custom styling
│   └── images/
│       └── common/            # Shared images
└── dist/                      # Generated presentations
```

## 📝 Day 1 Content

### Materi yang Dicakup:
1. **Introduction N8N** - Pengenalan platform dan use cases
2. **User Interface** - Tour interface dan navigation
3. **Workflow Concepts** - Konsep workflow dan node
4. **N8N Triggers** - Berbagai jenis trigger
5. **Credentials** - Manajemen kredensial dan keamanan
6. **Execution History** - Monitoring dan debugging

### Target Learning:
- ✅ Memahami interface N8N
- ✅ Membuat workflow sederhana
- ✅ Menggunakan berbagai trigger
- ✅ Mengelola kredensial
- ✅ Memonitor eksekusi workflow

## 🖼️ Images Placeholder

Untuk melengkapi slides, tambahkan images berikut ke `day-1/images/`:

### Required Images:
- `n8n-logo.png` - Logo N8N
- `ui-dashboard.png` - Screenshot dashboard
- `ui-canvas.png` - Screenshot canvas workspace
- `ui-node-panel.png` - Screenshot node panel
- `workflow-concept.png` - Diagram konsep workflow
- `trigger-examples.png` - Icons trigger nodes
- `credentials-add.png` - Screenshot form credentials
- `execution-history.png` - Screenshot execution history
- `exercise-overview.png` - Diagram exercise workflow

### Image Guidelines:
- **Resolution**: 1920x1080 atau proporsi 16:9
- **Format**: PNG atau JPG
- **Size**: < 2MB per image
- **Content**: Clear, readable screenshots dengan zoom yang tepat

## 🎨 Customization

### Mengubah Theme:
Edit `assets/css/custom.css` untuk:
- Colors dan branding
- Font family
- Layout adjustments
- Custom animations

### Menambah Content:
Edit `day-1/slides.md`:
- Gunakan `---` untuk slide baru
- Gunakan `--` untuk sub-slide
- Gunakan `Note:` untuk speaker notes

### Reveal.js Configuration:
Edit `index.html` untuk mengubah:
- Transition effects
- Plugin configuration
- Presentation settings

## 📱 Navigation

### Keyboard Shortcuts:
- **Arrow Keys** - Navigate slides
- **Space** - Next slide
- **Shift + Space** - Previous slide
- **Esc** - Slide overview
- **S** - Speaker notes mode
- **F** - Fullscreen
- **B** - Blackout screen

### Presentation Mode:
- **Speaker Notes**: Tekan `S` untuk membuka speaker view
- **PDF Export**: Tambahkan `?print-pdf` ke URL
- **Overview**: Tekan `Esc` untuk slide overview

## 🔧 Development

### Scripts Available:
```bash
npm start       # Start development server
npm run dev     # Alias untuk start
npm run build   # Prepare for production
```

### Adding New Days:
1. Buat folder `day-X/`
2. Tambah `slides.md` dan `images/`
3. Update `index.html` dengan link baru
4. Update navigation di slides

## 📦 Deployment

### GitHub Pages (Recommended):
Repository ini **ready untuk GitHub Pages** tanpa konfigurasi tambahan!

#### Langkah Deploy:
1. **Push repository** ke GitHub
2. **Buka Settings** repository di GitHub
3. **Pilih Pages** di sidebar kiri
4. **Source**: Deploy from a branch
5. **Branch**: main (atau master)
6. **Folder**: / (root)
7. **Save** dan tunggu beberapa menit

#### URL Akses:
```
https://[username].github.io/[repository-name]/
```

#### Features yang Sudah Ready:
✅ Reveal.js assets sudah di-bundle di `lib/`
✅ Semua path sudah relative dan compatible
✅ Navigation antar hari berfungsi
✅ Mobile responsive

### Hosting Alternatif:
Repository ini juga compatible dengan:
- Netlify (drag & drop folder)
- Vercel (import dari GitHub)
- Surge.sh (`surge .`)

### Build for Production:
```bash
npm run build
```

Hasil build ada di folder `dist/` (jika dikonfigurasi).

## 🤝 Contributing

### Untuk Menambah Content:
1. Fork repository
2. Buat branch baru
3. Tambah content dan images
4. Test di local
5. Submit pull request

### Guidelines:
- Ikuti struktur markdown yang ada
- Pastikan images resolution konsisten
- Test slides di berbagai screen size
- Tambah speaker notes untuk context

## 📚 Resources

### N8N Resources:
- [N8N Documentation](https://docs.n8n.io)
- [N8N Community](https://community.n8n.io)
- [N8N GitHub](https://github.com/n8n-io/n8n)

### Reveal.js Resources:
- [Reveal.js Documentation](https://revealjs.com/)
- [Markdown Plugin](https://revealjs.com/markdown/)
- [Themes Gallery](https://revealjs.com/themes/)

## 📄 License

MIT License - Feel free to use for educational purposes.

## 🆘 Support

Jika ada pertanyaan atau issue:
1. Check existing issues di repository
2. Buat issue baru dengan detail yang jelas
3. Contact: [your-email@domain.com]

---

**Happy Learning! 🎉**