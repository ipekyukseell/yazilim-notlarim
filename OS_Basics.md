# 3. RAPOR

## İşletim Sistemi Temelleri (OS Basics)

### Kernel Nedir?

Kernel (çekirdek), işletim sisteminin en önemli bileşenidir. Donanım ile yazılımlar arasında köprü görevi görür. Programların işlemci, bellek, disk ve diğer donanımlara güvenli bir şekilde erişmesini sağlar. Uygulamalar donanıma doğrudan erişemez; tüm işlemler kernel üzerinden gerçekleştirilir.

**Kernel'in Görevleri:**
- İşlemciyi (CPU) yönetmek.
- Belleği (RAM) yönetmek.
- Dosya sistemini kontrol etmek.
- Donanım aygıtlarıyla iletişim kurmak.
- Programlar arasında güvenliği sağlamak.

---

### Süreç (Process) – İş Parçacığı (Thread) Farkı

**Process (Süreç)**, çalışan bir programın bellekteki halidir. Her process kendine ait bellek alanına sahiptir ve diğer süreçlerden bağımsız çalışır.

**Thread (İş Parçacığı)** ise bir process içerisinde çalışan en küçük yürütme birimidir. Aynı process içindeki thread'ler aynı bellek alanını paylaşırlar.

| Process | Thread |
|---------|--------|
| Kendi belleğine sahiptir. | Belleği ortak kullanır. |
| Daha fazla kaynak tüketir. | Daha az kaynak tüketir. |
| Oluşturulması daha yavaştır. | Oluşturulması daha hızlıdır. |
| Bağımsız çalışır. | Process'e bağlı çalışır. |

---

### Bellek Yönetimi Nasıl Yapılır?

Bellek yönetimi, işletim sisteminin RAM'i çalışan programlar arasında verimli ve güvenli şekilde paylaştırmasıdır.

**İşletim sisteminin yaptığı işlemler:**
- Programlara ihtiyaç duydukları kadar bellek ayırır.
- Kullanılmayan belleği geri kazanır.
- Programların birbirlerinin belleğine erişmesini engeller.
- Gerektiğinde sanal bellek (Virtual Memory) kullanır.

**Sanal Bellek (Virtual Memory)**

RAM yetersiz kaldığında işletim sistemi diskin belirli bir bölümünü geçici bellek olarak kullanır. Bu yöntem sayesinde daha fazla uygulama çalıştırılabilir ancak RAM'e göre daha yavaş olduğu için performans düşebilir.

---

### CPU Zamanlayıcıları Nedir?

CPU zamanlayıcısı, işlemcinin hangi sürece ne kadar süre ayrılacağını belirleyen işletim sistemi bileşenidir.

**Yaygın CPU Zamanlama Algoritmaları**

#### FCFS (First Come First Serve)

İlk gelen süreç ilk çalıştırılır.

#### SJF (Shortest Job First)

Çalışma süresi en kısa olan süreç önce çalıştırılır.

#### Round Robin (RR)

Her sürece belirli bir zaman dilimi verilir. Süresi dolan süreç sıranın sonuna geçer.

#### Priority Scheduling

Öncelik değeri yüksek olan süreç önce çalıştırılır.

---

