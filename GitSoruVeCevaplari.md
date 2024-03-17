# Cevaplar - Git

- Git Nedir?
    Git versiyon kontrol sistemi, yazılım geliştirme süreçlerinde kullanılan dağıtık bir versiyon kontrol sistemidir. Geliştiricilere proje dosyalarının geçmişini takip etme, değişiklikleri yönetme, işbirliği yapma ve kodu izleme imkanı sağlar.

- "git pull" ile "git fetch" komutlarının farkı nedir?
    "git pull" komutu, uzak depodan değişiklikleri alır ve bunları yerel depoya indirirken aynı zamanda mevcut dalı (branch) günceller. "git fetch" komutu ise uzak depodaki değişiklikleri sadece yerel depoya indirir ancak mevcut dala otomatik olarak entegre etmez.

- Eğer takım arkadaşımız "kodlarımı gönderdim, benim geliştirmemin üzerine devam et" derse ve gönderdiği kodları "git pull" ile lokalimize alamıyorsak nerelerde hata yapılmış olabilir?
    * **Çakışan değişiklikler**: Bu bağlamda en sık karşılaşılan sorunların başında gelir. Eğer kişi lokal çalışma ortamında bir değişiklik yaptıysa, git pull komutu çalıştırılamaz.
    * **Yetki sorunu**: Kişi uzak sunucuya bağlanmada yetki kısıtlamasıyla karşı karşıya olabilir.
    * **Yanlış dala yollamak:** Geliştirici kodu yanlış daha göndermiş olabilir. Bu durumda gönderilen dalın da açık bir şekilde belirtilmesi faydalı olur.

- "git fetch origin" komutundaki "origin" neye karşılık gelmektedir?
    "origin" uzak bir Git deposunun bir takma adıdır. Geleneksel olarak ilk depo adını böyle versek de, farklı isimler de verebiliriz. Özellikle birden fazla uzak deposu bulunan projelerde kullanımı faydalıdır.

- "HEAD" kelimesi neyi temsil etmektedir?
    "HEAD" kelimesi, Git deposundaki mevcut işlem yapıldığı konumu temsil eder. Daha spesifik olarak, "HEAD" genellikle şu anki çalışma daldaki en son taahhütü işaret eder. Bu, kullanıcının çalıştığı dalı ve bu dalın son durumunu gösterir.

- "Staging Area" ya da "Index" diye isimlendirilen bölge tam olarak ne demektir?
    Staging Area, Git deposunda değişikliklerin hazırlandığı ve sonraki bir taahhüde dahil edilmek üzere bekletildiği bir ara alanı temsil eder. Bu bölge, değişikliklerin taahhütlere eklenmeden önce düzenlenmesine ve kontrol edilmesine olanak tanır.  

- "Untracked file" ne demektir?
    İzlenmeyen dosya, henüz ara bölgeye (staging area) alınmamış dosyalardır. Git, bu dosyanın değişikliklerini izlemeyecek veya kaydetmeyecek ve bu dosya hakkında herhangi bir bilgi saklamayacaktır. 

- ".git" klasörünü silersek ne olur?
    Bu klasörü silersek proje ile ilgili lokalde tuttuğumuz git ile ilgili tüm değişiklikler, tarih ve takip bilgisi silinir.

- Kendi lokalimizde her "git init" komutunu kullanıdığımızda otomatik olarak "ReadMe.md" dosyası oluşturulmasını istiyorsak ne yapmalıyız?
    Bunun için Git şablonunu (template) kullanabiliriz. Şu adımları izleyebiliriz:
    1. Lokal çalışma ortamında bir "ReadMe.md" dosyası oluştururuz. Bu bizim için yeni depo oluştururken bir şablon görevi görecek.
    2. Git şablonunun adresini git config ile şu şekilde kaydedelim (/path/to/your/template/directory yerine ReadMe.md oluşturduğumuz adresi vereceğiz):
    ```
        git config --global init.templateDir /path/to/your/template/directory
    ```
    3. "git init" komutu ile depo oluşturabiliriz. Bu durumda "ReadMe.md" bizim için otomatik olarak oluşturulacaktır.

- Git konusunda bahsi geçen "branch" yapısı nedir? Bize ne sağlar?
    

- Sıfırdan bir "branch" nasıl oluşturabiliriz?
- Var olan bir "branch"e nasıl geçebiliriz?
- "git clone" komutunu kullanırken belirli bir spesifik branch'i sadece çekmek istiyorsak nasıl yapabiliriz?
- "Merge conflict" ne demektir?
- "git log" komutu ile hangi bilgileri görebiliriz?
- "git diff" ile kaç farklı iki durumun arasındaki değişiklikleri görebiliriz?
- Git reset ile neyi geri alıyoruz?
- "git commit" ile "git push" arasındaki fark nedir?
- Atomic commit ne demektir?
- Repository ne demektir?
- "git tag" nedir? "git branch"’ten farkı nedir?
- Git'i görsel olarak kullanabilmek için hangi üçüncü taraf araçları ve uygulamaları kullanabiliriz?
- "GitHub" ile "git" arasındaki fark nedir? GitHub benzeri diğer siteler nelerdir? GitHub veya diğer sitelerdeki kullanıcı adlarını yazar mısınız?
- main ya da master branch'inin diğer branchlerden farkı nedir?
- ".gitignore" dosyası nedir ve ne amaçla kullanılır? - (Teşekkürler @madenyasin)
- "git push origin --delete branch_name” nedir ve ne için kullanılır?