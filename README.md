# Okul QR

Ders kitaplarındaki QR kodları büyük ekranda göstermeye yarayan, dokunmatik kullanıma uygun masaüstü uygulaması.

---

## Neden Yapıldı?

Bazı öğretmenler "QR kodu okutamıyoruz" sorununu dile getirdi. Bu uygulama o sorunu çözmek için geliştirildi: ders kitabındaki tüm QR kodları tek bir listede toplanır, büyük ekranda gösterilir ve üzerine dokunulduğu anda açılır.

---

## Nasıl Çalıştırılır?

```bash
bash baslat-beni.sh
```

İlk çalıştırmada betik otomatik olarak:
- Python 3 ve Tkinter kurulumunu kontrol eder / kurar
- `PDFs` klasörünü oluşturur
- Masaüstü kısayolu oluşturur ve uygulama menüsüne ekler

Sonraki çalıştırmalarda kurulum adımları atlanır ve program direkt açılır.

---

## Özellikler

- **Dokunmatik uyumlu** — büyük ekrana ve parmakla kullanıma göre tasarlandı
- **Canlı liste** — liste GitHub'dan otomatik çekilir, internet yoksa yedek dosya kullanılır
- **Tek dokunuşla aç** — karta dokunmak veya "Aç" butonuna basmak yeterli
- **Kaydırma** — parmakla sürükleyerek veya klavye ok tuşlarıyla kaydırılabilir
- **Klavye navigasyonu** — ↑ ↓ ile seçim, Enter ile açma
- **Filtrele** — Tümü / Video / PDF olarak filtrele
- **Ara** — ders adı, sayfa veya QR numarasına göre anlık arama
- **Sürüm kontrolü** — uygulamanın güncel olup olmadığı otomatik kontrol edilir

---

## Dosya Yapısı

```
Okul QR/
├── baslat-beni.sh       ← Çalıştırıcı betik (buradan başlat)
├── program.py           ← Ana uygulama (Python 3.6+)
├── program2.py          ← Eski Python uyumluluk sürümü (3.5+)
├── list-backup.txt      ← Yerel yedek liste (internet yokken kullanılır)
├── PDFs/                ← PDF tipindeki QR'lar için yerel dosyalar
│   └── DERS-SAYFA-QR.pdf
├── baslat.log           ← Otomatik oluşan hata/bilgi günlüğü
└── README.md
```

---

## Liste Formatı

`list-backup.txt` (ve GitHub'daki canlı liste) şu formatı kullanır:

```
# Bu bir yorumdur, atlanır

DERS-SAYFA-QRsirasi:URL
DERS-SAYFA-QRsirasi:PDF
DERS-SAYFA-QRsirasi:PDF:https://uzak-link.com/dosya.pdf
```

**Örnekler:**

| Satır | Anlamı |
|---|---|
| `TR-16-1:https://youtu.be/abc` | Türkçe kitabı, 16. sayfa, 1. QR → video |
| `TR-36-1:PDF` | Türkçe kitabı, 36. sayfa, 1. QR → PDFs/TR-36-1.pdf |
| `MAT-12-2:PDF:https://ornek.com/a.pdf` | Matematik, 12. sayfa, 2. QR → uzak PDF |

---

## Gereksinimler

| Gereksinim | Notlar |
|---|---|
| Python 3.5+ | `baslat-beni.sh` otomatik kurar |
| Tkinter | `baslat-beni.sh` otomatik kurar |
| İnternet | Opsiyonel — yoksa `list-backup.txt` kullanılır |

Desteklenen dağıtımlar: **Pardus / Debian / Ubuntu**, Arch, Fedora, RHEL, openSUSE

---

## Uygulama Çalışmıyorsa

1. `baslat.log` dosyasını açıp son satırlara bakın
2. `PDFs` klasöründen ilgili dersin PDF dosyasını açın
3. İstediğiniz QR kodunu bulup üzerine tıklayın

---

## Sürüm

`2.0` · Geliştirici: [PrintGoldenMan](https://github.com/PrintGoldenMan)

---

## Lisans

[MIT Lisansı](LICENSE) © 2026 PrintGoldenMan
