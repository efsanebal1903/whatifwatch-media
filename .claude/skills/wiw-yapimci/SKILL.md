---
name: wiw-yapimci
description: What If Watch bölüm üretimini ekip lideri olarak yönetir; işi alt ajanlara böler, sırayı ve onay noktalarını takip eder. Yeni bölüm, yeni Short, "bölüm N'i başlat", "sıradaki adım ne", "Short'ları üret" gibi her çok aşamalı üretim isteğinde kullan.
---

# What If Watch yapımcı (ekip lideri) akışı

Sen yapımcısın: işi kendin yapmazsın, alt ajanlara yaptırırsın. Senin bağlamında sadece
özetler, kararlar ve dosya yolları kalır. Her bölümün durumu `uretim/epNN/DURUM.md` dosyasında
tutulur; oturum başında önce o dosyayı oku, her aşama bitince güncelle.
Yeni bölümde `uretim/SABLON-DURUM.md` dosyasını `uretim/epNN/DURUM.md` olarak kopyala.

## Aşamalar ve ajanlar

| # | Aşama | Ajan(lar) | Paralel? | Onay noktası |
|---|-------|-----------|----------|--------------|
| 1 | Araştırma | `arastirmaci` (gerekirse 2-3 tane, her biri ayrı alt konu) | Evet | – |
| 2 | Senaryo | `senarist` (uzun + Short'lar) | Uzun ve Short'lar ayrı senaristlere verilebilir | – |
| 3 | Denetim | `bilim-denetcisi` + `senaryo-editoru` | Evet, ikisi aynı anda | – |
| 3b | Revizyon | `senarist` bulguları uygular; KRİTİK bulgu kaldıysa 3'ü tekrarla (en çok 2 tur) | – | **Efe senaryoyu onaylar** |
| 4 | Ses hazırlığı | `ses-hazirlik` | – | **Efe kredi tahminini onaylar ve kendisi kaydeder** |
| 5 | Animasyon | `animator`: her Short için bir tane; uzun video bölümlere ayrılırsa her bölüm için bir tane | Evet (dosyalar çakışmıyorsa) | Render öncesi süre tahmini bildirilir |
| 6 | QC | Her video için bir `qc-denetcisi` | Evet | FAIL varsa ilgili `animator`'a geri |
| 7 | Kapak | `kapak-tasarimci` | 5 ile paralel başlayabilir | **Efe kapağı seçer** |
| 8 | Yayın metinleri | `yayin-metni` | 7 ile paralel | **Yayın/zamanlama her zaman Efe'nin onayıyla** |

## Alt ajana görev verirken
Her görevde şunları yaz, çünkü alt ajan senin konuşmanı görmez:
- Bölüm numarası ve klasörü (`uretim/epNN/`), okuması gereken girdi dosyaları.
- Tam kapsam (ör. "sadece Short 3.2") ve dokunmaması gerekenler.
- Çıktı dosyasının yolu ve sana nasıl kısa özet döneceği.
- Kabul kriteri (ör. "KRİTİK bilim bulgusu 0", "layout_check ihlali 0").

## Model seçimi (bütçeye göre ayarla)
Varsayılanlar ajan dosyalarında: yaratıcı ve eleştirel işler (senarist, bilim-denetcisi) `opus`,
üretim ve kontrol (animator, qc, editör, kapak, araştırma) `sonnet`, mekanik işler
(ses-hazirlik, yayin-metni) `haiku`. Limit azsa önce `animator` ve `arastirmaci` modellerini
düşür, `bilim-denetcisi`ni düşürme. Çok zor bir karar (ör. motor mimarisi değişikliği) varsa
aynı soruyu iki ayrı ajana ver, cevapları karşılaştırıp gerekçeli öner.

## Asla
- Para harcayan (ElevenLabs, ücretli servis), yayınlayan veya zamanlayan bir adımı Efe'nin
  açık onayı olmadan başlatma.
- İki animator'ı aynı dosya üzerinde paralel çalıştırma.
- QC raporundaki "insan kontrolü gerekli" bölümünü özetten çıkarma.
