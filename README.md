---
deskripsi: >-
   Bangun di atas Avalanche. Bangun tanpa batas. Pengembang yang membangun di atas Avalanche
  dapat dengan mudah membuat aplikasi yang kuat, andal, dan aman.
---

# Dokumentasi Pengembang

## Getting Started

{% tabs %}
{% tab title="Coming From Ethereum?" %}
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

[Avalanche](https://avax.network) is an open-source platform for launching [decentralized applications](https://support.avalabs.org/en/articles/4587146-what-is-a-decentralized-application-dapp) and enterprise [blockchain](http://support.avalabs.org/en/articles/4064677-what-is-a-blockchain) deployments in one interoperable, highly scalable ecosystem. Avalanche gives you complete control on both the network and application layers–helping you build anything you can imagine.

A key difference between Avalanche and other decentralized networks is the consensus protocol. Over time, people have come to a false understanding that blockchains have to be slow and not scalable. The Avalanche protocol employs a novel approach to consensus to achieve its strong safety guarantees, quick finality, and high-throughput, without compromising decentralization.

## Avalanche \(AVAX\) Token

The Avalanche \(AVAX\) token is the native token of the Avalanche platform and is used to secure the network through staking, transact peer-to-peer, pay for fees, and provide a basic unit of account between the multiple subnetworks created on the Avalanche platform. `1 nAVAX` is equal to `0.000000001 AVAX`.

## Protokol Konsensus Avalanche

![Consensus Comparison](.gitbook/assets/consensus-comparison.png)

Protokol dalam keluarga Avalanche beroperasi melalui pemungutan suara sub-sampel berulang kali. Ketika sebuah [validator](http://support.avalabs.org/en/articles/4064704-what-is-a-blockchain-validator) sedang menentukan apakah [transaksi](http://support.avalabs.org/en/articles/4587384-what-is-a-transaction) harus diterima atau ditolak, ini menanyakan subset kecil validator acak apakah menurut mereka transaksi harus diterima atau ditolak. Jika validator yang ditanya menganggap transaksi tersebut tidak valid, telah menolak transaksi tersebut, atau lebih memilih transaksi yang bentrok, ia menjawab bahwa transaksi tersebut harus ditolak. Jika tidak, ia menjawab bahwa transaksi tersebut harus diterima.

Jika sebagian besar \(_alpha_ $$α$$\) dari validator mengambil sampel balasan yang menurut mereka transaksi harus diterima, validator lebih memilih untuk menerima transaksi. Artinya, ketika ditanya tentang transaksi di masa depan, ia akan menjawab bahwa transaksi tersebut harus diterima. Demikian pula, validator akan memilih untuk menolak transaksi jika sebagian besar validator menjawab bahwa mereka menganggap transaksi tersebut harus ditolak.

The validator repeats this sampling process until _alpha_ of the validators queried reply the same way \(accept or reject\) for _beta_ $$β$$ consecutive rounds.

In the common case when a transaction has no conflicts, finalization happens very quickly. When conflicts exist, honest validators quickly cluster around conflicting transactions, entering a positive feedback loop until all correct validators prefer that transaction. This leads to the acceptance of non-conflicting transactions and the rejection of conflicting transactions.

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

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYwOTAxODY2MiwtNjU5NTUzOTMzXX0=
-->