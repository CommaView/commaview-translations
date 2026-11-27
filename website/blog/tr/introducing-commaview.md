---
title: "CommaView ile tanışın: comma cihazları için yerel kamera yayını"
description: "CommaView, comma cihazının kamerasını yerel ağda yayınlayan bir Android uygulaması: MICI tarzı katmanlar, çalışma ortamı kurulumu, kayıtlar ve sürüş tekrarları."
date: 2026-05-02
slug: introducing-commaview
tags:
  - CommaView
  - comma device camera streaming
  - Android app
  - openpilot tools
heroLabel: "Ürün notları"
draft: false
---

CommaView, comma kamerasına yerel ağdan erişmenin bir SSH oturumuna yapıştırılmış bir yığın betik gibi değil, gerçek bir ürün gibi hissettirmesi gerektiği için var.

Amaç basit: bir Android cihazı comma'nızla eşleştirmek, yol kamerasını yerel ağda yayınlamak, sürüş için işe yarar katmanlar göstermek ve kurulumu olabilecek en iyi anlamda sıkıcı hâle getirmek.

## Neden önce yerel?

CommaView bir bulut paneli olmaya çalışmıyor. Uygulama comma cihazınızla yerel bağlantınız üzerinden konuşur ve temel işleyişi donanıma yakın tutar.

Bu önemli, çünkü önce yerel çalışan bir comma kamera yayını uygulaması hızlı, anlaşılır ve gizliliğe saygılı kalabilir. Kendi cihazınızın gördüğünü görmek için bir hesap gerekmemeli.

## CommaView neleri üstleniyor

Şimdiki Alpha, günlük testleri daha az can sıkıcı hâle getiren kısımlara odaklanıyor:

- yol kamerasının Android'e yerel ağdan yayını
- MICI tarzı yol, şerit, durum ve sürücü izleme katmanları
- comma tarafındaki `commaviewd` hizmeti için rehberli kurulum
- sürüş kayıtları ve tekrar oynatmaların dışa aktarılması
- test edenlerin uyumlu sürümleri yüklemesi için uygulama ve çalışma ortamı sürümlerinin eşleştirilmesi

## Neden önce Android?

CommaView yalnızca Android'de, çünkü bu iş için pratik hedef Android: telefonlar, tabletler, dosyadan uygulama yükleme, yerel ağ ve araca uygun donanım orada çok daha iyi bir araya geliyor.

Bu odak, uygulamanın her olası platform için kendini sulandırmak yerine keskin kalmasını sağlıyor.

## Sırada ne var

İlk test edenler, kurulum akışını sağlamlaştırmamıza, cihaz uyumluluğunu doğrulamamıza ve canlı katmanların daha fazla araç ve comma kurulumunda doğru hizalanmasına yardım edecek.

Katılmak isterseniz ana sayfadaki erken erişim listesine yazılın. CommaView büyüdükçe bu blogu sürüm notları, test edenlere duyurular ve teknik notlar için kullanacağız.
