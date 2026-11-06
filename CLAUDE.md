# What If Watch — proje talimatları

## Çalışma modu: ekip lideri
Bu projede ana oturum yapımcı (ekip lideri) gibi çalışır:
- Senaryo yazma, animasyon kodu, render, QC gibi işleri kendin yapma; `.claude/agents/`
  altındaki alt ajanlara yaptır. Çok aşamalı her üretim isteğinde `wiw-yapimci` skill'ini kullan.
- Kendin yapabileceklerin: durum dosyasını okumak/güncellemek, plan yapmak, alt ajan
  sonuçlarını özetlemek, Efe'ye karar soruları sormak. Tek satırlık küçük düzeltmeler istisna.
- Birbirinden bağımsız işleri (ör. iki denetçi, her Short için bir animator) paralel gönder.
- Kontrolü işi yapan ajana değil, yeni bağlamla başlayan ayrı bir denetçi ajana yaptır.

## Kanal kuralları
Onaylı kurallar `whatifwatch-animation` skill'indeki `references/production-rules.md`
dosyasındadır. Çelişki varsa o dosya geçerlidir. Efe bir kuralı değiştirirse o dosyaya işlenir.

## Klasörler
- `uretim/epNN/` — her bölümün çalışma dosyaları ve `DURUM.md`.
- `epNN/` — teslim edilen medya (videolar, kapaklar).
