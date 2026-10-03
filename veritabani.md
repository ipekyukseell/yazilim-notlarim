ER Modelinde İlişki Türleri

ER (Entity-Relationship) modelinde ilişki türleri, iki varlık (Entity) arasındaki bağlantının kaç kayıt arasında kurulabileceğini gösterir.

Temel ilişki türleri:

* 1:1 → Birden Bire
* 1:N → Birden Çoğa
* N:1 → Çoktan Bire
* N:M → Çoktan Çoğa

⸻

1. Birden Bire (1:1)

Bir varlığın bir kaydı, diğer varlığın en fazla bir kaydıyla ilişkilidir.

Aynı şekilde diğer varlığın bir kaydı da yalnızca bir kayıtla ilişkilidir.

Örnek: Kişi – Pasaport

KİŞİ                  PASAPORT
  1  ────────────────  1

Bir kişinin bir pasaportu vardır.

Bir pasaport da bir kişiye aittir.

Örnek

Kişi	Pasaport
İpek	P001
Ayşe	P002
Elif	P003

Burada:

* 1 kişi → 1 pasaport
* 1 pasaport → 1 kişi

Kısaca

1:1 = Bir → Bir

⸻

2. Birden Çoğa (1:N)

Bir varlığın bir kaydı, diğer varlığın birden fazla kaydıyla ilişkilidir.

Ancak diğer varlığın bir kaydı yalnızca bir kayıtla ilişkilidir.

Örnek: Bölüm – Öğrenci

BÖLÜM                  ÖĞRENCİ
  1  ─────────────────<  N

Bir bölümde birçok öğrenci bulunabilir.

Ancak bir öğrenci bir bölüme bağlıdır.

Örnek

Bilgisayar Mühendisliği
        ↓
      İpek
      Ayşe
      Elif
      Mehmet

Burada:

* 1 bölüm → birçok öğrenci
* 1 öğrenci → 1 bölüm

Kısaca

1:N = Bir → Çok

⸻

3. Çoktan Bire (N:1)

Çoktan bire ilişkisi, 1:N ilişkisinin ters yönden ifade edilmesidir.

Bir varlığın birçok kaydı, diğer varlığın tek bir kaydıyla ilişkilidir.

Örnek: Öğrenci – Bölüm

ÖĞRENCİ                 BÖLÜM
   N  ─────────────────>  1

Birçok öğrenci aynı bölüme bağlı olabilir.

Örnek

İpek ──┐
Ayşe ──┤
Elif ──┼──→ Bilgisayar Mühendisliği
Mehmet ┘

Burada:

* Çok öğrenci → 1 bölüm
* 1 bölüm → birçok öğrenci

Kısaca

N:1 = Çok → Bir

Önemli

1:N ve N:1 aslında aynı ilişkinin farklı yönlerden ifade edilmesidir.

Örneğin:

BÖLÜM ───────→ ÖĞRENCİ
  1              N

1:N

Aynı ilişkiye öğrenci tarafından bakarsak:

ÖĞRENCİ ───────→ BÖLÜM
   N              1

N:1

⸻

4. Çoktan Çoğa (N:M)

Her iki tarafta da birden fazla kayıt bulunabilir.

Bir A kaydı birçok B kaydıyla ilişkilidir.

Aynı zamanda bir B kaydı da birçok A kaydıyla ilişkilidir.

Örnek: Öğrenci – Ders

ÖĞRENCİ                 DERS
   N  ─────────────────  M

Bir öğrenci birçok ders alabilir.

Bir ders de birçok öğrenci tarafından alınabilir.

Örnek

İpek ─────→ Veri Tabanı
   └──────→ Algoritma
   └──────→ Matematik
Ayşe ─────→ Veri Tabanı
   └──────→ Matematik

Burada:

* 1 öğrenci → birçok ders
* 1 ders → birçok öğrenci

Bu nedenle ilişki:

N:M = Çok → Çok

⸻

5. N:M İlişkisinde Ara Tablo

İlişkisel veritabanlarında N:M ilişkiler doğrudan kurulmaz.

Bunun yerine araya bir ara tablo (junction / associative table) eklenir.

Örneğin:

ÖĞRENCİ Tablosu

OgrenciID	Ad
1	İpek
2	Ayşe

DERS Tablosu

DersID	DersAdi
10	Veri Tabanı
20	Algoritma

ÖĞRENCİ_DERS Tablosu

OgrenciID	DersID
1	10
1	20
2	10

Burada OgrenciID ve DersID, ilgili tablolara bağlanan anahtar alanlardır.

İlişki şu şekilde gösterilebilir:

ÖĞRENCİ
   │
   │ 1:N
   ↓
ÖĞRENCİ_DERS
   ↑
   │ N:1
   │
  DERS

Bu iki ilişki birlikte:

ÖĞRENCİ ↔ DERS
    N       M

şeklinde N:M ilişkisini oluşturur.

⸻

6. İlişki Türlerini Karşılaştırma

İlişki	Anlamı	Örnek
1:1	Bir → Bir	Kişi → Pasaport
1:N	Bir → Çok	Bölüm → Öğrenci
N:1	Çok → Bir	Öğrenci → Bölüm
N:M	Çok → Çok	Öğrenci → Ders

⸻

7. İlişki Türünü Nasıl Buluruz?

Bir ilişki sorusunda kendimize iki soru sorabiliriz:

Soru 1

A’dan bir tane, B’den kaç tane olabilir?

Soru 2

B’den bir tane, A’dan kaç tane olabilir?

⸻

Örnek 1: Bölüm – Öğrenci

Bir bölümde kaç öğrenci olabilir?

→ Çok

Bir öğrenci kaç bölüme bağlıdır?

→ Bir

Sonuç:

BÖLÜM → ÖĞRENCİ
  1        N

1:N

⸻

Örnek 2: Öğrenci – Ders

Bir öğrenci kaç ders alabilir?

→ Çok

Bir ders kaç öğrenci tarafından alınabilir?

→ Çok

Sonuç:

ÖĞRENCİ → DERS
   N        M

N:M

⸻

Örnek 3: Kişi – Pasaport

Bir kişinin kaç pasaportu olabilir?

→ Bir

Bir pasaport kaç kişiye aittir?

→ Bir

Sonuç:

KİŞİ → PASAPORT
  1       1

1:1

⸻

8. Kolay Ezberleme

1 : 1  → Bir - Bir
1 : N  → Bir - Çok
N : 1  → Çok - Bir
N : M  → Çok - Çok

Burada:

* 1 = Bir
* N = Çok
* M = Çok

Dolayısıyla:

1:N → Bir tarafta bir, diğer tarafta çok

N:1 → Bir tarafta çok, diğer tarafta bir

N:M → İki tarafta da çok

⸻

9. Sınav İçin Kısa Özet

İlişki	Açıklama
1:1	Bir kayıt, yalnızca bir kayıtla ilişkilidir.
1:N	Bir kayıt, birçok kayıtla ilişkilidir.
N:1	Birçok kayıt, tek bir kayıtla ilişkilidir.
N:M	Birçok kayıt, birçok kayıtla ilişkilidir.
N:M’de	Genellikle ara tablo kullanılır.

En önemli örnekler

Kişi ─── Pasaport
 1          1
→ 1:1
Bölüm ─── Öğrenci
 1           N
→ 1:N
Öğrenci ─── Bölüm
    N          1
→ N:1
Öğrenci ─── Ders
    N          M
→ N:M

⭐ Akılda Tut

1:1 → Bir-Bir

1:N → Bir-Çok

N:1 → Çok-Bir

N:M → Çok-Çok