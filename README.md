
<h1 align="center">Inery-Testnet-Kurulum-Rehberi

<br/><br>
![inery](https://user-images.githubusercontent.com/111747226/199734984-b5481b6f-ed6f-46b4-94ec-ff4ed18643ac.png)
<br/><br>
### Inery, verileri merkezden dağıtmak için blok zinciri teknolojisini kullanmak ve aynı zamanda veri ihlallerini azaltmak ve güvenliği sağlamak için benimsenen blok zinciri sinerjisine sahip dağıtılmış bir veritabanını temsil eder. Bu yaklaşım, kullanıcı verilerini güvence altına alır ve yaygın bir kullanıma sahiptir.

### Güvenli depolama, ilaç, tedarik zincirleri, finans, bankacılık vb. alanlarda kullanılabilir. Inery platformu uygulaması, sürekli olarak bilgisayar tarafından okunabilir bir forma dönüştürülen verilerin depolanması işlevi görür. Bu şekilde, verilerin güvenli bir şekilde saklanması ve değer sözleşmeleriyle bağlanmasıyla Inery Blockchain, verilerin en yüksek şeffaflık ve güvenlikle depolanmasını, değiştirilmesini ve aktarılmasını sağlar.

### Inery yazılımı, merkezi olmayan blok zinciri teknolojisinden yararlanmak isteyen herhangi bir işletme için mükemmel bir çözümü temsil ediyor. Bu nedenle Inery, veritabanlarının merkeziyetsizliği ele almak için özel olarak tasarlanmıştır.

### Sistem Gereksinimleri 

|CPU | RAM  | Disk  | 
|----|------|----------|
|   6| 12GB  | 500GB    |

# Aşağıdaki rehberden digital ocean veya google cloud ile en düşük sunucuları kiralayıp kurabilirsiniz.
  
   # Daha önce Node kurulumu yapmadıysanız buradan sırasıyla adımları takip ederek tüm süreci öğrenebilirsiniz.
  ## Yeni Başladım Rehberi; [Pusula Finans Labs.](https://www.labs.pusulafinans.com/category/rehber/)
  ### 1. [Testnet ve Node test kurulum rehberi Bölüm-1](https://www.labs.pusulafinans.com/2022/08/23/testnet-ve-node-kurulum-rehberi/)
  ### 2. [Yeni Chrome Tarayıcı nasıl açarım?](https://www.labs.pusulafinans.com/2022/08/23/yeni-chrome-tarayici-nasil-acarim/)
  ### 3. [Ücretsiz Sunucu Kiralama](https://www.labs.pusulafinans.com/2022/08/23/nasil-ucretsiz-sunucu-kiralarim/)
  ### 4. [Digital Ocean Nasıl Kayıt olurum?](https://www.labs.pusulafinans.com/2022/08/23/digital-oceana-nasil-kayit-olabilirim/)
  ### 5. [MobaXTerm Terminal Kurulumu](https://www.labs.pusulafinans.com/2022/08/23/mobaxterm-terminal-kurulumu/)

 
  
  # 1. adım
Öncelikle [Buradan](https://testnet.inery.io/dashboard/) sitesine girip kayıt ''Sign Up'' butonuyla kayıt olmamız gerekiyor. Kayıt aşamasından sonra bizden sunucumuza dair birtakım bilgileri istediği için, sunucuyu temin ettikten sonra kayıt işlemine devam etmemiz gerekiyor.
<br/><br>
![inery2](https://user-images.githubusercontent.com/111747226/199738064-451761ea-99cc-4250-8cdf-bcbcbc2aa463.png)

  Görseldeki adımları tamamlamak için; Aşağıdaki görseldeki gibi suncunuzdan bilgilerinizi temin edebilirsiniz. Contabo üzerinden gösterlim; "Reverse DNS Managment" sekmesine basıyoruz. Sonrasında gelen sayfada hem IP adresiniz karşında da ServerName kısmı var bunları kopyalayıp kayıt olurken yukarıdaki görselde gösterilen yerlere yazıyoruz.
 <br/><br> 
 ![inery3](https://user-images.githubusercontent.com/111747226/199739053-1e982aef-64ef-4843-9f26-ce4719e9da2c.png)
 
 ### Kayıt işlemi tamamladıktan sonra kendi sayfanızdaki bölümden test tokeni claim ediyoruz. Sonrasında, Node kurulum adımlarına geçebiliriz.
 
   # 1. adım Nore Kurulumu
   
  ## Root yetkisi alalım.
  ```
  sudo su
  cd
  ```
  
 ## Sunucumuzu güncelleyelim
  
  ```
 sudo apt update && sudo apt upgrade -y
  ```
  
 ## Kütüphane kurulumunu yapalım
  
 ```
sudo apt-get install -y make bzip2 automake libbz2-dev libssl-dev doxygen graphviz libgmp3-dev \
autotools-dev libicu-dev python2.7 python2.7-dev python3 python3-dev \
autoconf libtool curl zlib1g-dev sudo ruby libusb-1.0-0-dev \
libcurl4-gnutls-dev pkg-config patch llvm-7-dev clang-7 vim-common jq libncurses5
 ```
 
## Firewall için düzenlemeleri yapalım
   ```
sudo apt-get install firewalld 
sudo systemctl start firewalld 
sudo systemctl enable firewalld 
sudo firewall-cmd --set-default-zone=public 
sudo firewall-cmd --zone=public --add-port=22/tcp --permanent 
sudo firewall-cmd --zone=public --add-port=8888/tcp --permanent 
sudo firewall-cmd --zone=public --add-port=9010/tcp --permanent 
sudo firewall-cmd --reload 
sudo systemctl restart firewalld
 ```
 ## Githubdan gerekli dosyaları indiriyoruz.
   ```
git clone https://github.com/inery-blockchain/inery-node
 ```
## Kurulum klasörüne giriyoruz.
   ```
cd inery-node/inery.setup
 ```
## Uygulama izinlerini değiştirelim
   ```
chmod +x ine.py
 ``` 
## Binary'i aktarıyoruz.
   ```
./ine.py --export
 ``` 
## Bilgileri güncelleyelim.
   ```
cd; source .bashrc; cd -
 ``` 
## Config dosyasının içine girelim.
   ```
sudo nano tools/config.json
 ``` 
## Gerekli kısımlar değiştiriyoruz. Config dosyası içindeki bu bölümün gerekli ayarları kayıt olduğunuz Inery dashboard üzerinden ulaşabilirsiniz. oradaki bilgileri Aşağıdak kod parçasında gördüğünüz örnekteki yerlere yazıyoruz. 
   ```
"MASTER_ACCOUNT":
{
    "NAME": "AccountName",
    "PUBLIC_KEY": "PublicKey",
    "PRIVATE_KEY": "PrivateKey",
    "PEER_ADDRESS": "IP:9010",
    "HTTP_ADDRESS": "0.0.0.0:8888",
    "HOST_ADDRESS": "0.0.0.0:9010"
}
 ``` 
 ### Gerekli düzenlemeyi yaptıktan sonra CRTL+X yaptıktan sonra Y basıp ENTER ile değişkliği kayıt ediyoruz.
 
     ## Screen oluşturulım.
   ```
screen -R inery
 ```
      ## Node Başlatıyoruz.
   ```
./ine.py --master
 ```
 ###
 



  Formda sizden KMA adresinizi vermenizi isteyecek, bunun için polkadotjs cüzdana sahip olmanız gerekiyor. Kurulumunu bilmiyorsanız. [Buradan](https://www.pusulafinans.com/polkadot-cuzdan-nasil-olusturulur/) makalemize göz atabilirsiniz.
  Kurulumu yaptıktan sonra; Aşağıdaki görselleri takip ederek, KMA adresinize ulaşabilirsiniz.
  ![image](https://user-images.githubusercontent.com/111747226/195038643-45d453c9-20ff-49f6-b7a5-0d0b7f69577d.png)   ![image](https://user-images.githubusercontent.com/111747226/195038903-d12d58b5-16d6-4516-ac11-07457b8bc42c.png)

  
## Kayıt işlemleri sonrasında "contribute" aktif hale geldiğinde güncellemelerini yayınlarız.
