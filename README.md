# igvc2027_ws
İTÜ Robotik Arama Kurtarma Ekibi, IGVC 2027 için otonom araç geliştirme 


RAKE Otonom Araç Takımı - Git & GitHub Çalışma Rehberi

Merhaba Takım! Projemizin (igvc2027_ws) GitHub üzerinde sorunsuz ilerlemesi, ana kodumuzun (main) her zaman hatasız kalması ve birbirimizin kodlarını bozmamamız için izleyeceğimiz standart iş akışı aşağıdadır.

Lütfen kod yazmaya başlamadan önce bu rehberi dikkatlice okuyun.
BÖLÜM 1: Şifre (Token) Oluşturma ve Kaydetme (Sadece 1 Kere)

GitHub artık terminalden komut yazarken hesap şifrenizi kabul etmiyor. Özel bir "Token" (Kişisel Erişim Şifresi) oluşturmamız gerekiyor.

    Token Üretme:

        GitHub'a tarayıcıdan giriş yapın.

        Sağ üst profil fotoğrafı > Settings > Sol en alt Developer settings > Personal access tokens > Tokens (classic) sekmesine gidin.

        Generate new token (classic) butonuna tıklayın. İsim verin (örn: ubuntu-pc), süreyi seçin ve listeden sadece repo kutucuğunu işaretleyip en alttan Generate token deyin.

        🚨 KRİTİK UYARI: ghp_ ile başlayan bu şifre sadece bir kere ekranda görünecektir. Sayfayı kapatmadan hemen bu şifreyi kopyalayın.

    Şifreyi Bilgisayara Kaydetme:

        Sürekli şifre girmemek için terminali açın ve şu komutu çalıştırın:git config --global credential.helper store

        (Bu komut şifrenizi diske kaydeder, böylece sonraki adımlarda şifre girdikten sonra bir daha size şifre sormaz).

BÖLÜM 2: Repoyu İndirme (Sadece İlk Gün)

Projeyi sıfırdan bilgisayarınıza çekmek için terminalde çalışmak istediğiniz klasöre gidin ve:git clone [https://github.com/hamzailgaz/igvc2027_ws.git](https://github.com/hamzailgaz/igvc2027_ws.git)cd igvc2027_ws
BÖLÜM 3: Günlük Geliştirme Döngüsü (Standart Mesai)

Projede her gün, her yeni koda başlarken bu adımları sırasıyla uygulayacağız.

1. En Güncel Kodu Alın (Pull Before Start)
Koda başlamadan önce herkesin eklediği son değişiklikleri kendi bilgisayarınıza çekmelisiniz.git checkout main (Ana dala geçiş yap)
git pull origin main (Son güncellemeleri indir)

2. Kendi Dalınızı (Branch) Açın
🚨 Kural: main dalında asla doğrudan kod yazmıyoruz! Yeni bir işe başlarken her zaman isminizle veya görevle bir dal açın:git checkout -b ismin/yeni-gorev-adi (Örn: git checkout -b muharrem/lidar-entegrasyonu)

    Hayat Kurtaran İpucu: Eğer dal açmayı unutup main üzerinde kod yazmaya başlarsanız panik yapmayın. Hemen git checkout -b yeni-dal yazın; Git, yazdığınız o havadaki kodları yeni dala otomatik taşıyacaktır.

3. Kod Yazın ve Test Edin
VS Code üzerinden veya terminalden ROS 2 paketlerinizi geliştirin. İşiniz bittiğinde mutlaka colcon build yaparak kodun derlendiğinden ve sistemi bozmadığından emin olun.

    🚨 VS Code Uyarısı: VS Code'un kendi ürettiği gizli .vscode klasörünü veya browse.vc.db gibi dosyaları kesinlikle GitHub'a göndermiyoruz. Değişiklikleri kaydederken bu dosyaların .gitignore tarafından engellendiğinden emin olun.

4. Değişiklikleri Paketleyin (Commit)
Değişen veya eklenen kodlarınızı GitHub'a kargolamak üzere paketleyin:git add . (Tüm değişiklikleri sahneye / kutuya al)
git commit -m "Lidar nokta bulutu eklendi ve test edildi" (Kutuyu etiketle)

5. GitHub'a Gönderin (Push)
Paketinizi GitHub sunucusuna yollayın:git push origin ismin/yeni-gorev-adi

    Şifre Sorarsa Ne Yapacağız?
    Terminal sizden Username istediğinde GitHub kullanıcı adınızı girin. Password istediğinde Bölüm 1'de kopyaladığınız ghp_ ile başlayan Token'ı yapıştırın.🚨 Dikkat: Linux terminaline şifre yapıştırdığınızda ekranda hiçbir şey (yıldız bile) görünmez! Yazmıyor sanıp defalarca yapıştırmayın. Bir kere sağ tıklayıp yapıştırın ve direkt Enter'a basın.

BÖLÜM 4: Pull Request (PR) Açma ve Kaptanı Bekleme

Kodlarınızı GitHub'a gönderdiniz, ancak bu kodlar henüz main dalına (ana projeye) geçmedi. Bunun için izin (PR) istemelisiniz:

    Tarayıcıdan hamzailgaz/igvc2027_ws GitHub sayfasına girin.

    Sayfanın üstünde sarı renkli "Compare & pull request" butonu göreceksiniz. (Eğer görmezseniz, Pull requests sekmesine girip New pull request diyerek sağ taraftan kendi dalınızı seçin).

    Açılan ekranda ne gibi değişiklikler yaptığınızı açıklayan kısa bir not yazın ve yeşil Create pull request butonuna basın.

    Burada işiniz bitiyor. Yazılım Kaptanı (Hamza) kodlarınızı inceleyecek. Eğer bir sorun yoksa yeşil "Merge" butonuna basarak sizin kodlarınızı ana projeye katacaktır.

    Onay gelene kadar yeni bir işe geçmek isterseniz tekrar git checkout main ve git pull origin main yaparak 1. adıma dönebilirsiniz.

İyi çalışmalar, hatasız derlemeler!
