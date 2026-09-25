# 7) Algoritma ve Veri Yapıları Mantığı

## 1. Veri Yapısı Nedir?

**Veri yapısı**, verilerin bilgisayar belleğinde düzenli ve verimli bir şekilde saklanmasını, erişilmesini ve işlenmesini sağlayan yapılardır.

Bir programda doğru veri yapısını seçmek:

- Verilere daha hızlı erişmemizi sağlar.
- Arama, ekleme ve silme işlemlerini daha verimli hale getirir.
- Belleğin daha verimli kullanılmasına yardımcı olur.
- Büyük veri kümeleriyle çalışmayı kolaylaştırır.
- Programın performansını artırabilir.

### Mülakat Sorusu

**Soru:** Veri yapılarına neden ihtiyaç duyarız?

**Cevap:** Verileri ihtiyaca uygun şekilde organize ederek erişim, arama, ekleme ve silme işlemlerini daha verimli gerçekleştirmek için veri yapılarını kullanırız.

---

# 2. Big-O Mantığı

**Big-O**, bir algoritmanın giriş verisi büyüdükçe çalışma süresinin veya kullandığı kaynakların nasıl değiştiğini ifade eder.

Örneğin:

```python
for player in players:
    print(player)
```

Listedeki bütün oyuncular bir kez kontrol edildiği için bu algoritmanın zaman karmaşıklığı:

**O(n)**

olur.

## En Sık Kullanılan Big-O Değerleri

| Big-O | Açıklama | Örnek |
|---|---|---|
| **O(1)** | Sabit zaman | Array index erişimi |
| **O(log n)** | Logaritmik | Binary Search |
| **O(n)** | Doğrusal | Linear Search |
| **O(n log n)** | Doğrusal-logaritmik | Merge Sort |
| **O(n²)** | Karesel | Bubble Sort |
| **O(2ⁿ)** | Üstel | Bazı recursive algoritmalar |

### Mülakat Sorusu

**Soru:** O(1), O(n)'den neden daha verimlidir?

**Cevap:** O(1)'de işlem sayısı veri miktarından bağımsızdır. O(n)'de ise veri miktarı arttıkça işlem sayısı da artar.

---

# 3. Array (Dizi)

**Array**, verileri sıralı bir şekilde saklayan temel veri yapılarından biridir.

Örneğin:

```python
players = ["Messi", "Ronaldo", "Mbappe"]
```

Elemanların indeksleri:

```text
0 → Messi
1 → Ronaldo
2 → Mbappe
```

şeklindedir.

## Avantajları

- Index üzerinden hızlı erişim sağlar.
- Belirli bir elemana doğrudan ulaşılabilir.
- Kullanımı basittir.

Örneğin:

```python
players[1]
```

işlemi doğrudan ikinci elemana erişir.

Bu işlem genellikle:

**O(1)**

karmaşıklığındadır.

## Dezavantajları

- Araya eleman eklemek maliyetli olabilir.
- Eleman silme işlemi sırasında diğer elemanların yer değiştirmesi gerekebilir.
- Dinamik olmayan array yapılarında boyut problemi yaşanabilir.

### Mülakat Sorusu

**Soru:** Array'de index üzerinden elemana erişmenin Big-O değeri nedir?

**Cevap:** **O(1)**

---

# 4. Linked List

**Linked List**, elemanların birbirine bağlantılar üzerinden bağlandığı veri yapısıdır.

Her node genellikle:

- Veriyi
- Bir sonraki node'a ait referansı

tutar.

Örneğin:

```text
[10] → [20] → [30] → [40]
```

Burada her node bir sonraki node'u gösterir.

## Avantajları

- Dinamik olarak büyüyebilir.
- Uygun konum biliniyorsa ekleme ve silme işlemleri verimli olabilir.
- Elemanların bellekte arka arkaya bulunması gerekmez.

## Dezavantajları

- Rastgele erişim yoktur.
- Belirli bir elemana ulaşmak için listenin başından ilerlemek gerekebilir.
- Her node bağlantı bilgisi de tuttuğu için ekstra bellek kullanabilir.

Linked List'te belirli bir elemana erişim genellikle:

**O(n)**

olur.

### Mülakat Sorusu

**Soru:** Array ve Linked List arasındaki temel fark nedir?

**Cevap:** Array'de index üzerinden hızlı erişim mümkündür. Linked List'te ise elemanlara bağlantılar üzerinden ulaşılır ve belirli bir elemana erişmek için liste üzerinde ilerlemek gerekir.

---

# 5. Stack

**Stack**, LIFO mantığıyla çalışan bir veri yapısıdır.

**LIFO = Last In, First Out**

Yani:

> **Son giren, ilk çıkar.**

Tabak örneğiyle düşünebiliriz:

```text
┌─────┐
│  30 │ ← İlk çıkar
├─────┤
│  20 │
├─────┤
│  10 │ ← İlk giren
└─────┘
```

## Temel İşlemler

### Push

Stack'e eleman ekler.

```python
stack.append(10)
```

### Pop

Stack'in en üstündeki elemanı çıkarır.

```python
stack.pop()
```

### Peek

En üstteki elemana bakar fakat çıkarmaz.

## Kullanım Alanları

- Undo / Redo işlemleri
- Fonksiyon çağrıları
- Parantez kontrolü
- DFS algoritması
- Expression evaluation

### Mülakat Sorusu

**Soru:** Stack hangi mantıkla çalışır?

**Cevap:** **LIFO (Last In, First Out)** mantığıyla çalışır.

---

# 6. Queue

**Queue**, FIFO mantığıyla çalışan veri yapısıdır.

**FIFO = First In, First Out**

Yani:

> **İlk giren, ilk çıkar.**

Market kuyruğu buna güzel bir örnektir.

```text
10 → 20 → 30 → 40
↑
İlk çıkar
```

## Temel İşlemler

- **Enqueue:** Eleman ekleme
- **Dequeue:** Eleman çıkarma

## Kullanım Alanları

- İşlem kuyrukları
- Yazıcı sistemleri
- İşletim sistemi süreçleri
- Network işlemleri
- BFS algoritması

### Mülakat Sorusu

**Soru:** Queue hangi mantıkla çalışır?

**Cevap:** **FIFO (First In, First Out)** mantığıyla çalışır.

---

# 7. Stack ve Queue Farkı

| Özellik | Stack | Queue |
|---|---|---|
| Mantık | LIFO | FIFO |
| Açılım | Last In First Out | First In First Out |
| İlk çıkan | Son giren | İlk giren |
| Örnek | Tabak yığını | Market kuyruğu |
| Kullanım | DFS | BFS |

### Mülakat Sorusu

**Soru:** Stack ile Queue arasındaki temel fark nedir?

**Cevap:** Stack LIFO mantığıyla, Queue ise FIFO mantığıyla çalışır.

---

# 8. HashMap

**HashMap**, verileri **key-value** şeklinde saklayan veri yapısıdır.

Python'da bunun en yaygın karşılığı:

```python
dict
```

Örneğin:

```python
player = {
    "name": "Mbappe",
    "age": 25,
    "overall": 91
}
```

Burada:

```text
Key       Value
----------------
name      Mbappe
age       25
overall   91
```

şeklinde tutulur.

Key kullanarak değere ulaşabiliriz:

```python
player["overall"]
```

Sonuç:

```text
91
```

HashMap'te arama, ekleme ve silme işlemleri uygun koşullarda **ortalama O(1)** olabilir.

> Not: En kötü durumda hash çakışmaları nedeniyle karmaşıklık değişebilir.

### Mülakat Sorusu

**Soru:** HashMap neden hızlıdır?

**Cevap:** Key değerinin bir hash fonksiyonu aracılığıyla uygun konuma eşlenmesi sayesinde arama, ekleme ve silme işlemleri ortalama olarak O(1) zamanda gerçekleştirilebilir.

---

# 9. Linear Search

**Linear Search**, verileri baştan sona tek tek kontrol ederek arama yapar.

Örneğin:

```text
10 → 20 → 30 → 40 → 50
              ↑
            Aranan
```

Algoritma:

1. İlk elemana bakar.
2. Aranan değer değilse sonraki elemana geçer.
3. Aranan değeri bulana kadar devam eder.

En kötü durumda bütün elemanların kontrol edilmesi gerekir.

Bu nedenle:

**O(n)**

karmaşıklığındadır.

### Mülakat Sorusu

**Soru:** Linear Search'ün zaman karmaşıklığı nedir?

**Cevap:** En kötü durumda **O(n)**.

---

# 10. Binary Search

**Binary Search**, sıralanmış bir veri üzerinde çalışan arama algoritmasıdır.

Örneğin:

```text
10 20 30 40 50 60 70
```

Aranan değer için ortadaki elemana bakılır.

Aranan değer ortadaki değerden küçükse sol tarafa, büyükse sağ tarafa geçilir.

Her adımda arama alanı yaklaşık olarak ikiye bölünür.

Bu nedenle zaman karmaşıklığı:

**O(log n)**

olur.

## Çok Önemli

Binary Search kullanabilmek için veri genellikle:

> **Sıralanmış olmalıdır.**

### Mülakat Sorusu

**Soru:** Binary Search'ün çalışması için temel şart nedir?

**Cevap:** Arama yapılacak verinin sıralanmış olması gerekir.

---

# 11. Bubble Sort

**Bubble Sort**, yan yana bulunan elemanları karşılaştırarak sıralama yapan basit bir algoritmadır.

Örneğin:

```text
50 20 40 10
```

Yan yana elemanlar karşılaştırılır ve büyük olan sağ tarafa taşınır.

## Karmaşıklığı

Ortalama ve en kötü durumda:

**O(n²)**

olabilir.

## Avantajı

- Öğrenmesi kolaydır.
- Uygulaması basittir.

## Dezavantajı

- Büyük veri kümelerinde yavaştır.
- Daha verimli sıralama algoritmaları vardır.

### Mülakat Sorusu

**Soru:** Bubble Sort'un zaman karmaşıklığı nedir?

**Cevap:** Ortalama ve en kötü durumda **O(n²)**.

---

# 12. Selection Sort

Selection Sort, her adımda sıralanmamış bölümdeki en küçük veya en büyük elemanı bulup doğru konuma yerleştirir.

Örneğin:

```text
50 20 40 10
```

İlk olarak en küçük değer bulunur:

```text
10
```

ve başa alınır.

Sonra kalan bölüm için aynı işlem devam eder.

## Karmaşıklığı

Genellikle:

**O(n²)**

olur.

### Mülakat Sorusu

**Soru:** Selection Sort'un temel çalışma mantığı nedir?

**Cevap:** Her adımda sıralanmamış bölümdeki minimum veya maksimum elemanı bulup doğru konuma yerleştirmektir.

---

# 13. Insertion Sort

Insertion Sort, elemanları tek tek alıp daha önce sıralanmış bölüm içerisindeki doğru konuma yerleştirir.

Örneğin:

```text
5 3 8 2
```

İlk eleman sıralı kabul edilir.

Sonraki eleman doğru konuma yerleştirilir:

```text
3 5
```

Daha sonra diğer elemanlar eklenir.

## Karmaşıklığı

Ortalama ve en kötü durumda:

**O(n²)**

olabilir.

Ancak veri büyük ölçüde sıralıysa oldukça verimli olabilir.

---

# 14. Merge Sort

Merge Sort, **Divide and Conquer** yaklaşımını kullanır.

Yani problemi küçük parçalara böler ve daha sonra bu parçaları birleştirir.

Örneğin:

```text
[8, 3, 5, 2]
```

Önce:

```text
[8, 3] [5, 2]
```

Sonra:

```text
[8] [3] [5] [2]
```

Daha sonra sıralı şekilde birleştirilir.

Sonuç:

```text
[2, 3, 5, 8]
```

## Zaman Karmaşıklığı

```text
O(n log n)
```

### Mülakat Sorusu

**Soru:** Merge Sort neden büyük veri kümelerinde Bubble Sort'a göre daha verimlidir?

**Cevap:** Merge Sort'un zaman karmaşıklığı O(n log n), Bubble Sort'un ise O(n²)'dir. Veri büyüdükçe aradaki performans farkı önemli hale gelir.

---

# 15. Divide and Conquer

**Divide and Conquer**, büyük bir problemi daha küçük problemlere bölme yaklaşımıdır.

Üç temel aşaması vardır:

1. **Divide** → Problemi parçalara böl.
2. **Conquer** → Küçük problemleri çöz.
3. **Combine** → Sonuçları birleştir.

Merge Sort bunun klasik örneklerinden biridir.

---

# 16. Recursion

**Recursion**, bir fonksiyonun kendisini tekrar çağırmasıdır.

Örneğin:

```python
def countdown(n):

    if n == 0:
        return

    print(n)

    countdown(n - 1)
```

Burada fonksiyon kendisini tekrar çağırmaktadır.

Recursion kullanırken mutlaka bir:

**Base Case**

bulunmalıdır.

Aksi halde fonksiyon sürekli kendisini çağırabilir.

### Mülakat Sorusu

**Soru:** Recursive fonksiyonda neden Base Case gerekir?

**Cevap:** Recursive çağrıların ne zaman duracağını belirlemek için gerekir.

---

# 17. DFS ve BFS

Graf ve ağaç problemlerinde sık kullanılan iki temel algoritmadır.

## DFS

**Depth First Search**

Öncelikle mümkün olduğu kadar derine gider.

Genellikle:

- Stack
- Recursion

kullanılabilir.

## BFS

**Breadth First Search**

Önce aynı seviyedeki düğümleri ziyaret eder.

Genellikle:

- Queue

kullanılır.

### Mülakat Sorusu

**Soru:** DFS ve BFS arasındaki temel fark nedir?

**Cevap:** DFS derinlemesine ilerler ve stack/recursion kullanabilir. BFS ise seviyeleri sırayla gezer ve queue kullanır.

---

# 18. Zaman ve Bellek Karmaşıklığı

Bir algoritmayı değerlendirirken sadece çalışma süresine değil, kullandığı belleğe de bakılır.

## Time Complexity

Algoritmanın ne kadar işlem yaptığını ifade eder.

Örneğin:

```text
O(n)
```

## Space Complexity

Algoritmanın kullandığı ek belleği ifade eder.

### Mülakat Sorusu

**Soru:** Time Complexity ile Space Complexity arasındaki fark nedir?

**Cevap:** Time Complexity algoritmanın çalışma maliyetini, Space Complexity ise algoritmanın kullandığı bellek miktarını ifade eder.

---

# 19. Mülakatlarda Çok Sorulan Sorular

### 1. Array'de index erişimi kaçtır?

**O(1)**

### 2. Linear Search kaçtır?

**O(n)**

### 3. Binary Search kaçtır?

**O(log n)**

### 4. Binary Search için temel şart nedir?

**Verinin sıralı olması.**

### 5. Stack hangi mantıkla çalışır?

**LIFO**

### 6. Queue hangi mantıkla çalışır?

**FIFO**

### 7. HashMap'in ortalama arama karmaşıklığı nedir?

**O(1)**

### 8. Bubble Sort kaçtır?

**O(n²)**

### 9. Merge Sort kaçtır?

**O(n log n)**

### 10. DFS hangi veri yapısını kullanabilir?

**Stack veya Recursion**

### 11. BFS hangi veri yapısını kullanır?

**Queue**

### 12. Recursion neden Base Case'e ihtiyaç duyar?

**Fonksiyonun ne zaman duracağını belirlemek için.**

---

# 20. Kısa Özet

```text
Array
→ Index erişimi
→ O(1)

Linked List
→ Node + bağlantı
→ Erişim O(n)

Stack
→ LIFO
→ Push / Pop

Queue
→ FIFO
→ Enqueue / Dequeue

HashMap
→ Key - Value
→ Ortalama O(1)

Linear Search
→ O(n)

Binary Search
→ O(log n)
→ Sıralı veri gerekir

Bubble Sort
→ O(n²)

Selection Sort
→ O(n²)

Insertion Sort
→ Ortalama O(n²)

Merge Sort
→ O(n log n)

DFS
→ Stack / Recursion

BFS
→ Queue
```

# 🎯 Mülakat İçin En Önemli Nokta

Bir veri yapısının sadece **tanımını ezberlemek yerine**, şu üç soruya cevap verebilmek önemlidir:

1. **Nasıl çalışıyor?**
2. **Hangi durumda kullanılır?**
3. **Zaman ve bellek karmaşıklığı nedir?**

Örneğin:

> **"Neden Array yerine HashMap kullandın?"**

sorusuna sadece "HashMap key-value tutar" demek yerine:

> "Veriye belirli bir key üzerinden hızlı şekilde ulaşmam gerekiyorsa HashMap tercih ederim. Uygun koşullarda arama işlemi ortalama O(1) olduğu için büyük veri kümelerinde avantaj sağlayabilir."

şeklinde açıklama yapmak daha güçlü bir mülakat cevabıdır.