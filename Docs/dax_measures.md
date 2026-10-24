# Measure DAX

Measure berikut digunakan untuk menganalisis nasabah bertransaksi ulang dan biaya transaksi. Measure biaya hanya menampilkan nominal ketika satu mata uang dipilih.

## Nasabah_Bertransaksi_Ulang

```DAX
=COUNTROWS(
    FILTER(
        VALUES(
            'FP20Analytcis_Banking_Dataset_Challenge27_English'[CustomerID]
        ),
        CALCULATE(
            COUNTROWS(
                'FP20Analytcis_Banking_Dataset_Challenge27_English'
            ),
            ALL(
                'FP20Analytcis_Banking_Dataset_Challenge27_English'[ProductCategory]
            )
        ) >= 2
    )
)
```

**Arti:** Menghitung jumlah nasabah dengan minimal dua transaksi, sesuai filter yang aktif. Penghitungan transaksi per nasabah mencakup seluruh kategori produk.

## Total_Biaya_Kartu_Kredit

```DAX
=IF(
    HASONEVALUE(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'[Currency]
    ),
    SUM(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'[CreditCardFees]
    ),
    BLANK()
)
```

**Arti:** Menjumlahkan `CreditCardFees` untuk mata uang yang dipilih. Hasil kosong jika belum tepat satu mata uang yang dipilih.

## Total_Biaya_Asuransi

```DAX
=IF(
    HASONEVALUE(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'[Currency]
    ),
    SUM(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'[InsuranceFees]
    ),
    BLANK()
)
```

**Arti:** Menjumlahkan `InsuranceFees` untuk mata uang yang dipilih. Hasil kosong jika belum tepat satu mata uang yang dipilih.

## Total_Biaya_Keterlambatan

```DAX
=IF(
    HASONEVALUE(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'[Currency]
    ),
    SUM(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'[LatePaymentAmount]
    ),
    BLANK()
)
```

**Arti:** Menjumlahkan `LatePaymentAmount` untuk mata uang yang dipilih. Hasil kosong jika belum tepat satu mata uang yang dipilih.

## Jumlah_Transaksi_Biaya_Keterlambatan

```DAX
=CALCULATE(
    COUNTROWS(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'
    ),
    'FP20Analytcis_Banking_Dataset_Challenge27_English'[LatePaymentAmount] > 0
)
```

**Arti:** Menghitung transaksi dengan `LatePaymentAmount` lebih dari nol, sesuai filter yang aktif.

## Persentase_Transaksi_Biaya_Keterlambatan

```DAX
=DIVIDE(
    [Jumlah_Transaksi_Biaya_Keterlambatan],
    COUNTROWS(
        'FP20Analytcis_Banking_Dataset_Challenge27_English'
    ),
    0
)
```

**Arti:** Menghitung persentase transaksi yang memiliki biaya keterlambatan dibandingkan seluruh transaksi pada filter aktif. Hasilnya ditampilkan sebagai persentase.