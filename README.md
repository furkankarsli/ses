# Frekans Sentezleyici ve Sinyal Laboratuvarı (Frequency Synthesizer & Signal Lab)

Bu proje, Vanilla JavaScript ve **Web Audio API** kullanılarak geliştirilmiş, tarayıcı tabanlı gelişmiş bir stereo osilatör ve ses sentezleyicidir. Dijital sinyal işleme (DSP) tekniklerini kullanarak beyin dalgalarını yönlendirmek (Brainwave Entrainment), odaklanmayı artırmak veya özel ses mimarileri (Monaural/Binaural Beats) yaratmak amacıyla tasarlanmıştır.

## Projenin Amacı ve Bilimsel Yaklaşım
Bu sistemin temel gücü, birbirine çok yakın frekansların (Örn: 121 Hz ve 122 Hz) üst üste bindirilerek **Monaural Beat (Tek Kulaklı Vuruş)** elde edilmesi prensibine dayanır. İki frekans fiziksel olarak çarpıştığında, aradaki fark kadar (1 Hz - Delta frekansı) ritmik bir dalgalanma yaratır. Bu ritmik vuruşlar, beynin "Frekans Takip Tepkisi" (Frequency Following Response) aracılığıyla fiziksel olarak yavaşlamasına ve odak/uyku moduna geçmesine yardımcı olur.

## Teknik Özellikler ve Sistem Mimarisi

* **Çoklu Osilatör Yönetimi:** Eşzamanlı olarak sınırsız sayıda frekans eklenebilir (Sinüs, Kare, Testere, Üçgen dalga formları).
* **Gerçek Zamanlı Osiloskop (Time-Domain Visualizer):** Üretilen sinyallerin fiziksel girişimlerini (interference) ve üst üste binme (superposition) durumlarını anlık olarak çizen yüksek çözünürlüklü (2048 FFT) dalga analizörü.
* **Dinamik Ses ve Panner Kontrolü (Gain & StereoPanner Nodes):** Her bir frekans kanalı için bağımsız ses seviyesi ve sağ/sol kulaklık dengesi (Binaural Beat yaratmak için) gerçek zamanlı olarak ayarlanabilir.
* **Clipping (Bozulma) Önleme:** Tüm sinyaller, çıkış katmanına ulaşmadan önce bir `DynamicsCompressorNode` üzerinden geçirilerek dijital bozulmalar ve ses patlamaları donanımsal olarak engellenir.
* **Çevrimdışı Yüksek Kalite Render (OfflineAudioContext):** Sistem, çalınan karmaşık sinyal ağını gerçek zamanlı kaydetmek yerine, arkaplanda yüksek hızda işleyerek `lamejs` kütüphanesi ile doğrudan yüksek kaliteli Stereo MP3 formatına kodlar.
* **Katmanlı Ses Tasarımı:** Ana frekansların yoruculuğunu kırmak amacıyla (maskeleme), sisteme harici arka plan müzikleri (doğa sesleri, beyaz gürültü vb.) entegre edilebilir ve frekanslar müziğin içine "gömülebilir".

## Kurulum ve Kullanım

Herhangi bir sunucu kurulumuna veya bağımlılığa (npm, node vb.) ihtiyaç yoktur. Saf (Vanilla) HTML/JS ile yazılmıştır.

1. Depoyu klonlayın: `git clone https://github.com/KULLANICI_ADINIZ/frekans-sentezleyici.git`
2. `index.html` dosyasını herhangi bir modern web tarayıcısında (Chrome, Safari, Edge) açın.
3. Mobil cihazlarla (iOS/Android) tam uyumludur.

## Geliştirici Notu

Otonom sistemler, mobil robotlar (AMR) ve gömülü yazılım alanlarındaki çalışmalarımda sıklıkla karşılaştığım **sensör verisi işleme, frekans analizi ve donanım-yazılım entegrasyonu** süreçlerinin web ortamına (JavaScript tabanlı DSP) uyarlanmış bir versiyonudur. İnsan-makine etkileşiminde, dijital sinyallerin biyolojik sistemler (beyin dalgaları) üzerindeki etkisini pratik bir arayüzle deneyimlemek için geliştirilmiştir.

---
**Geliştirici:** Furkan Karslı | Mekatronik Mühendisi
**İletişim:** [LinkedIn](https://linkedin.com/in/furkankarsli)
