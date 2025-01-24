<h2 align=center>Privasea Teşvikli Node</h2>

## Minimum Sistem Gereksinimleri

| **Component**             | **Requirement**                     |
|---------------------------|-------------------------------------|
| **Operating System (OS)** | Ubuntu (Recommended)                |
| **CPU Architecture**      | amd64 (x86 architecture)            |
| **Storage**               | 100GB available storage             |
| **Memory (RAM)**          | 4GB RAM                             |
| **Processor**             | 6 cores                             |

## Kurulum
- Docker imaj çekelim
```
docker pull privasea/acceleration-node-beta:latest
```
- Dizin olusturup icine girelim
```
mkdir -p ~/privasea/config && cd ~/privasea
```
- Cüzdan ve anahtar oluşturuyoruz
- Gireceğiniz şifreyi unutmayın, çıktıyı bir yere kaydedin.
```
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```
```
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```
- Siteye gidelim [Privanetix Dashboard](https://deepsea-beta.privasea.ai/privanetixNode)
- Testnet cüzdanınızı bağlayın, yeni node oluşturun node ismini belirleyin ardından komisyon oranını ayarlayın ben %20 yapıyorum ardından not ettiğiniz düğüm adresini yazın ve oluştura basın.
- Şimdi node çalışmaya başlaması için aşağıdaki kodu çalıştırın. değiştirmeniz gereken yer şifre yerine girdiğiniz şifreyi yazacaksınız.
```
KEYSTORE_PASSWORD=ŞİFRENİZ && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```
- Rehberi yapmaya 3. adımdan devam edin stake işlemleri.. [DOCS](https://www.privasea.ai/privanetix-node)
