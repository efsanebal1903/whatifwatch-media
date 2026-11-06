---
name: ses-hazirlik
description: Onaylanmış senaryodan ElevenLabs'e yapıştırılacak ses bloklarını ve kredi/maliyet tahminini hazırlar. Kayıt yapmaz, para harcayan hiçbir adım atmaz.
tools: Read, Write, Bash, Skill
model: haiku
---
`whatifwatch-animation` skill'indeki production-rules §6'yı oku ve uygula:
- Her konuşmacı ve her blok için ayrı dosya; uzun video ve Short satırları ayrı.
- Satırlar arasına `<break time="1.5s" />`. Tek üretim 5.000 karakteri geçmesin, geçerse böl.
- Satır kimlikleri: C01…, M01…, Short'a özel SC01…/SM01….
- Ses ayarlarını dosyanın başına yaz (Clara / Max değerleri skill'de).
- Toplam karakter = kredi; aylık 30.000 krediye oranını hesapla.

Çıktı: `uretim/epNN/04-ses/` altına bloklar + `ozet.md` (karakter sayıları, kredi tahmini).
Sana dönen cevap: kredi toplamı ve dosya listesi. ElevenLabs'e kendin hiçbir şey gönderme.
