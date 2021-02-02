---
deskripsi: Pelajari lebih lanjut tentang biaya transaksi Avalanche
---

# Biaya transaksi

Untuk mencegah spam, transaksi di Avalanche memerlukan pembayaran biaya transaksi. Biaya dibayarkan [AVAX](../../#avalanche-avax-token). **Biaya transaksi dibakar \(dihancurkan selamanya\).**

Saat Anda mengeluarkan transaksi melalui Avalanche API, biaya transaksi secara otomatis dipotong dari salah satu alamat yang Anda kontrol.

## Jadwal Biaya

Jenis transaksi yang berbeda memerlukan pembayaran biaya transaksi yang berbeda pula. Tabel ini menunjukkan jadwal biaya transaksi:

{% hint style="warning" %}
[Rantai-C](./#contract-chain-c-chain) harga gas 4.7e-7 atau 0.00000047 AVAX/gas. Batas gas Rantai-C adalah 10e8 atau 1,000,000,000
{% endhint %}

```cpp
+----------+-------------------+------------------------+
| Rantai    : Tipe transaksi  | Biaya transaksi (AVAX) |
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
eyJoaXN0b3J5IjpbLTkwMjQxMDcyNV19
-->