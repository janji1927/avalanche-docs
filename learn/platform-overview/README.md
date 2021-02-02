---
deskripsi: Mempelajari konsep inti dan arsitektur Avalanche
---

# Tinjauan Platform

Avalanche memiliki 3 blockchain bawaan: [**Rantai Pertukaran \(X-Chain\)**](./#exchange-chain-x-chain), [**Platform Chain \(P-Chain\)**](./#platform-chain-p-chain), and [**Contract Chain \(C-Chain**\)](./#contract-chain-c-chain). All 3 blockchains are [validated](http://support.avalabs.org/en/articles/4064704-what-is-a-blockchain-validator) and secured by the [**Primary Network**](http://support.avalabs.org/en/articles/4135650-what-is-the-primary-network). The Primary Network is a special [subnet](http://support.avalabs.org/en/articles/4064861-what-is-a-subnetwork-subnet), and all members of all custom subnets must also be a member of the Primary Network by staking at least 2,000 AVAX.

Here are tutorials on [creating a subnet](../../build/tutorials/platform/create-a-subnet.md) and [adding validators](../../build/tutorials/nodes-and-staking/add-a-validator.md) to a subnet.

![Primary network](../../.gitbook/assets/primary-network.png)

## Subnets

**Subnet**, atau subnetwork, adalah kumpulan validator dinamis yang bekerja bersama untuk mencapai konsensus tentang status kumpulan blockchain. Setiap blockchain divalidasi oleh satu subnet. Subnet dapat memvalidasi banyak blockchain. Sebuah node bisa menjadi anggota dari banyak subnet.

Subnet mengelola keanggotaannya sendiri, dan mungkin mengharuskan validator konstituennya memiliki properti tertentu. Ini sangat berguna, dan kami mengeksplorasi konsekuensinya secara lebih mendalam di bawah ini:

### Pemenuhan

Arsitektur subnet Avalanche membuat kepatuhan peraturan dapat dikelola. Seperti disebutkan di atas, subnet mungkin memerlukan validator untuk memenuhi serangkaian persyaratan.

Beberapa contoh termasuk:

* Validator harus berlokasi di negara tertentu
* Validator harus lulus pemeriksaan KYC/AML
* Validator harus memiliki lisensi tertentu

### Dukungan untuk Blockchain Pribadi

Anda dapat membuat subnet di mana hanya validator yang telah ditentukan sebelumnya yang dapat bergabung dan membuat subnet pribadi di mana konten blockchain hanya akan terlihat oleh validator tersebut. Ini sangat ideal untuk organisasi yang tertarik untuk merahasiakan informasi mereka.

### Pemisahan Masalah

Dalam jaringan blockchain yang heterogen, beberapa validator tidak ingin memvalidasi blockchain tertentu karena mereka tidak tertarik dengan blockchain tersebut. Model subnet memungkinkan validator untuk hanya memperhatikan diri mereka sendiri dengan blockchain yang mereka pedulikan. Ini mengurangi beban validator.

### Persyaratan Khusus Aplikasi

Aplikasi berbasis blockchain yang berbeda mungkin memerlukan validator untuk memiliki properti tertentu. Misalkan ada aplikasi yang membutuhkan RAM atau CPU power dalam jumlah besar. Subnet mungkin mengharuskan validator memenuhi persyaratan [perangkat keras tertentu](http://support.avalabs.org/en/articles/4064879-technical-requirements-for-running-a-validator-node-on-avalanche) sehingga aplikasi tidak mengalami kinerja rendah karena validator lambat.

## Mesin virtual

A **Mesin Virtual** \(VM\) mendefinisikan logika tingkat aplikasi dari sebuah blockchain. Dalam istilah teknis, ini menentukan status blockchain, fungsi transisi status, transaksi, dan API di mana pengguna dapat berinteraksi dengan blockchain. Setiap blockchain di Avalanche adalah instance dari VM.

Saat menulis VM, Anda tidak perlu memikirkan logika tingkat rendah seperti jaringan, konsensus, dan struktur blockchain. Avalanche melakukan ini di belakang layar sehingga Anda dapat fokus pada hal yang ingin Anda bangun.

Pikirkan VM sebagai cetak biru untuk blockchain; Anda dapat menggunakan VM yang sama untuk membuat banyak blockchain, yang masing-masing mengikuti kumpulan aturan yang sama tetapi secara logis tidak bergantung pada blockchain lainnya.

### Mengapa Mesin Virtual?

Pada awalnya, jaringan blockchain memiliki satu Mesin Virtual \(VM\) dengan serangkaian fungsionalitas statis yang telah ditentukan sebelumnya. Desain yang kaku dan monolitik ini membatasi aplikasi berbasis blockchain yang dapat dijalankan seseorang di jaringan tersebut.

Orang yang menginginkan aplikasi terdesentralisasi khusus harus membuat jaringan blockchain mereka sendiri yang sepenuhnya baru dari awal. Melakukan hal itu membutuhkan banyak waktu dan usaha, menawarkan keamanan terbatas, dan umumnya menghasilkan blockchain yang dipesan lebih dahulu dan rapuh yang tidak pernah diluncurkan.

Ethereum mengambil langkah untuk menyelesaikan masalah ini dengan kontrak pintar. Pengembang tidak perlu khawatir tentang jaringan dan konsensus, tetapi membuat aplikasi terdesentralisasi masih sulit. VM Ethereum memiliki kinerja rendah dan memberlakukan batasan pada pengembang kontrak pintar. Soliditas dan beberapa bahasa lain untuk menulis kontrak pintar Ethereum masih asing bagi sebagian besar pemrogram.

Avalanche VMs \(AVMs\) memudahkan untuk menentukan aplikasi desentralisasi berbasis blockchain. Daripada bahasa baru dan terbatas seperti Solidity, developer dapat menulis VM di Go \(bahasa lain akan didukung di masa mendatang\).

### Membuat Blockchain dan Mesin Virtual Anda

Avalanche belum mendukung pembuatan Mesin Virtual baru \(VMs\). Saat ini, Avalanche hanya mendukung pembuatan instance baru dari Avalanche VM.

{% page-ref page="../../build/tutorials/platform/create-a-new-blockchain.md" %}

Di masa mendatang, Avalanche akan memungkinkan Anda untuk menentukan dan meluncurkan blockchain khusus, dan kami akan merilis SDK untuk membantu Anda melakukannya.

{% page-ref page="../../build/tutorials/platform/create-a-virtual-machine-vm.md" %}

## Rantai Pertukaran \(X-Chain\)

**X-Chain** bertindak sebagai platform terdesentralisasi untuk membuat dan memperdagangkan aset pintar digital, representasi dari sumber daya dunia nyata \(misalnya, ekuitas, obligasi\) dengan seperangkat aturan yang mengatur perilakunya, seperti "tidak bisa diperdagangkan sampai besok "atau" hanya bisa dikirim ke warga AS".

Satu aset yang diperdagangkan di X-Chain adalah AVAX. Saat Anda mengeluarkan transaksi ke blockchain di Avalanche, Anda membayar biaya dalam mata uang AVAX.

X-Chain adalah turunan dari Mesin Virtual Avalanche (AVM). Itu [X-Chain API](../../build/avalanchego-apis/exchange-chain-x-chain-api.md) memungkinkan klien untuk membuat dan memperdagangkan aset di X-Chain dan contoh AVM lainnya.

{% page-ref page="../../build/tutorials/smart-digital-assets/create-a-fix-cap-asset.md" %}

## Rantai Platform \(Rantai-P\)


P-Chain adalah blockchain metadata di Avalanche dan mengoordinasikan validator, melacak subnet aktif, dan memungkinkan pembuatan subnet baru. P-Chain mengimplementasikan. [protokol konsensus Snowman](../../#snowman-consensus-protocol).

[P-Chain API](../../build/avalanchego-apis/platform-chain-p-chain-api.md) memungkinkan klien untuk membuat subnet, menambahkan validator ke subnet, dan membuat blockchain.

## Rantai Kontrak \(C-Chain\)

C-Chain memungkinkan pembuatan kontrak pintar menggunakan [C-Chain’s API](../../build/avalanchego-apis/contract-chain-c-chain-api.md).

C-Chain adalah mesin virtual dari Mesin Virtual Ethereum yang didukung oleh [Avalanche](../../).

<!--stackedit_data:
eyJoaXN0b3J5IjpbODQ5ODQ0NTU5LDM3NzEyMjYzMiwtMTA2NT
A1ODk0OCwtMjA0NzQ5MzAxNywxOTIwMDU4OTMyLC03NzM0NTAy
NTYsMTM4MjEyMzUyNV19
-->