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

Dijamin \(dengan probabilitas tinggi berdasarkan parameter sistem\) bahwa jika validator yang jujur menerima atau menolak transaksi, semua validator yang jujur akan menerima atau menolak transaksi itu.

Pelajari lebih lanjut komponen teknis dari protokol konsensus Avalanche dengan membaca [whitepaper](https://arxiv.org/pdf/1906.08936.pdf).

## Protokol Konsensus Manusia Salju

Snowman is a chain-optimized consensus protocol–high-throughput, totally-ordered, and great for smart contracts. Snowman is powered by the [Avalanche consensus protocol](./#avalanche-consensus-protocol). Both [P-Chain](learn/platform-overview/#platform-chain-p-chain) and [C-Chain](learn/platform-overview/#contract-chain-c-chain) implement the Snowman consensus protocol.

## Fitur Utama

### Kecepatan

Menggunakan protokol konsensus baru, yang dikembangkan oleh tim ilmuwan komputer Cornell, dan mampu mengkonfirmasi transaksi secara permanen dalam waktu kurang dari 1 detik.

### Scalability

Mampu 4,500 transaksi per detik – urutan besarnya lebih besar dari blockchain yang ada.

### Keamanan

Memastikan jaminan keamanan yang lebih kuat jauh di atas standar 51% jaringan lain.

### Fleksibilitas

Mudah membuat blockchain khusus dan aplikasi terdesentralisasi yang berisi hampir semua logika arbitrer.

### Keberlanjutan

Menggunakan algoritma konsensus bukti kepemilikan yang hemat energi daripada bukti kerja.

### Dukungan Kontrak Cerdas

Mendukung pembuatan kontrak pintar Soliditas dan alat Ethereum favorit Anda seperti Remix, Metamask, Truffle, dan banyak lagi.

### Blockchain Pribadi dan Publik

Buat blockchain publik atau pribadi Anda sendiri.

### Didesain untuk Keuangan

Dukungan asli untuk dengan mudah membuat dan memperdagangkan aset pintar digital dengan aturan khusus yang kompleks.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE2NDQ2MjI2LC0xNjQ5MTgzNTgxLC0xNj
QwMzg2MjI2LC00NjgyOTEwOTAsLTY1OTU1MzkzM119
-->