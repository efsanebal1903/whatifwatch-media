# What If Watch — yedek (şifreli)

Tarih: 30 Ekim 2026. Bu daldaki dosyalar AES-256 ile şifrelidir; şifre yalnızca kanal sahibinde (Efe) vardır.

## İçerik
- **kod_yedek** (~117 MB): animasyon motorunun tamamı (pilot/, ep1/, ep2a/, ep3a/, motion2/ …), senaryolar, satır listeleri, dudak senkronu verileri, fontlar, küçük görseller, kanal skill'i (whatifwatch-animation) ve sohbet geçmişi. Ses ve video yok. Hızlı geri yükleme için.
- **tam_yedek** (~825 MB, 9 parça): yukarıdakilerin hepsi + bütün ses kayıtları (ElevenLabs kayıtları, satır satır kesilmiş sesler, yan sesler), kullanıcı ekleri ve çıktı klasörü (Short'lar, kapaklar, altyazılar, metinler; 100 MB'tan büyük ham uzun videolar hariç — yayınlanan sürümleri `publish` dalında).
- Yayınlanan videolar ve kapaklar zaten `publish` dalında: ep01/, ep02/, ep03/.

Dışarıda bırakılanlar (yeniden üretilebilir): render ara dosyaları (seg*.mp4, kontrol kareleri), 3D render kareleri, Kokoro ses modeli ve konuşma tanıma modeli (GitHub'dan yeniden indirilir: thewh1teagle/kokoro-onnx model-files-v1.0, k2-fsa/sherpa-onnx asr-models).

## Geri yükleme
```bash
git clone --branch yedek --depth 1 https://github.com/efsanebal1903/whatifwatch-media yedek && cd yedek
# hızlı (sadece kod):
cat kod_yedek.tar.gz.enc.part* | openssl enc -d -aes-256-cbc -pbkdf2 -iter 200000 -pass pass:'ŞİFRE' | tar -xzf -
# tam:
cat tam_yedek.tar.gz.enc.part* | openssl enc -d -aes-256-cbc -pbkdf2 -iter 200000 -pass pass:'ŞİFRE' | tar -xzf -
```
Çıkan klasörler: `scratchpad/` (motor ve bölümler), `USERDATA/outputs`, `USERDATA/attachments`, `meta/` (skill + sohbet geçmişi).
Motoru çalıştırmak: Python 3, `pip install playwright pillow numpy scipy`, Chromium (Playwright), ffmpeg. Uzun video önizleme: `cd scratchpad/ep3a && python3 dev.py ornek.jpg 10 60 120`; render: `python3 render3.py cikti.mp4`. Short: `python3 render_shorts3.py 3.1`. Ayrıntılar skill'in `references/engine-map.md` dosyasında.

Bütünlük kontrolü: `SHA256.txt` (tam yedek = parçaların birleşimi).
