# THM-B99
## TryHackMe Brooklyn 99 çözümü
## Bu CTF'de amacımız bir adet user flag ve bir adet root flag bulmak. Herkese iyi denemeler.
### Öncelikle nmap kullanarak bize verilen ip adresini taratıyoruz.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/ec997f2e-f3b6-492a-9db8-1a7a6c7bde17)

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/d6c68d0c-3de5-4f3c-bd13-ec803f3c0bdf)

### Sonuçlar bize 21 ftp 22 ssh ve 80 http portlarının açık olduğunu söylüyor.
### Aynı zamanda görüldüğü üzere 21 ftp portuna Anonymous adıyla şifresiz giriş imkanımız var.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/292b6453-99be-44fb-a582-6ae8c431aeae)

### Anonymous kullanıcı adıyla şifreyi boş bırakıp içeri giriyoruz ve içerde txt dosyası bulunuyor.
### Ne yazıkki cat komutuyla bunu okuyamıyoruz. Bu yüzden get komutu kullanıp dosyayı indirelim.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/ffbd9d54-d49f-4034-82b4-3773813529e4)

### Dosyayı indirdik şimdi içeriğine bakalım.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/7c17a43d-8d6b-4a66-a02f-ceddaf3695d1)

### Burdan anlaşılabilceği üzere Jake diye bir kullanıcımız var ve şifresi zayıf. Yani bruteforce kullanabiliriz.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/3dde7ce3-31a5-4178-8e50-3bd7acd0e6cc)

### Hydra kullanarak saldırı başlatıyoruz. 

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/4c1a6a2b-ad18-4586-beed-1d15670e7038)

### Şifremizi elde ettik artık ssh ile içeri giriş yapabiliriz.
### Jake'in dizininde ls çalıştırıyoruz. Ancak çok fazla işe yarar bir şey bulamıyoruz.
### Home dizinine geçtikten sonra totalde 3 kullanıcı görüyoruz.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/467ebfd9-3c58-47ec-bdb7-7922260311c0)

### Bunlardan holt klasörünün içinde user.txt isimli bir dosya buluyoruz ve içinde ilk flagimiz yer alıyor.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/9eaf16eb-b617-4f38-a8d0-5d0abf59d59b)

### Evet, ilk flagimizi aldıktan sonra sıra geldi root flagi bulmaya.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/dc625099-a246-4f23-9633-5445f8150164)

### Kullanabildiğimiz root komutu var mı diye sudo -l kullanıyoruz.
### Görüldüğü üzere less komutunu root olarak kullanabiliyoruz.
### less komutu normalde dosyaları okumak için kullanılır.
### Bunu lehimize kullanıp root olarak shell açabiliriz. Herhangi bir dosyayı less ile açıyoruz.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/3fdb9c59-7330-4bf3-b9fc-686ac44cc018)

### !/bin/sh komutunu çalıştırıyoruz.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/5ba16e8e-8a57-4973-aea5-3e927c172641)

### Artık içerideyiz. Root flagimizi de alıp bu etapı sonlandırıyoruz. Buraya kadar takip ettiğiniz için teşekkürler.

![image](https://github.com/nonamexishere/THM-B99/assets/137460049/dc295567-187f-4679-8015-252dcbb73ee3)

### Aşağıdaki alan cevapları içermektedir.
## |
## |
## |
## |
## |
## |
## |
## |
## |
## |
## |
## |
## User flag : ee11cbb19052e40b07aac0ca060c23ee
## Root flag : 63a9f0ea7bb98050796b649e85481845


