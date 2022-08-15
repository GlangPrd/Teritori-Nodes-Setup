# Minumum System Requirements

- 2 CPU
- 4 GB RAM
- 80 GB SSD

 # Tek script ile Otomatik Kurulum

 - wget -O TT.sh https://raw.githubusercontent.com/Nodeist/Kurulumlar/main/Teritori/TT && chmod +x TT.sh && ./TT.sh
 
 # Kurulum Sonrası Kodlar
 
 Senkronizasyon durumunu kontrol etmek için :

- teritorid status 2>&1 | jq .SyncInfo

 # Cüzdan Oluşturma 

- teritorid keys add $MYWALLET

Cüzdanınızı hatırlatıcı (mnemonic) kullanarak kurtarmak için :

- teritorid keys add $MYWALLET --recover

 # Validatör Oluşturma 

- teritorid tx staking create-validator \
  --amount 1000000utori \
  --from $MYWALLET \
  --commission-max-change-rate "0.01" \
  --commission-max-rate "0.2" \
  --commission-rate "0.07" \
  --min-self-delegation "1" \
  --pubkey  $(teritorid tendermint show-validator) \
  --moniker $NODEİSMİ \
  --chain-id $TT_ID \
  --fees 250utori

 # Kullanışlı Komutlar
 
 Logları Kontrol Et :

- journalctl -fu teritorid -o cat

Servisi Yeniden Başlat :

- systemctl restart teritorid

 Hapisten Kurtul(Unjail):

- teritorid tx slashing unjail \
  --broadcast-mode=block \
  --from=$MYWALLET \
  --chain-id=$TT_ID \
  --gas=auto --fees 250utori




