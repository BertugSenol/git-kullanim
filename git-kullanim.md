> Git ve GitHub kurulumu MacOS üzeridne yapılmıştır.


# GIT VE GITHUB

## GIT

Git bir versiyon kontrol sistemidir. Üzerinde çalışılan projede yapılan değişiklikleri kontrol edebilmek için kullanılır. Projenin geçmişine sahip olmak önemlidir çünkü zaman içinde projede yapılan değişiklikleri görme ve bunları düzenleyebilmemize olanak sağlar. Böylece geçmiş versiyonlara geri dönebilir, verileri veya dosyaları tekrardan düzenleme fırsatı bulabiliriz.

### Git Kurulumu

#### Git for MacOS

MacOS için [buraya](http://git-scm.com/download/mac) tıklayın ve Git'i kurun.

#### Git for Windows

Windows için [buraya](https://git-scm.com/download/win) tıklayın ve Git'i kurun.

#### Git for Linux

Linux için [buraya](https://git-scm.com/download/linux) tıklayın ve Git'i kurun.

---

Kurulumu tamamladıktan sonra terminalde `git` komutunu çalıştırabiliyor olmanız gerekiyor.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/Git-kurulum.png "Terminal")

##### Git için Terminal Yapılandırma

`$ chsh -s /bin/bash`

yazarak varsayılan terminalizi _zsh_'tan _bash_'a geçirebilirsiniz.

`$ chsh -s /bin/zsh`

yazarak da varsayılan terminalizi tekrardan _zsh_ yapabilirsiniz.

> Not: Aşağıda yer alan komutları kullanabilmeniz için varsayılan terminalinizin **bash** olması gerekmektedir.

> Varsayılan terminalinizi değiştirdikten sonra terminali kapatıp tekrardan çalıştırmanız gerekmektedir.

> Terminalde isminizin yanında master # yazısını göreceksiniz.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/Git-baslangic.png "Terminal")

### Git Yapılandırma

Versiyonların kim tarafından ve ne zaman gerçekleştiğini belirtmek için yapılandırma işlemi yapılmalıdır. Her şeyin kurulduğuna emin olmak için aşağıdaki komutları terminalde tek tek çalıştırın.

```
# Git'i kendi adınıza göre ayarlama
$ git config --global user.name "<tam-adınız>"

# Git'i kendi email adresinize göre ayarlama
$ git config --global user.email "<email-adresiniz>"

# Git çıktınızı renklendirme
$ git config --global color.ui auto

# Mevcut git ayarlarınıza ulaşma
$ git config --list
```

### Git&Code Editörü

Yapılandırmanın son adımı çalışacağınız editörü kurmaktır.

`$ git config --global core.editor <"editör-ismi"> --wait`

- Atom kullanmak için editör ismi yerine **atom**,

- VSCode kullanmak için editör ismi yerine **code** yazabilirsiniz.


### Git Projesi Oluşturma

Git repository'si ile işlem yapmadan önce öncelikle git reposunun oluşturulması gerekmektedir. Yeni bir git repository'si oluşturmak için `git init` komutunu kullanacağız.

#### Temel Terminal Komutları

`pwd` --> Mevcut dizinin path'i

`ls` --> Mevcut dizindeki dosyaların listesi

`cd` --> Dizin değiştirme

`cd -` --> Bir önceki dizine dönme

`rm` --> Belirtilen dosya veya dizini silme

`clear` --> Terminali temizleme


#### Temel Git Komutları

Öncelikle çalışmak istediğimiz dosyayı (bu dosyanın git projesi olduğunu belirtmek için) belirlemeliyiz. Daha sonrasında bu dosyanın içine terminal açacağız.

`$ cd <"Gitmek istediğiniz dosyanın yolu">`

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-path.png "cd komutu")

Çalışmak istediğimiz dosya içine bu dosyanın bir git projesi olduğunu belirtmek için terminale

`$ git init`

yazmamız gerekmektedir.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-init.png "git init")

`git init` komutu git'in dizindeki takip etmesi için gerekli olan bütün dosyaları dizinin içine **.git** adlı gizli bir dosyanın içine kurar. Başındaki nokta kurulacak olan dizinin gizli olacağı anlamına gelir.

### Local Bilgisayarınıza Git Repository'si Klonlama

Git kullanmanın en büyük avantajlarından birisi de başka bilgisayarlardan kendi(local) bilgisayarımıza git reposunu çekebiliyor olmamızdır.

GitHub'tan kendi bilgisayarınıza repo klonlamak isterseniz klonlamak istediğiniz projenin url adresini kopyalamanız gerekmektedir. Url adresine repo sayfasında bulunan **Code** sekmesinde bulunan *web url*sinden ulaşabilirsiniz.

![Web](/users/bertugsenol/Desktop/Ekran-Resimleri/git-klon.png "Git Clone")

`$ git clone <"local-bilgisayarımıza-çekmek-istediğimiz-reponun-url-adresi">`

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/terminal-klon.png "Git Clone")

> `git clone` komutu kullanıldığında mevcut çalışma dizininizin içine klonladığınız repo için yeni bir dizin oluşturur. Bu terminalinizde anlık olarak bulunduğunuz *path*'i değiştirmez. Bu yüzden terminalden `cd` komutu ile klonladığınız dizinin içine gitmeniz gerekmektedir.

> Bir repo `git clone` komutu ile klon edildiğinde **git init** otomatik olarak klon ile beraber gelir.

### Çalışma Dizinimizdeki Reponun Durumu

Ana araçlarımızdan birisi olan `$ git status` komutu, mevcut çalışma dizinimizdeki dosyaların hangi durumda olduğunun çıktısını verir ve bir sonraki adımda hangi komutları kullanabileceğimiz hakkında ipuçları verir.

`$ git status`

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-status.png "Git Status")

> Şu anda **Working Directory**'de .DS-Store adlı dosyamız dışında herhangi bir dosya olmadığı için git hiçbir dosyamızı takip etmiyor.
>> .DS_Store, MacOS bilgisayarlarda dizinin Finder bilgilerini depoladığı dosyadır. Herhangi bir git reposunda kullanımı yoktur. **.gitignore** dosyasının içine ekleyebilirsiniz. Eğer ki zaten reponuzda yer alıyorsa da `.gitignore` dosyasına ekledikten sonra `git rm --cached .DS_Store` komutuyla sisteminizden kaldırabilirsiniz.

- On branch master: git'in şu anda master dalında olduğunu belirtir.
- Your branch is up to date with 'origin/master': Projemizin klonlanan repo ile senkron olduğunu belirtir.

> `git status` terminalde en çok kullanacağımız komutlardan biri olacak. Git'in çalışma dizininde oluşturulan fakat henüz takip etmediği dosyalar ve git'in takip ettiği düzenleme yapılan dosyalar hakkında bilgiler verir.


### Reponun Commit Geçmişini Görüntüleme

Öncelikle "Commit etmek nedir ve ne sıklıkta commit işlemi yapılmalıdır?" sorularının cevabını verelim.

Commit etmek, `git`'in takip ettiği dosyaları veri tabanına kalıcı olarak eklemesi olayıdır. Proje üzerinde yapılan değişiklikler arasında commit alınması gerekir. İki commit işlemi arasındaki bu değişikliklerin  ne çok büyük ne çok küçük olmalıdır. Böylelikle çok sık commit işlemi yapmamış oluruz ya da yapılan büyük değişiklikte çıkan problemler sonrası bir önceki versiyona geçtiğimizde çok bir şey kaybetmemiş oluruz.

Aldığımız her commit'e, commit hakkında bir mesaj bırakabiliriz. Bu eski versiyonlara dönmek istediğimiz zaman işimize yarayacaktır.

#### Git Log komutu

`git log` komutu ile mevcut projede yapılmış **commit** işlemlerini takip edebiliriz.

`$ git log`

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-log.png "Git Log")

Klonladığımız repoda yapılan değişikleri görmek için yazdığımız `git log` komutu bize birden fazla bilgi verir.

- Yapılan commit işlemlerinin ilk satırında yer alan sarı renkli commit yazısı bize o commit'in kimlik numarasını yani **SHA** kodunu verir.
  - SHA kodu 40 hanelidir. Ulaşmak istediğimiz commit'e bu numaranın ilk 7 hanesiyle veya bütünüyle ulaşabiliriz.
- Author: Yapılan commit işleminin kimin tarafından gerçekleştiğini belirtir.
- Date: Yapılan commit işleminin hangi tarihte yapıldığını belirtir.
- Yapılan commit işleminin son satırında ise commit işlemine verilen mesaj yer alır.
- SHA kodunun yanıda yer alan (HEAD -> master) bilgisi de güncel olan commit'in hangisi olduğunu belirtir.

> Repo içerisinde çok fazla commit işlemi yapıldıysa terminal bize yapılan bütün commit işlemlerini göstermeyecektir.

Yapılan commit işlemlerinin hepsini görebilmek için;

- `j` veya `↓` tuşlarıyla aşağı doğru inebilir,
- `k` veya `↑` tuşlarıyla yukarı doğru çıkabilir,
- spacebar kullanarak bir sayfa olacak şekilde aşağı inebilir,
- `q` tuşu ile de `git log` işleminden çıkış yapabilirsiniz.

##### git log --oneline

`$ git log --oneline`

komutu ile de yapılan commit işlemlerini tek satır halinde görebiliriz. Commit'in SHA kodunun ilk 7 hanesini gösterir. Hangi dosya üzerinde değişiklik yapıldığı hakkında bilgi vermez.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-oneline.png "Git Oneline")

##### git log --stat

`$ git log --stat`

komutu ile yapılan commit işlemlerini daha detaylı görebilirsiniz. Düzenleme yapılan dosyaları gösterir.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-stat.png "Git Stat")

> Yeşil renkli +'lar ve kırmızı renkli -'ler bize o commit işleminde yapılan eklemeler ve çıkarmaların kaçar satır olduğu hakkında bilgiler verir.

##### git log -p

`$ git log -p`

komutu ile düzenlenen dosya içerisinde aslında hangi değişikliklerin yapıldığı bilgisini alabiliriz.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-log-p.png "Git Log -p")

- 1 - düzenleme yapılan dosyanın hangisi olduğunu belirtir.
- 2 - düzenleme yapılan dosyanın eski ve yeni versiyon isimlerini söyler.
- 3 - düzenlemelerin hangi satırlarda olduğu hakkında bilgi verir.
  - -0,0 eski versiyonun, +1,2 yeni versiyonun bilgisidir.
- 4 - yapılan değişikliklerin aslında ne olduğunu belirtir.
  - kırmızı renkli satırlar orijinal versiyonda olup da commit sırasında kaldırılanları/silinenleri temsil eder.
  - yeşil renkli satırlar commit sırasında eklenenleri temsil eder.

##### git log -p --stat

`$ git log -p --stat`

komutu `git log -p` ve `git log --stat` komutlarının birleşimidir. `--stat` bilgisi `-p` bilgisinin üzerinde yer alır.

#### git show

`$ git show`

komutu `git log -p` komutu ile benzer çalışmaktadır. `git show` komutunu tek başına yazdığımız zaman yapılan son commit işleminin detayları bilgisini alabiliriz.

##### git show <"SHA-kodu" veya "SHA kodunun ilk 7 hanesi">

`$ git show 2fad73f`

komutu ilk 7 hanesi "2fad73f" olan commit işleminin detaylarını gösterir.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-show.png "Git Show")

### Working Directory - Staging Index - Repository Bölgeleri ve Commit İşlemi

- Working Directory: Çalışma dizini anlamına gelir. Git'in henüz takip etmediği, üzerinde değişiklikler yapılan dosyalar bu bölgede yer alır.
- Staging Index: Dosyanın commit edilmesi için staging index bölgesinde olması gerekmektedir.
  - `git add` komutu commit etmek istediğimiz dosya veya dosyaları working directory bölgesinden staging index bölgesine gönderir.

    `$ git add <"commit-edilmesini-istediğimiz-dosyanın-adı">`

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-add.png "Git Add")

> text-2-new.txt dosyasında değişiklik yaptıktan sonra `git add text-2-new.txt` komutunu yazıyoruz.

  - `git add .` komutu working directory bölgesinde bulunan **bütün** dosyaların staging index bölgesine geçmesi için kullanılır.

    `$ git add .`

  - `git add <"file-1 file-2 file-3 ....">` komutu ile manuel olarak working directory bölgesinden staging index bölgesine gönderebiliriz.

    `$ git add <"file-1 file-2 file-3 ....">`

  - Staging index bölgesine eklenen dosya, `git status` komutu ile durumunu sorguladığımızda **"Changes to be committed"** satırının hemen altında yer alacaktır.

  - Staging index bölgesinde yer alan dosyayı tekrardan working directory bölgesine göndermek istersek `git rm --cached <"staging-index-bölgesinde-olan-ve-unstage-etmek-istediğimiz-dosya">` komutunu kullanmamız gerekir.

    `$ git rm --cached <"staging-index-bölgesinde-olan-ve-unstage-etmek-istediğimiz-dosya">`

- Repository: Staging index bölgesinde bulunan dosya veya dosyaların commit edilmesinden sonra eklendiği bölgedir.

  - `git commit` komutu staging index bölgesinde yer alan dosya veya dosyaların commit edilmesi için kullanılır.

    `$ git commit -m <"yapılan-commit-işlemi-mesajı">`

      - `git log` komutu ile yapılan commit işleminin kontrolünü sağlayabilirsiniz.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-stages.png "Git Stages")

### Git Diff

`git diff` komutu henüz commit edilmemiş, çalışma dizinindeki dosyanın bir önceki versiyondan farkını görebilmek için kullanılır.

`$ git diff`

`$ git diff <"file-name">` ile de özel olarak o dosyanın git reposunda bulunan versiyonu ile arasındaki farkı kontrol edebilirsiniz.

### .gitignore

Projenin yapısında yer almasını istediğimiz fakat commit edilmesini istemediğimiz dosyalar için `.gitignore` komutunu kullanabiliriz. `.git` dosyasının bulunduğu lokasyona `.gitignore` adlı gizli bir dosya kurulacaktır. git'in takip etmesini istemediğimiz dosyaların isimlerini .gitignore dosyasının içine yazmamız git'in artık o dosyaları takip etmemesini sağlar.

`$ cat >> .gitignore`

komutu ile gizli bir `.gitignore` dosyası oluşturduktan sonra terminale git'in takip etmesini istemediğiniz dosyanın adını yazmanız o dosyanın bundan sonra git tarafından *ignore* edilmesini sağlayacaktır.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-ignore.png "Git Ignore")

### Terminal Üzerinden Dosya Silme İşlemi

`$ git rm <"file-name">` komutu ile silmek istediğimiz dosyayı dizinden kaldırabiliriz.

### Terminal Üzerinden Dosya Adı Değiştirme İşlemi

`$ git mv <"dosyanın-eski-ismi"> <"dosyanın-yeni-ismi">` komutu ile terminal üzerinden dosya adı üzerinde değişiklik yapabilirsiniz.

### Versiyon Değiştirme (Geçmiş Commitlere Geri Dönme)

`$ git checkout <"geçmek-istediğimiz-versiyonun-SHA-kodu"> .`

komutu ile eski bir versiyona dönebiliriz. Komutun sonunda yer alan "**.**", bütün dosyaların eski versiyonalara döneceği anlamına gelir. Sadece belli dosyaların eski versiyona dönmesini istiyorsanız "**.**" yerine eski versiyona dönmesini istediğiniz dosyanın adını yazmanız yeterlidir.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-checkout.png "Git Checkout - Versiyon Değiştirme")

> Şu anda projede alınan 2 adet commit işlemi var ve güncel olan commit işlemi, yanında (**HEAD -> master**) yazan commit'tir.
> Yeni bir commit işlemi yapalım.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-checkout-2.png "Git Checkout - Versiyon Değiştirme")

> Yeni commit işlemi yapıldı ancak siz eski versiyona dönmek istiyorsunuz. Komutumuzu yazalım.

`$ git checkout fa5d9ec`

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-checkout-3.png "Git Checkout - Versiyon Değiştirme")

> Yapılan versiyon değişikliğini kontrol etmek amaçlı terminale `git log` yazalım.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-checkout-4.png "Git Checkout - Versiyon Değiştirme")

> Eski versiyonumuza döndük.

### Dal - Branch

Branch yani dal, projenin kopyası anlamına gelmektedir. Git çalıştığımız proje üzerine ilk kurulduğu zaman **master** adında bir dal yaratır ve projenin bir kopyasını burada tutar. Yapılan commit işlemi sırasında hangi dal aktif ise commit o dala eklenir.

> Yeni gelen güncellemeyle birlikte GitHub, ana dalını **main** olarak güncellemiştir.

#### git branch

`$ git branch`

komutu mevcut projede var olan dalların listesini çıkartır. Aktif olarak hangi dalda olduğumuzu da bu komut sayesinde öğrenebiliriz.

`$ git branch <"yaratmak-istediğimiz-dalın-ismi">`

komutu ile de yeni bir dal oluşturabiliriz.

##### Branch silme

`$ git branch -d <"silmek-istediğimiz-branch-adı">`

komutu ile dal silme işlemini gerçekleştirebiliriz.

#### git checkout

`$ git checkout <"geçmek-istediğimiz-dal">`

komutunu `$ git branch <"yaratmak-istediğimiz-dalın-ismi">` ile yarattığımız yeni dala geçmek için kullanabiliriz.

#### Branch içinde Git diff

`$ git diff master <"dal-ismi">`

komutu ile master dalı ile belirttiğimiz dal arasındaki farkı kontrol edebiliriz.


## GitHub

GitHub, git projeleri için bir depolama alanıdır. Bu depolama alanı yapılan projeyi dünyadaki herkesle paylaşmak için kullanılabilir. Repo paylaşabilir ve depo alanından uzak bilgisayara repo klonlayabilirsiniz.

### Yeni Bir Repository Oluşturma

- [GitHub](www.github.com) sitesine giriş yapın.
- Sağ üstte bulunan **+** sekmesine tıkladıktan sonra **New repository**'ye tıklayın.
- Deponuza vermek istediğiniz ismi, kelimelerin arasına "**-**" koyduktan sonra alt tarafta bulunan **Create new repository**'ye tıklayın.
- Böylece GitHub'ta reponuz oluşacaktır.

### GitHub'a Proje Gönderme

- İlk olarak oluşturduğumuz reponun linkini kopyalıyoruz.
- Daha sonra terminale `$ git remote add <"repomuza-vermek-istediğimiz-takma-isim"> <"GitHub-linki">` komutunu yazıyoruz.
  - `$ git remote` komutu ile yaptığımız işlemin kontrolünü sağlayabiliriz.
- Son olarak da `$ git push -u <"repomuza-verdiğimiz-takma-isim"> <"eklemek-istediğimiz-branch'ın-ismi">` komutunu girdikten sonra *GitHub* hesabımızın kullanıcı adını ve şifresini soracaktır.
  - Şifrenizi **Settings->Developer Settings->Personal Access Tokens->Generate New Token** yolunu izleyerek alabilirsiniz.

### Pull Request

Projede açılan dalların, projenin son aşamasında birleştirilmesi gerekir. Birden fazla branch'in olduğu projede yapılan değişiklikleri ana dalda birleştirmek için master branch için pull request atılmalıdır.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-pull.png "Git Pull")

- Projenin dallarını, pull request sekmesine tıkladığımızda görebiliriz. **Compare & pull request** ya da **new pull request**'e tıkladıktan sonra `base:<"ana-dal">, compare:<"yan-dal">` olacak şekilde **Create pull request**'e tıklayın.
  - Pull request oluşturmanız için dalların *merge* edilmeye uygun olması gerekmektedir.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-pull-2.png "Git Pull")

- Tekrardan aşağıda yer alan **Create pull request** butonuna bastıktan sonra karşımıza *merge pull request* seçeneği çıkacaktır.

![Terminal](/users/bertugsenol/Desktop/Ekran-Resimleri/git-pull-3.png "Git Pull")

- Daha sonrasında **Confirm merge** diyerek *pull request* işlemini tamamlıyoruz.

---
