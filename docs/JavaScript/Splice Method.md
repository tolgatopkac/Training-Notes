---
sidebar_position: 6
---

#### Array Splice Method kullanımı

`splice()` methodu, bir array'de eleman ekleme/silme işlemlerini yapmak için kullanılır ve daha sonra silinen elemanı döndürür. İlk argüman, ekleme veya silme için dizi elemanının konumunu belirtirken, isteğe bağlı olan ikinci argüman silinecek öğe sayısını belirtir. Devamında (0,1 ,....) eklenecek olan optional argümanlar array'in elemanı olarak eklenir. 3. Örnek ❗

```bash

let array = [1,2,3,4,5];

let arraySliceOne = array.splice(0,2); # returns [1,2]; original array : [3, 4, 5];

let arraySliceTwo = array.splice(3); # return [4,5]; original array : [1, 2, 3];

let arraySliceThree = array.splice(3, 1, "a", "b", "c"); #❗ return [4]; original array: [1, 2, 3, "a", "b", "c", 5];

```

❗ **Note:** : Splice methodu orijinal array'i değiştirir ve silinen elemanları döndürür.
