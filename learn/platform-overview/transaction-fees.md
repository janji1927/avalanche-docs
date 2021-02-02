---
deskripsi: Pelajari lebih lanjut tentang biaya transaksi Avalanche
---

# Biaya transaksi

Untuk mencegah spam, transaksi di Longsor memerlukan pembayaran biaya transaksi. Biaya dibayarkan [AVAX](../../#avalanche-avax-token). **The transaction fee is burned \(destroyed forever\).**

When you issue a transaction through Avalanche’s API, the transaction fee is automatically deducted from one of the addresses you control.

## Fee Schedule

Different types of transactions require payment of a different transaction fee. This table shows the transaction fee schedule:

{% hint style="warning" %}
The [C-Chain](./#contract-chain-c-chain) gas price is 4.7e-7 or 0.00000047 AVAX/gas. The C-Chain gas limit is 10e8 or 1,000,000,000
{% endhint %}

```cpp
+----------+-------------------+------------------------+
| Chain    : Transaction Type  | Transaction Fee (AVAX) |
+----------+-------------------+------------------------+
| P        : Create Blockchain |                   0.01 |
+----------+-------------------+------------------------+
| P        : Add Validator     |                      0 |
+----------+-------------------+------------------------+
| P        : Add Delegator     |                      0 |
+----------+-------------------+------------------------+
| P        : Create Subnet     |                   0.01 |
+----------+-------------------+------------------------+
| P        : Import AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| P        : Export AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| X        : Send              |                  0.001 |
+----------+-------------------+------------------------+
| X        : Create Asset      |                   0.01 |
+----------+-------------------+------------------------+
| X        : Mint Asset        |                  0.001 |
+----------+-------------------+------------------------+
| X        : Import AVAX       |                  0.001 |
+----------+-------------------+------------------------+
| X        : Export AVAX       |                  0.001 |
+----------+-------------------+------------------------+
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzM4MjMzMDRdfQ==
-->