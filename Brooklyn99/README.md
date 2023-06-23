# THM-B99
## TryHackMe Brooklyn 99 çözümü
## Bu CTF'de amacımız bir adet user flag ve bir adet root flag bulmak. Herkese iyi denemeler.
### Öncelikle nmap kullanarak bize verilen ip adresini taratıyoruz.

![nmap1](https://github.com/nonamexishere/TryHackMe/assets/137460049/53b4f557-adf1-4956-80fd-1b60f9fbef22)

![nmap2](https://github.com/nonamexishere/TryHackMe/assets/137460049/e9cb4636-97f4-4647-b664-992d25c827ee)

### Sonuçlar bize 21 ftp 22 ssh ve 80 http portlarının açık olduğunu söylüyor.
### Aynı zamanda görüldüğü üzere 21 ftp portuna Anonymous adıyla şifresiz giriş imkanımız var.

![ftp1](https://github.com/nonamexishere/TryHackMe/assets/137460049/e19559c3-d1b1-4dc1-b862-88b8e57242bf)

### Anonymous kullanıcı adıyla şifreyi boş bırakıp içeri giriyoruz ve içerde txt dosyası bulunuyor.
### Ne yazıkki cat komutuyla bunu okuyamıyoruz. Bu yüzden get komutu kullanıp dosyayı indirelim.

![ftp2](https://github.com/nonamexishere/TryHackMe/assets/137460049/00d43865-78df-4443-bdc6-956421bcef68)

### Dosyayı indirdik şimdi içeriğine bakalım.

![ftp3](https://github.com/nonamexishere/TryHackMe/assets/137460049/2a3509a7-67d1-4690-963f-fc8f538e22c8)

### Burdan anlaşılabilceği üzere Jake diye bir kullanıcımız var ve şifresi zayıf. Yani bruteforce kullanabiliriz.

![hydra1](https://github.com/nonamexishere/TryHackMe/assets/137460049/6cc0e83e-fe14-4b69-a985-50b4639b14a4)

### Hydra kullanarak saldırı başlatıyoruz. 

![hydra2](https://github.com/nonamexishere/TryHackMe/assets/137460049/01dd277e-6e6a-4460-96b3-1fd34de87b76)

### Şifremizi elde ettik artık ssh ile içeri giriş yapabiliriz.
### Jake'in dizininde ls çalıştırıyoruz. Ancak çok fazla işe yarar bir şey bulamıyoruz.
### Home dizinine geçtikten sonra totalde 3 kullanıcı görüyoruz.

![ssh1](https://github.com/nonamexishere/TryHackMe/assets/137460049/4d6ff192-b9e0-4663-933a-b5a6e0af5b21)

### Bunlardan holt klasörünün içinde user.txt isimli bir dosya buluyoruz ve içinde ilk flagimiz yer alıyor.

![ssh2](https://github.com/nonamexishere/TryHackMe/assets/137460049/6186e8b4-da08-4091-a33b-946ec75c8123)

### Evet, ilk flagimizi aldıktan sonra sıra geldi root flagi bulmaya.

![yetki1](https://github.com/nonamexishere/TryHackMe/assets/137460049/27f80496-c036-44e1-a9be-d993216bf668)

### Kullanabildiğimiz root komutu var mı diye sudo -l kullanıyoruz.
### Görüldüğü üzere less komutunu root olarak kullanabiliyoruz.
### less komutu normalde dosyaları okumak için kullanılır.
### Bunu lehimize kullanıp root olarak shell açabiliriz. Herhangi bir dosyayı less ile açıyoruz.

![yetki2](https://github.com/nonamexishere/TryHackMe/assets/137460049/85edb2f4-cc64-4ac4-b3df-705364c4972a)

### !/bin/sh komutunu çalıştırıyoruz.

![yetki3](https://github.com/nonamexishere/TryHackMe/assets/137460049/1b436565-5d69-4beb-bfe7-d760b375d27a)

### Artık içerideyiz. Root flagimizi de alıp bu etapı sonlandırıyoruz. Buraya kadar takip ettiğiniz için teşekkürler.

![final](https://github.com/nonamexishere/TryHackMe/assets/137460049/eca96147-0c31-414e-b491-46450d5114de)

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


