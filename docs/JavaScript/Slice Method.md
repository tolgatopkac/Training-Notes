---
sidebar_position: 5
---

#### Array Slice Method kullanımı

`slice()` methodu, bir array içindeki belirli elemanları seçerek yeni bir array nesnesi olarak döndürür. Bu method, verilen başlangıç argümanından başlayarak, isteğe bağlı olarak bitiş argümanına kadar olan elemanları **son elemanı dahil etmeden** seçer. İkinci argüman belirtilmezse seçim işlemi array'in sonuna kadar devam eder.

```bash
let array = [1,2,3,4,5];

let arraySliceOne = array.slice(0,2); # returns [1,2]

let arraySliceTwo = array.slice(2,3); # return [3];

let arraySliceThree = array.slice(4); # return [5]

```

**❗ Not:** Slice methodu orijinal array'i değiştirmez. Yeni bir array döndürür..
