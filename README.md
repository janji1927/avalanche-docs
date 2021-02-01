---
deskripsi: >-
   Bangun di atas Avalanche. Bangun tanpa batas. Pengembang yang membangun di atas Avalanche
  dapat dengan mudah membuat aplikasi yang kuat, andal, dan aman.
---

# Dokumentasi Pengembang

## Mulai

{% tabs %}
{% tab title="Berasal Dari Ethereum?" %}
{% page-ref page="build/tutorials/smart-contracts/deploy-a-smart-contract-on-avalanche-using-remix-and-metamask.md" %}

{% page-ref page="build/tutorials/smart-contracts/using-truffle-with-the-avalanche-c-chain.md" %}
{% endtab %}

{% tab title="Avalanche Wallet" %}
{% page-ref page="build/tutorials/nodes-and-staking/staking-avax-by-validating-or-delegating-with-the-avalanche-wallet.md" %}

{% page-ref page="build/tutorials/platform/transfer-avax-between-x-chain-and-p-chain.md" %}

{% page-ref page="build/tutorials/platform/transfer-avax-between-x-chain-and-c-chain.md" %}
{% endtab %}

{% tab title="Staking" %}
{% page-ref page="build/get-started.md" %}

{% page-ref page="build/tutorials/nodes-and-staking/" %}
{% endtab %}

{% tab title="Advanced" %}
{% page-ref page="build/tutorials/platform/create-a-subnet.md" %}

{% page-ref page="build/tutorials/platform/create-a-new-blockchain.md" %}

{% page-ref page="build/tutorials/smart-digital-assets/create-a-fix-cap-asset.md" %}

{% page-ref page="build/tutorials/smart-digital-assets/creating-a-variable-cap-asset.md" %}

{% page-ref page="build/tutorials/smart-digital-assets/creating-a-nft-part-1.md" %}
{% endtab %}
{% endtabs %}

## Avalanche

[Avalanche](https://avax.network) platform sumber terbuka untuk meluncurkan [aplikasi terdesentralisasi](https://support.avalabs.org/en/articles/4587146-what-is-a-decentralized-application-dapp) dan penerapan [blockchain](http://support.avalabs.org/en/articles/4064677-what-is-a-blockchain) perusahaan dalam satu ekosistem yang dapat dioperasikan dan sangat skalabel. Avalanche memberi Anda kendali penuh pada jaringan dan lapisan aplikasi – membantu Anda membangun apa pun yang dapat Anda bayangkan.

Perbedaan utama antara Avalanche dan jaringan terdesentralisasi lainnya adalah protokol konsensus. Seiring waktu, orang menjadi salah paham bahwa blockchain harus lambat dan tidak dapat diskalakan. Protokol Avalanche menggunakan pendekatan baru terhadap konsensus untuk mencapai jaminan keamanan yang kuat, penyelesaian cepat, dan throughput tinggi, tanpa mengorbankan desentralisasi.

## Token \(AVAX\) Avalanche

Token Avalanche \(AVAX\) adalah token asli dari platform Avalanche dan digunakan untuk mengamankan jaringan melalui staking, bertransaksi peer-to-peer, membayar biaya, dan menyediakan unit akun dasar antara beberapa subnetwork yang dibuat di platform Avalanche. `1 nAVAX` sama dengan` 0.000000001 AVAX`.

## Protokol Konsensus Avalanche

![Consensus Comparison](.gitbook/assets/consensus-comparison.png)

Protokol dalam keluarga Avalanche beroperasi melalui pemungutan suara sub-sampel berulang kali. Ketika sebuah [validator](http://support.avalabs.org/en/articles/4064704-what-is-a-blockchain-validator) sedang menentukan apakah [transaksi](http://support.avalabs.org/en/articles/4587384-what-is-a-transaction) harus diterima atau ditolak, ini menanyakan subset kecil validator acak apakah menurut mereka transaksi harus diterima atau ditolak. Jika validator yang ditanya menganggap transaksi tersebut tidak valid, telah menolak transaksi tersebut, atau lebih memilih transaksi yang bentrok, ia menjawab bahwa transaksi tersebut harus ditolak. Jika tidak, ia menjawab bahwa transaksi tersebut harus diterima.

Jika sebagian besar \ (_ alpha_ $$α$$ \) dari validator mengambil sampel balasan yang menurut mereka transaksi harus diterima, validator lebih memilih untuk menerima transaksi. Artinya, ketika ditanya tentang transaksi di masa depan, ia akan menjawab bahwa transaksi tersebut harus diterima. Demikian pula, validator akan memilih untuk menolak transaksi jika sebagian besar validator menjawab bahwa mereka menganggap transaksi tersebut harus ditolak.

Validator mengulangi proses pengambilan sampel ini hingga _alpha_ dari validator menanyakan balasan dengan cara yang sama \(terima atau tolak\) untuk putaran berturut-turut _beta_ $$β$$.

Dalam kasus umum ketika transaksi tidak memiliki konflik, penyelesaian terjadi dengan sangat cepat. Ketika konflik terjadi, validator yang jujur dengan cepat berkumpul di sekitar transaksi yang bertentangan, memasuki loop umpan balik positif sampai semua validator yang benar memilih transaksi itu. Hal ini mengarah pada penerimaan transaksi yang tidak bertentangan dan penolakan transaksi yang bentrok.

![How Avalanche Consensus Works](.gitbook/assets/howavalancheconsensusworks.png)

It is guaranteed \(with high probability based on system parameters\) that if any honest validator accepts or rejects a transaction, all honest validators will accept or reject that transaction.

Learn more technical components of the Avalanche consensus protocol by reading the [whitepaper](https://arxiv.org/pdf/1906.08936.pdf).

## Snowman Consensus Protocol

Snowman is a chain-optimized consensus protocol–high-throughput, totally-ordered, and great for smart contracts. Snowman is powered by the [Avalanche consensus protocol](./#avalanche-consensus-protocol). Both [P-Chain](learn/platform-overview/#platform-chain-p-chain) and [C-Chain](learn/platform-overview/#contract-chain-c-chain) implement the Snowman consensus protocol.

## Key Features

### Speed

Uses a novel consensus protocol, developed by a team of Cornell computer scientists, and is able to permanently confirm transactions in under 1 second.

### Scalability

Capable of 4,500 transactions per second–an order of magnitude greater than existing blockchains.

### Security

Ensures stronger security guarantees well-above the 51% standard of other networks.

### Flexibility

Easily create custom blockchains and decentralized apps that contain almost any arbitrary logic.

### Sustainability

Uses energy-efficient proof-of-stake consensus algorithm rather than proof-of-work.

### Smart Contract Support

Supports the creation of Solidity smart contracts and your favorite Ethereum tools like Remix, Metamask, Truffle, and more.

### Private and Public Blockchains

Create your own public or private blockchains.

### Designed for Finance

Native support for easily creating and trading digital smart assets with complex, custom rulesets.
**strong text**
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkxODQwNTYxOSwtMTY0OTE4MzU4MSwtMT
Y0MDM4NjIyNiwtNDY4MjkxMDkwLC02NTk1NTM5MzNdfQ==
-->