---
deskripsi: Mempelajari konsep inti dan arsitektur Avalanche
---

# Tinjauan Platform

Avalanche features 3 built-in blockchains: [**Exchange Chain \(X-Chain\)**](./#exchange-chain-x-chain), [**Platform Chain \(P-Chain\)**](./#platform-chain-p-chain), and [**Contract Chain \(C-Chain**\)](./#contract-chain-c-chain). All 3 blockchains are [validated](http://support.avalabs.org/en/articles/4064704-what-is-a-blockchain-validator) and secured by the [**Primary Network**](http://support.avalabs.org/en/articles/4135650-what-is-the-primary-network). The Primary Network is a special [subnet](http://support.avalabs.org/en/articles/4064861-what-is-a-subnetwork-subnet), and all members of all custom subnets must also be a member of the Primary Network by staking at least 2,000 AVAX.

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

Think of a VM as a blueprint for a blockchain; you can use the same VM to create many blockchains, each of which follows the same ruleset but is logically independent of other blockchains.

### Why Virtual Machines?

At first, blockchain networks had one Virtual Machine \(VM\) with a pre-defined, static set of functionality. This rigid, monolithic design limited what blockchain-based applications one could run on such networks.

People who wanted custom decentralized applications had to create their own, entirely new blockchain network from scratch. Doing so required a great deal of time and effort, offered limited security, and generally resulted in a bespoke, fragile blockchain that never got off the ground.

Ethereum made a step toward solving this problem with smart contracts. Developers didn’t need to worry about networking and consensus, but creating decentralized applications was still hard. The Ethereum VM has low performance and imposes restrictions on smart contract developers. Solidity and the other few languages for writing Ethereum smart contracts are unfamiliar to most programmers.

Avalanche VMs \(AVMs\) make it easy to define a blockchain-based decentralized application. Rather than new, limited languages like Solidity, developers can write VMs in Go \(other languages will be supported in the future\).

### Creating Your Blockchain and Virtual Machine

Avalanche does not yet support the creation of new Virtual Machines \(VMs\). Presently, Avalanche only supports the creation of new instances of the Avalanche VM.

{% page-ref page="../../build/tutorials/platform/create-a-new-blockchain.md" %}

In the future, Avalanche will allow you to define and launch custom blockchains, and we’ll release SDKs to help you do so.

{% page-ref page="../../build/tutorials/platform/create-a-virtual-machine-vm.md" %}

## Exchange Chain \(X-Chain\)

The **X-Chain** acts as a decentralized platform for creating and trading digital smart assets, a representation of a real-world resource \(e.g., equity, bonds\) with a set of rules that govern its behavior, like “can’t be traded until tomorrow” or “can only be sent to US citizens.”

One asset traded on the X-Chain is AVAX. When you issue a transaction to a blockchain on Avalanche, you pay a fee denominated in AVAX.

The X-Chain is an instance of the Avalanche Virtual Machine \(AVM\). The [X-Chain API](../../build/avalanchego-apis/exchange-chain-x-chain-api.md) allows clients to create and trade assets on the X-Chain and other instances of the AVM.

{% page-ref page="../../build/tutorials/smart-digital-assets/create-a-fix-cap-asset.md" %}

## Platform Chain \(P-Chain\)

The **P-Chain** is the metadata blockchain on Avalanche and coordinates validators, keeps track of active subnets, and enables the creation of new subnets. The P-Chain implements the [Snowman consensus protocol](../../#snowman-consensus-protocol).

The [P-Chain API](../../build/avalanchego-apis/platform-chain-p-chain-api.md) allows clients to create subnets, add validators to subnets, and create blockchains.

## Contract Chain \(C-Chain\)

The **C-Chain** allows for the creation smart contracts using the [C-Chain’s API](../../build/avalanchego-apis/contract-chain-c-chain-api.md).

The C-Chain is an instance of the Ethereum Virtual Machine powered by [Avalanche](../../).

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4ODQwNjc2OCwxMzgyMTIzNTI1XX0=
-->