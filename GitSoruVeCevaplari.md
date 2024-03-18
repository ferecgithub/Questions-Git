# Cevaplar - Git

1. Git Nedir?
    Git versiyon kontrol sistemi, yazılım geliştirme süreçlerinde kullanılan dağıtık bir versiyon kontrol sistemidir. Geliştiricilere proje dosyalarının geçmişini takip etme, değişiklikleri yönetme, işbirliği yapma ve kodu izleme imkanı sağlar.

2. "git pull" ile "git fetch" komutlarının farkı nedir?
    "git pull" komutu, uzak depodan değişiklikleri alır ve bunları yerel depoya indirirken aynı zamanda mevcut dalı (branch) günceller. "git fetch" komutu ise uzak depodaki değişiklikleri sadece yerel depoya indirir ancak mevcut dala otomatik olarak entegre etmez.

3. Eğer takım arkadaşımız "kodlarımı gönderdim, benim geliştirmemin üzerine devam et" derse ve gönderdiği kodları "git pull" ile lokalimize alamıyorsak nerelerde hata yapılmış olabilir?
    * **Çakışan değişiklikler**: Bu bağlamda en sık karşılaşılan sorunların başında gelir. Eğer kişi lokal çalışma ortamında bir değişiklik yaptıysa, git pull komutu çalıştırılamaz.
    * **Yetki sorunu**: Kişi uzak sunucuya bağlanmada yetki kısıtlamasıyla karşı karşıya olabilir.
    * **Yanlış dala yollamak:** Geliştirici kodu yanlış daha göndermiş olabilir. Bu durumda gönderilen dalın da açık bir şekilde belirtilmesi faydalı olur.

4. "git fetch origin" komutundaki "origin" neye karşılık gelmektedir?
    "origin" uzak bir Git deposunun bir takma adıdır. Geleneksel olarak ilk depo adını böyle versek de, farklı isimler de verebiliriz. Özellikle birden fazla uzak deposu bulunan projelerde kullanımı faydalıdır.

5. "HEAD" kelimesi neyi temsil etmektedir?
    "HEAD" kelimesi, Git deposundaki mevcut işlem yapıldığı konumu temsil eder. Daha spesifik olarak, "HEAD" genellikle şu anki çalışma daldaki en son taahhütü işaret eder. Bu, kullanıcının çalıştığı dalı ve bu dalın son durumunu gösterir.

6. "Staging Area" ya da "Index" diye isimlendirilen bölge tam olarak ne demektir?
    Staging Area, Git deposunda değişikliklerin hazırlandığı ve sonraki bir taahhüde dahil edilmek üzere bekletildiği bir ara alanı temsil eder. Bu bölge, değişikliklerin taahhütlere eklenmeden önce düzenlenmesine ve kontrol edilmesine olanak tanır.  

7. "Untracked file" ne demektir?
    İzlenmeyen dosya, henüz ara bölgeye (staging area) alınmamış dosyalardır. Git, bu dosyanın değişikliklerini izlemeyecek veya kaydetmeyecek ve bu dosya hakkında herhangi bir bilgi saklamayacaktır. 

8. ".git" klasörünü silersek ne olur?
    Bu klasörü silersek proje ile ilgili lokalde tuttuğumuz git ile ilgili tüm değişiklikler, tarih ve takip bilgisi silinir.

9. Kendi lokalimizde her "git init" komutunu kullanıdığımızda otomatik olarak "ReadMe.md" dosyası oluşturulmasını istiyorsak ne yapmalıyız?
    Bunun için Git şablonunu (template) kullanabiliriz. Şu adımları izleyebiliriz:
    1. Lokal çalışma ortamında bir "ReadMe.md" dosyası oluştururuz. Bu bizim için yeni depo oluştururken bir şablon görevi görecek.
    2. Git şablonunun adresini git config ile şu şekilde kaydedelim (/path/to/your/template/directory yerine ReadMe.md oluşturduğumuz adresi vereceğiz):
    ```
        git config --global init.templateDir /path/to/your/template/directory
    ```
    3. "git init" komutu ile depo oluşturabiliriz. Bu durumda "ReadMe.md" bizim için otomatik olarak oluşturulacaktır.

10. Git konusunda bahsi geçen "branch" yapısı nedir? Bize ne sağlar?
    Git sistemindeki dal yapısı geliştiricilere aynı proje üzerinde farklı özellikleri veya değişiklikleri paralel şekilde geliştirme imkanı verir. Bug düzeltmesi veya yeni özellik (feature) dalları açarak geliştiriciler canlı ürün dalını kirletmemiş olurlar. Bu aynı zamanda izolasyon da sağlar.

11. Sıfırdan bir "branch" nasıl oluşturabiliriz?
    Git sisteminde sıfırdan bir dal oluşturmanın 2 temel yolu vardır. Bunların ikisi de aynı işi yapar. Sadece versiyon farkı yönünden farkı vardır.
    1. Versiyon 2.23'ten sonra önerilen yol olan "switch" anahtar kelimesi ile dal oluşturabiliriz:
    ```
        git switch -c <dal_adi>
    ```
    2. Daha eski bir yol olan "checkout" anahtar kelimesi ile anahtar kelimesi ile dal oluşturabiliriz:
    ```
        git checkout -b <dal_adi>
    ```

12. Var olan bir "branch"e nasıl geçebiliriz?
    "switch" veya "checkout" anahtar kelimeleri ile var olan bir dala geçilebilir.
    1. Versiyon 2.23'ten sonra önerilen yol olan "switch" anahtar kelimesi ile dala geçme:
    ```
        git switch <dal_adi>
    ```
    2. Daha eski bir yol olan "checkout" anahtar kelimesi ile anahtar kelimesi ile dala geçme:
    ```
        git checkout <dal_adi>

13. "git clone" komutunu kullanırken belirli bir spesifik branch'i sadece çekmek istiyorsak nasıl yapabiliriz?
    Belirli bir dalı clone etmek istiyorsak, `-b` veya `--branch` bayrağını kullanmalıyız. Komut taslak olarak aşağıdaki gibidir:
    ,,,
        git clone -b <dal_adi> <depo_adresi>
    ,,,

14. "Merge conflict" ne demektir?
    "Merge conflict" (birleştirme çakışması), birleştirme işlemi sırasında karşılaşılan ve Git'in otomatik olarak çözemediği çatışmaları ifade eder. Bu çatışmalar, farklı dallardaki aynı dosyanın aynı satırında yapılan değişikliklerden kaynaklanabilir veya bir daldaki bir dosyanın silinmesi ve diğer dalda aynı dosyanın değiştirilmesi gibi durumlardan ortaya çıkabilir. Merge conflict, Git'in çatışmayı çözemediği durumlarda, kullanıcıya manuel olarak müdahale etmesi gerektiğini belirtir. Bu durumda, kullanıcı çatışan dosyaları incelemeli, çakışan değişiklikleri düzeltmeli ve ardından çözümlerini taahhüt (commit) etmelidir.

15. "git log" komutu ile hangi bilgileri görebiliriz?
    "git log" komutu, bir Git deposundaki commit geçmişini görüntülemek için kullanılır. Bu komutla, eşsiz birer hash kodu şekilde taahhütlerin kimliği, yazarın adı ve emaili, tarih ve saat bilgisi, taahhüt mesajı, yapılan değişikliklerin listesi (özet istiyorsan `--oneline`, ayrıntılı istiyorsak `-p` bayrakları kullanılabilir) gösterilir.

16. "git diff" ile kaç farklı iki durumun arasındaki değişiklikleri görebiliriz?
    "git diff" komutu temel olarak 4 farklı durumun karşılaştırması için kullanılır. Bunlar:
    1. İki commit arasındaki değişiklikleri görmek için:
    ```
        git diff <commit1> <commit2>
    ```
    2. İki farklı dal arasındaki değişiklikleri görmek için:
    ```
        git diff <branch1> <branch2>
    ```
    3. İki etiket arasındaki değişiklikleri görmek için:
    ```
        git diff <tag1> <tag2>
    ```
    4. Çalışma dizinizdeki değişiklikleri ve en son commit arasındaki farkı görmek için:
    ```
        git diff HEAD
    ```

17. Git reset ile neyi geri alıyoruz?
    "git reset" komutu, işaretçiyi (HEAD) ve çalışma dizinini belirli bir önceki konuma geri döndürmek için kullanılır. Bu, yapılan değişiklikleri geri almak veya değiştirmek için kullanışlıdır. 3 çeşit bayrak kullanılabilir:
    
    1. Soft reset (`--soft`): İşaretçiyi ve dizininizi belirli bir önceki commit'e (veya herhangi bir belirli bir konuma) geri götürür, ancak değişikliklerinizi çalışma dizinizdeki (staged) bırakır. Yani, commit yapmamış gibi bir önceki duruma dönmenizi sağlar.
    2. Mixed reset (`--mixed`): Soft reset gibi davranır, ancak değişiklikleri çalışma dizininden (staged) çıkarır ve değişiklikleri takip eden dosyaları değişikliklerden önceki durumuna geri getirir. Yani, commit yapmamış gibi çalışma dizinindeki değişiklikleri iptal eder, ancak dosyalarınızı değiştirmek için hazır hale getirir.
    3. Hard reset (`--hard`): İşaretçiyi belirli bir önceki konuma geri götürür ve tüm değişiklikleri ve kayıtlı olmayan dosyaları siler. Yani, belirli bir önceki duruma tam olarak geri dönmek istediğinizde kullanılır ve tüm yapılan değişiklikleri siler.

18. "git commit" ile "git push" arasındaki fark nedir?
19. Atomic commit ne demektir?
20. Repository ne demektir?
21. "git tag" nedir? "git branch"’ten farkı nedir?
22. Git'i görsel olarak kullanabilmek için hangi üçüncü taraf araçları ve uygulamaları kullanabiliriz?
23. "GitHub" ile "git" arasındaki fark nedir? GitHub benzeri diğer siteler nelerdir? GitHub veya diğer sitelerdeki kullanıcı adlarını yazar mısınız?
24. main ya da master branch'inin diğer branchlerden farkı nedir?
25. ".gitignore" dosyası nedir ve ne amaçla kullanılır? - (Teşekkürler @madenyasin)
26. "git push origin --delete branch_name” nedir ve ne için kullanılır?