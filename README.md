# CSE 211 - In-Memory Database Project

> **Bu fork hakkında:** Bu proje, CSE 211 dersi kapsamında 4 kişilik bir ekiple (Group 19) geliştirilen bir dönem projesidir. Orijinal repo: [Computer-Engineering-Yeditepe/CSE-211-Term-project-Memory-Database](https://github.com/Computer-Engineering-Yeditepe/CSE-211-Term-project-Memory-Database).
>
> Görev dağılımı belgesinde modüller isim isim ayrılmış olsa da, commit geçmişi asıl katkı dağılımını gösteriyor: 11 commit'in 8'i bu hesaba (Efe Demirci) ait. Kişisel olarak asıl geliştirdiğim/düzelttiğim kısımlar: **çekirdek veritabanı motoru** (`src/core` — `Table`, `Row`, `Cell` veri yapıları), **indeksleme entegrasyonu** (`HashIndex`), **HTTP/REST API backend sunucusu** (`libs/httplib.h` entegrasyonu ve endpoint'ler), genel proje dokümantasyonu, `Doxyfile`/Doxygen yapılandırması (mevcut olanı düzenledim), ve `main.cpp` ile `Makefile` üzerindeki düzeltmeler.

## Kurulum ve Çalıştırma

### Gereksinimler
- C++17 destekleyen derleyici (g++ veya clang++)
- Python 3.x
- Flask (Python paketi)

### 1. Python Bağımlılıklarını Yükleyin
```bash
pip3 install flask requests
```

### 2. Projeyi Derleyin
```bash
make clean
make
```

### 3. Backend Sunucusunu Başlatın
```bash
./build/bin/main
```
Backend sunucu port 8080'de çalışacak.

### 4. Frontend Sunucusunu Başlatın (Yeni Terminal)
```bash
python3 frontend/app_simple.py
```
Frontend sunucu port 5002'de çalışacak.

### 5. Tarayıcıda Açın
```
http://localhost:5002
```

## Özellikler

- ✅ Veritabanı tablolarını görüntüleme
- ✅ Yeni tablo oluşturma
- ✅ Veri ekleme (Insert)
- ✅ Veri silme (Delete)
- ✅ SQL sorgu çalıştırma (SELECT, WHERE)
- ✅ REST API endpoint'leri

## API Endpoint'leri

- `GET /get_all` - Tüm veritabanını getir
- `GET /insert?col1=val1&col2=val2` - Veri ekle
- `GET /delete?id=1` - Satır sil
- `GET /create_table?name=TableName&columns=col1,col2&types=INT,STRING` - Tablo oluştur
- `GET /query?query=SELECT * FROM TableName` - SQL sorgu çalıştır

## Proje Yapısı

```
├── src/              # C++ kaynak kodları
├── include/          # Header dosyaları
├── frontend/         # Python Flask frontend
├── data/             # Test veritabanı dosyaları
├── libs/             # Harici kütüphaneler (json.hpp, httplib.h)
├── main.cpp          # Ana program
└── Makefile          # Derleme dosyası
```

## Notlar

- Backend ve frontend ayrı terminal pencerelerinde çalıştırılmalıdır
- Veritabanı dosyaları `data/` klasöründe JSON formatında saklanır
- Test veritabanı: `data/test_db.json`


