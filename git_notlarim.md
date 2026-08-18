# Git ve GitHub Notları

## Git
- Bir **versiyon kontrol sistemidir.**
- Projedeki yapılan değişiklikleri takip eder.
- Eski sürümlere geri dönmeyi sağlar.
- Ekip çalışmalarını kolaylaştırır.

---

## GitHub
- Git projelerini internet üzerinde saklamaya yarayan bir **web platformudur.**
- Kodlarımızı yedeklememizi sağlar.
- Projelerimizi başkalarıyla paylaşabiliriz.
- Git ile oluşturulan repository'ler GitHub'a yüklenebilir.

---

## Commit
- Yapılan değişiklikleri **kaydetme işlemidir.**
- Projenin belirli bir andaki durumunu kayıt altına alır.
- Her commit bir açıklama (mesaj) ile birlikte oluşturulur.

---

## Branch
- **Dallanma** anlamına gelir.
- Ana projeyi etkilemeden yeni özellikler geliştirmek için kullanılır.
- Denemeler yapmak ve farklı çalışmalar yürütmek için ayrı bir çalışma alanı oluşturur.

---

## Repository (Repo)
- Git projesinin bulunduğu **klasördür.**
- Projeye ait dosyalar ve Git geçmişi burada saklanır.
- Her proje için ayrı bir repository oluşturulabilir.

---

## Kısa Özet

- **Git** → Versiyon kontrol sistemi.
- **GitHub** → Git projelerini internet üzerinde saklayan platform.
- **Commit** → Yapılan değişiklikleri kaydetme işlemi.
- **Branch** → Ana projeden bağımsız çalışma dalı.
- **Repository (Repo)** → Git projesinin bulunduğu klasör.
# Git Temel Komutlar

- `git status`: Git'in güncel durumunu gösterir.
- `git init`: Git'i başlatır.
- `git commit`: Seçtiklerini Git geçmişine kaydeder ve geçmişe yeni bir kayıt ekler.
- `git log`: Geçmişteki kayıtları gösterir.
- `.gitignore`: Git'in takip etmesini veya commit'e dahil etmesini istemediğimiz dosya ve klasörleri belirtmek için kullanılır.

# Git Komutları ve Kavramları

## HEAD
Hem commit olarak hem de güncel olarak konumumuzu gösterir.  
Şu anda nerede olduğumuzu gösterir.

## Merge
Birleştirmek anlamına gelir.  
Bir branch'taki yapılan değişiklikleri başka bir branch ile birleştirmek için kullanılır.

## Fast Forward
`git merge` sırasında yapılan en basit birleştirme şeklidir.  
Eğer iki branch arasında doğrudan birleştirme yapılabiliyorsa Git, **Fast Forward** yöntemiyle birleştirir.

## Merge Conflict
İki branch'te aynı bölüm üzerinde farklı değişiklikler yapıldığında, Git'in hangi değişikliği kullanacağına karar verememesi sonucu oluşan **çakışmadır**.

## Stash
Değişiklikleri geçici olarak saklamak/depolamak için kullanılır.  
Git bu değişiklikleri kendi içinde saklar ve istediğimiz zaman geri getirebiliriz.

## Master
Ana branch'tir.

## Branch
Ana projeden ayrılmış bir çalışma koludur.  
Yeni bir şey denemek istediğimizde yeni bir branch açabiliriz.

## Git Switch
Branch'ler arasında geçiş yapmak için kullanılır.

Örnek:
```bash
git switch branch_adi
