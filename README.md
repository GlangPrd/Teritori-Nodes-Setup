# Minumum System Requirements

- 2 CPU
- 4 GB RAM
- 80 GB SSD

 # Tek script ile Otomatik Kurulum

 - wget -O TT.sh https://raw.githubusercontent.com/Nodeist/Kurulumlar/main/Teritori/TT && chmod +x TT.sh && ./TT.sh
 
 # Kurulum Sonrası Kodlar
 
 Senkronizasyon durumunu kontrol etmek için ;

- teritorid status 2>&1 | jq .SyncInfo

 # Cüzdan Oluşturma 

- teritorid keys add $MYWALLET

Cüzdanınızı hatırlatıcı (mnemonic) kullanarak kurtarmak için ;

- teritorid keys add $MYWALLET --recover



