# Dokuman Dizini

Bu klasor, repodaki Markdown belgelerini daha okunabilir ve takip edilebilir halde tutmak icin kullanilir.

## Belge tipleri

- `donusturulmus not`: PDF'den Markdown'a alinmis, icerigi korunmus ama her zaman tam temizlenmemis belge
- `duzenlenmis teknik not`: okunabilirlik ve yapi acisindan toparlanmis belge
- `yardimci not`: ana raporu aciklayan veya baglam veren kisa belge

## Mevcut belgeler

| Belge | Tip | Konu | Iliskili PDF |
| --- | --- | --- | --- |
| [`baffle_WO_vanes_rapor.md`](./baffle_WO_vanes_rapor.md) | donusturulmus not | vane icermeyen baffle yapisinin temel mantigi | [`../pdf/baffle_WO_vanes_rapor.pdf`](../pdf/baffle_WO_vanes_rapor.pdf) |
| [`baffle_raporu_hakkinda.md`](./baffle_raporu_hakkinda.md) | yardimci not | baffle raporunun ne oldugunu ve ne olmadigini aciklayan baglam notu | - |
| [`CMOS_APS_PPD_star_tracker.md`](./CMOS_APS_PPD_star_tracker.md) | duzenlenmis teknik not | CMOS APS, PPD, sogurma fiziği ve star tracker etkileri | [`../pdf/CMOS_APS_PPD_star_tracker.pdf`](../pdf/CMOS_APS_PPD_star_tracker.pdf) |

## Gelecek kullanim kurali

Yeni bir teknik belge eklenirken mumkunse:

1. PDF surumu `../pdf/` altina eklenir.
2. Markdown surumu bu klasore eklenir.
3. Belgenin tipi acikca belirtilir.
4. Ana `README.md` ve bu dosya guncellenir.
