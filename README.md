
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

  
  
  ## Root yetkisi alalım.
  ```
  sudo su
  cd
  ```
  
 ## Sunucumuzu güncelleyelim
  
  ```
 sudo apt update && sudo apt upgrade -y
  ```
  
 ## Ardından bu komu ile çalıştırıyoruz.
  
 ```
curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/Manta-Network/manta-rs/main/tools/install.sh | sh
 ```
 
  ## Kurulum tamamlandıktan sonra
   ```
source ~/.profile
 ```
 ## İşlemler bu kadar kurulumu tamamladık. Şimdi kayıt işlemlerine devam edeceğiz.
   ```
manta-trusted-setup register
 ```
  

  
  
  
 ## Yukarıdaki kodu girdikten sonra aşağıdaki gibi bir ekran sizi karşılayacak. Buraya twitter adresinizi başında "@" işareti olmadan giriyoruz. Sonrasında mail adresimizi girip enter basıyoruz.
  
  ![image](https://docs.manta.network/assets/images/ts_guide_register-a29ac5c407de7d05e590fefa7c93ae5e.png)
  
### Bu şekilde bir görünüm elde ettiyseniz. Başarılı şekilde kayıt işlemini tamamlamışsınız demektir. 

#NOT: Yukarıdaki adımlar ile çalıştıramazsanız bu kısmı kullanabilirsiniz. 

 # 2. Manuel Kurulum
  
  
  ## Root yetkisi alalım.
  ```
  sudo su
  cd
  ```
  
 ## Sunucumuzu güncelleyelim
  
  ```
 sudo apt update && sudo apt upgrade -y
  ```
  
 ## Ardından bu komu ile çalıştırıyoruz.
  
 ```
sudo apt install pkg-config build-essential libssl-dev curl jq
 ```
 ```
curl https://sh.rustup.rs -sSf | sh -s -- -y
 ```
 ```
source $HOME/.cargo/env
 ```
 ```
git clone https://github.com/Manta-Network/manta-rs.git
 ```

 ```
cd manta-rs
 ``` 
 ```
cargo run --release --package manta-trusted-setup --all-features --bin groth16_phase2_client register
 ``` 
  
 ## İşlemler bu kadar kurulumu tamamladık. Şimdi kayıt işlemlerine devam edeceğiz.
   ```
manta-trusted-setup register
 ```
 ## Yukarıdaki kodu girdikten sonra aşağıdaki gibi bir ekran sizi karşılayacak. Buraya twitter adresinizi başında "@" işareti olmadan giriyoruz. Sonrasında mail adresimizi girip enter basıyoruz.
  
  ![image](https://docs.manta.network/assets/images/ts_guide_register-a29ac5c407de7d05e590fefa7c93ae5e.png)
  
### Bu şekilde bir görünüm elde ettiyseniz. Başarılı şekilde kayıt işlemini tamamlamışsınız demektir. 

# KAYIT FORMU;
  [Buradan](https://mantanetwork.typeform.com/TrustedSetup) formuna ulaşabilirsiniz. Sizden istenilen bilgileri oradan doldurup, kayı işlemini tamamlayabilirsiniz.
  
  Formda sizden KMA adresinizi vermenizi isteyecek, bunun için polkadotjs cüzdana sahip olmanız gerekiyor. Kurulumunu bilmiyorsanız. [Buradan](https://www.pusulafinans.com/polkadot-cuzdan-nasil-olusturulur/) makalemize göz atabilirsiniz.
  Kurulumu yaptıktan sonra; Aşağıdaki görselleri takip ederek, KMA adresinize ulaşabilirsiniz.
  ![image](https://user-images.githubusercontent.com/111747226/195038643-45d453c9-20ff-49f6-b7a5-0d0b7f69577d.png)   ![image](https://user-images.githubusercontent.com/111747226/195038903-d12d58b5-16d6-4516-ac11-07457b8bc42c.png)

  
## Kayıt işlemleri sonrasında "contribute" aktif hale geldiğinde güncellemelerini yayınlarız.
