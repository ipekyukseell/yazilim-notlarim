

NTFS – ext4 – APFS Farkları

NTFS

NTFS (New Technology File System), Windows işletim sistemlerinde kullanılan temel dosya sistemidir. Dosya ve klasör izinleri, güvenlik özellikleri ve büyük dosyalarla çalışma konusunda gelişmiştir.

* Windows sistemlerinde yaygın olarak kullanılır.
* Dosya ve klasör izinlerini destekler.
* Büyük dosya ve diskleri destekler.
* Günlükleme (journaling) özelliği sayesinde sistem hatalarından sonra veri bütünlüğünü korumaya yardımcı olur.

ext4

ext4 (Fourth Extended Filesystem), Linux işletim sistemlerinde yaygın olarak kullanılan bir dosya sistemidir.

* Linux sistemlerinde yaygın olarak kullanılır.
* Büyük disk ve dosyaları destekler.
* Günlükleme (journaling) özelliğine sahiptir.
* Performans ve güvenilirlik açısından Linux sistemleri için uygundur.

APFS

APFS (Apple File System), Apple tarafından geliştirilen ve macOS, iOS gibi Apple işletim sistemlerinde kullanılan modern dosya sistemidir.

* Apple cihazlarında kullanılır.
* SSD ve flash depolama için optimize edilmiştir.
* Dosya ve klasör yönetiminde modern özellikler sunar.
* Şifreleme ve veri güvenliği özelliklerini destekler.

Kısaca Karşılaştırma

Dosya Sistemi	Kullanıldığı Sistem	Öne Çıkan Özellik
NTFS	Windows	Güvenlik ve izinler
ext4	Linux	Performans ve güvenilirlik
APFS	Apple	SSD/flash optimizasyonu ve güvenlik

⸻

Blok Yapısı Nedir?

Blok, depolama aygıtında verilerin saklandığı temel birimlerden biridir. Dosyalar diske doğrudan tek parça olarak değil, birden fazla blok içerisinde kaydedilebilir.

Örneğin bir dosya 3 blok yer kaplıyorsa, dosyanın verileri diskin farklı bölgelerindeki 3 ayrı blokta tutulabilir.

Dosya sisteminin görevi, hangi dosyanın hangi bloklarda bulunduğunu takip etmektir.

Kısaca:

Blok = Verilerin diskte saklandığı temel depolama birimi.

⸻

HDD vs SSD Çalışma Prensipleri

HDD

HDD (Hard Disk Drive), verileri manyetik diskler üzerinde saklar. İçerisinde dönen plakalar ve bu plakalar üzerindeki verileri okuyan/yazan mekanik bir kafa bulunur.

Veriye ulaşmak için mekanik parçaların hareket etmesi gerektiğinden SSD’lere göre daha yavaştır.

Avantajları:

* Genellikle daha düşük maliyetlidir.
* Büyük depolama kapasiteleri sunabilir.

Dezavantajları:

* Mekanik parçalar içerir.
* Darbelere karşı daha hassastır.
* Okuma/yazma hızı SSD’lere göre daha düşüktür.

SSD

SSD (Solid State Drive), verileri flash bellek üzerinde saklar. Mekanik hareketli parçalar içermez.

Bu nedenle verilere erişim süresi HDD’ye göre çok daha düşüktür ve genel olarak daha hızlı çalışır.

Avantajları:

* Daha hızlı okuma/yazma performansı sunar.
* Mekanik parça içermez.
* Darbelere karşı HDD’ye göre daha dayanıklıdır.
* Daha sessiz çalışır.

Dezavantajları:

* Aynı kapasite için HDD’ye göre genellikle daha pahalıdır.
* Flash bellek hücrelerinin sınırlı yazma ömrü vardır.

⸻



Örneğin:

HDD → Mekanik hareket → Daha uzun erişim süresi

SSD → Elektronik erişim → Daha kısa erişim süresi → Daha hızlı çalışma