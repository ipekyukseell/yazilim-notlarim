Ağ Temelleri (Networking)

1. IP Nedir?

IP (Internet Protocol), cihazların ağ üzerinde birbirini tanımasını sağlayan adres bilgisidir. Cihazların birbirleriyle iletişim kurmasını sağlar.

2. Port Nedir?

Port, bir cihazdaki uygulama ve servislerin iletişim kurduğu sanal kapılardır.

Örnek:

* HTTP → 80
* HTTPS → 443

3. DNS Nedir?

DNS (Domain Name System), alan adlarını IP adreslerine çevirir.

Örneğin google.com yazdığımızda DNS, bu alan adının hangi IP adresine ait olduğunu bulur.

4. TCP Nedir?

TCP (Transmission Control Protocol), verilerin güvenilir ve sıralı bir şekilde gönderilmesini sağlar. Veri kaybolursa tekrar gönderilmesini sağlar.

5. UDP Nedir?

UDP (User Datagram Protocol), verileri hızlı bir şekilde gönderir ancak verilerin kesin olarak ulaştığını garanti etmez. Hızın önemli olduğu durumlarda kullanılır.

6. Paket Yapısı Nasıl Çalışır?

İnternette gönderilen veriler tek parça halinde değil, paketler halinde gönderilir.

1. Veri küçük parçalara ayrılır.
2. Paketlere gerekli ağ bilgileri eklenir.
3. Paketler ağ üzerinden gönderilir.
4. Hedef cihaz paketleri alır.
5. Paketler birleştirilerek veri tekrar oluşturulur.

7. Ping Ne İşe Yarar?

Ping, bir cihazın veya sunucunun erişilebilir olup olmadığını kontrol etmek için kullanılır. Ayrıca bağlantının yanıt süresini ölçmeye yardımcı olur.

ping google.com

8. Traceroute Ne İşe Yarar?

Traceroute, bilgisayarımızdan hedef sunucuya giderken verilerin geçtiği ağ cihazlarını ve izlediği yolu göstermeye yarar.

Windows’ta:

tracert google.com

9. Nslookup Ne İşe Yarar?

Nslookup, DNS sorgulaması yapmak için kullanılır. Bir alan adının hangi IP adresine karşılık geldiğini öğrenmemizi sağlar.

nslookup google.com

