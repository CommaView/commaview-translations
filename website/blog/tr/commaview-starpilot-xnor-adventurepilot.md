---
title: "CommaView artık StarPilot, xnor ve AdventurePilot ile çalışıyor"
description: "CommaView 0.0.163, 0.0.162'deki StarPilot'un ardından xnor-tech'in openpilot'unu ve AdventurePilot'u ekliyor. Her fork, comma 3X ve comma four'da Live View'da ne gösteriyor?"
date: 2026-10-12
slug: commaview-starpilot-xnor-adventurepilot
tags:
  - openpilot forks
  - StarPilot
  - sunnypilot
  - xnor
  - AdventurePilot
  - Rivian
heroLabel: "Sürüm notları"
draft: false
---

CommaView artık beş openpilot sürümüyle çalışıyor: **openpilot**, **sunnypilot**, **StarPilot**, **xnor-tech'in openpilot'u** (xnor ve rx sürümleri) ve **AdventurePilot**. StarPilot CommaView 0.0.162 ile geldi; 0.0.163 Beta'sı xnor ve AdventurePilot'u ekliyor. Her birinde Live View, fork'un kendi ekranını Android telefonunuzda, tabletinizde veya multimedya ünitenizde, o fork'un eklediklerle birlikte çizer.

Şimdiye kadar bu fork'larda kurulum “unsupported upstream remote” hatasıyla duruyordu. 0.0.163 uygulaması ve çalışma ortamıyla, openpilot'ta olduğu gibi yüklenir ve eşleşir.

## Her fork Live View'da ne gösteriyor

CommaView fork'un adından tahmin yürütmez. comma'nızdaki çalışma ortamı, fork'un ekranının neler eklediğini uygulamaya söyler; uygulama da bunu comma four ekranına, comma 3X ekranına veya CommaView'un kendi ekranına çizer.

| Fork | CommaView'un çizdiği |
| --- | --- |
| openpilot | comma four ve comma 3X ekranları ya da CommaView'un kendi katmanı |
| sunnypilot | sunnypilot'un ekranı: MADS, hız sınırı asistanı, gökkuşağı yol çizgisi, kör nokta göstergeleri ve comma 3X'e özel eklemeleri |
| StarPilot | StarPilot'un renkleri, widget'ları, uyarıları ve kamera seçimi |
| xnor | xnor sürümlerinde openpilot'un ekranı, rx'te sunnypilot'unki ve rx'in Rivian direksiyon rengi |
| AdventurePilot | şerit ortalama göstergesi, CURVE etiketi ve direksiyon modu rengiyle sunnypilot'un ekranı |

## StarPilot

StarPilot sürüş modlarını renkle gösterir ve CommaView, StarPilot'un seçtiği renkleri kullanır: kenarlığı, yol çizgisi ve widget'ları, uyarıları ve sürücü kamerası dahil kamera seçimi. Önce StarPilot'un **Disable Logging** ayarını kapatın: Live View'un yayın aldığı video kodlayıcıyı durdurur.

## xnor-tech'in openpilot'u: xnor ve rx

xnor-tech'in openpilot'u tek bir depodan iki sürüm hâlinde gelir. **xnor** dalları openpilot'un ekranını, **rx** dalları sunnypilot'unkini çalıştırır; ikisinde de xnor-tech'in araç destekleri vardır. CommaView, comma'nızın hangisini çalıştırdığını anlar ve o ekranı, uyarılarıyla birlikte comma'nın yazdığı gibi çizer.

rx çalıştıran bir Rivian'da direksiyon, aracın nasıl yönlendiğini gösterir: açıyla yönlendirirken yeşil, torkla yönlendirirken mavi. CommaView aynı renkleri comma four'un direksiyonunda ve comma 3X'in Deneysel mod düğmesinde çizer.

## AdventurePilot

AdventurePilot, kendi araç destekleri olan bir sunnypilot fork'u. CommaView, sunnypilot'un ekranını AdventurePilot'un eklemeleriyle çizer:

- **şerit ortalama göstergesi**: comma 3X ekranında itme ve kaymayı gösteren bir etiket, comma four'da küçük bir çubuk;
- comma 3X ekranında, viraj hız kontrolü devredeyken yanıp sönen **CURVE etiketi**;
- direksiyonda **direksiyon modu rengi** ve bir Rivian açı kanalından yönlendirirken yanal ivmeyi gösteren bir tork çubuğu.

## Nasıl edinilir

CommaView yalnızca davetle katılınan bir Beta'da. Davetliyseniz uygulama 0.0.163 güncellemesini kendisi sunar. Uygulama güncellendikten sonra comma'nızdaki çalışma ortamını uygulamadan güncelleyin, sonra istendiğinde comma'yı yeniden başlatın. Çalışma ortamı güncellemeleri araç P konumunda ve openpilot devre dışıyken yapılır; böylece bir sürüş asla yarıda kesilmez.

CommaView'da yeni misiniz? [Kurulum rehberi](/tr/guides/setup), uygulamayı yüklemeyi ve comma'nızı bağlamayı adım adım anlatır.

## Değişmeyenler

- CommaView **comma 3X** ve **comma four** üzerinde çalışır. comma 3 hâlâ desteklenmiyor; xnor-c3 gibi fork'ların comma 3 sürümleri de dahil ([neden](/tr/#faq-comma-3)).
- CommaView fork'unuzun sürüşünü asla değiştirmez. Yanına küçük bir çalışma ortamı, ekran arayüzüne de küçük bir kanca ekler; böylece aynı yol çizgisini, şeritleri ve uyarıları çizebilir.
- CommaView'un henüz desteklemediği bir fork'ta kurulum durur ve comma'nızı olduğu gibi bırakır. Fork'unuzun desteklenmesini my.commaview.com'daki özellik panosundan isteyebilirsiniz.

## Daha fazlası

- [Hangi openpilot fork'ları CommaView ile çalışıyor](/tr/forks) ve her biri ne gösteriyor
- Her sürümde [Yenilikler](/tr/whats-new)
- [CommaView sürümleri nasıl çıkıyor](/tr/guides/releases)

CommaView resmî değildir; comma.ai, sunnypilot, StarPilot, xnor-tech veya AdventurePilot ile bağlantılı değildir. Beta yazılımıdır ve bir güvenlik sistemi değildir: dikkatinizi asla sürüşten dağıtmasına izin vermeyin.
