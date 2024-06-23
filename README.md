# ECLİPSE TESTNET İŞLEMLERİ  

>Not : Yaptığımız işlemleri proje teşvik etmiyor. Sadece potansiyel ödüle hak kazanmak için yapıyoruz.
>
>İşlemleri sırasıyla yapın!
-----------------

# Başlangıç
### Perequisite Yüklemesi

```
sudo apt update
sudo apt upgrade -y
```
-----------

### Rust Yüklemesi

```
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
Çıkan kod satırında ```1``` işaretleyin

-----------

### Dosya Konum Değişikliği

```
. "$HOME/.cargo/env"
```
### Rust Versiyon Kontrol

```
rustc --version
```

### Solana CLI Kurulumu

#### 1
```
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
```

#### 2
```
export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"
```

### Solana CLI Versiyon Kontrol

```
solana --version
```

### Nodejs - NPM Kurulumu

Reply with ```y``` and proceed 
```
sudo apt-get update
sudo apt-get install nodejs
sudo apt-get install npm
npm install --global yarn

```

#### Versiyon Kontrol
```
node -v
npm --version
yarn --version
```


# Anchor Kurulumu

```
cargo install --git https://github.com/project-serum/anchor anchor-cli --locked
```
-----------
### Anchor Versiyon Kontrol
```
anchor --version
```
------------

## Solana Cüzdan Oluşturma

```
solana-keygen new -o /path-to-wallet/my-wallet.json
```
```ENTER``` basın ve devam edin

## Yeni Cüzdan Konfigürasyon İşlemleri

#### 1
```
solana config set --url https://testnet.dev2.eclipsenetwork.xyz/
```
------------

#### 2
```
solana config set --keypair /path-to-wallet/my-wallet.json

```

----------------

> Yeni cüzdan kelimelerini ve solana cüzdan adresinizi bir yere kaldırın.

----------------

# Kısım 2: Oluşturduğumuz Solana Cüzdanına ETH Sepolia Göndereceğiz

## Yukarıda aldığınız cüzdan seed kelimelerini - Metamask veya EVM uyumlu başka cüzdan uygulamasından içe aktarın.

> Aktardığınız cüzdanın adresini alın ve aşağıdaki faucetten test eth talep edin.

Quicknode : https://faucet.quicknode.com/ethereum/sepolia

-----

# Eclipse Bridge Reposunu Klone Yapalım

```
git clone https://github.com/Eclipse-Laboratories-Inc/testnet-deposit
```

### Rotasını Belirleyelim

#### 1
```
cd testnet-deposit
```
#### 2
```
npm install
```

# Güncellemeleri Yapalım
Node versiyonunu güncelle 
```
sudo apt-get remove nodejs
```
```y``` basın ve devam edin


```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash
source ~/.bashrc
```

```
nvm install --lts
nvm use --lts
```

```
node -v
```

-----------------

## Bridge Scriptini Çalıştıralım

```
node deposit.js [Solana Address] 0x7C9e161ebe55000a3220F972058Fb83273653a6e [Amount in Gwei] [Fee in Gwei] [Ethereum Private Key] [Sepolia RPC Endpoint]
```

## Yukarıdaki kısımları aşağıdaki bilgilere göre değiştirin!!!!

>Solana Adresss : Kaldırdığınız adresi köşeli parantez içerisiyle değiştirin
>
>Amount in Gwei : ```3000000```
>
>Fee in Gwei : ```100000```
>
>Ethereum Private Key : Metamaska aktardığınız cüzdanın private keyini yapıştırın
>
>Sepolia RPC Endpoint : -- https://rpc.sepolia.org/

## İşlemler sonrası aşağıdaki gibi görünmesi gerekiyor

```
node deposit.js Cz2CCCtzqUAB97NAkVM6FzdF6d3EPx7pa4pN1JaWwrxz 0x7C9e161ebe55000a3220F972058Fb83273653a6e 3000000 3000000 0xeeeeeeeeeeeeeeeeeeprivatekey https://rpc.sepolia.org/
```
![image](https://github.com/mztacat/Eclipse-Testnet-Interaction/assets/31314340/e1b43551-6eaf-4a2a-81fb-9312c775d47e)

## Solana Cüzdan Bakiye Kontrol 

```
solana balance
```
![image](https://github.com/mztacat/Eclipse-Testnet-Interaction/assets/31314340/626224c9-d871-4fc9-bb3d-f7560fbb7f56)

# Token Oluşturma

```
spl-token create-token --enable-metadata -p TokenzQdBNbLqP5VEhdkAS6EPFLC1PHnBqCXEpPxuEb
```
### Aşağıdaki gibi adres oluşturduysa diğer işleme geçin
![image](https://github.com/mztacat/Eclipse-Testnet-Interaction/assets/31314340/14b85f96-e975-41ee-aebb-de86ff38203d)

## Mint Token 

```
spl-token create-account <Token Adresinizi Yazın>
```

### Token Bakiye Kontrol
```
spl-token accounts
```
![image](https://github.com/mztacat/Eclipse-Testnet-Interaction/assets/31314340/e5308f99-62ad-457a-89ea-a8fed07110ef)


# İşlemler bu kadar şimdi en başında solana address komudu ile aldığımız sol adresimizle aşağıdaki formu dolduruyoruz.

Doldur:
https://docs.google.com/forms/d/e/1FAIpQLSfJQCFBKHpiy2HVw9lTjCj7k0BqNKnP6G1cd0YdKhaPLWD-AA/viewform?pli=1

