---
sidebar_position: 4
---

### JSON nedir ?

JSON (JavaScript Object Notation), verileri depolamak ve taşımak için yaygın olarak kullanılan bir veri biçimidir. JSON, insanlar ve makinalar tarafından okunabilir, kolayca anlaşılır yapıya sahiptir ve JavaScript programlama dilinde nesnelerin oluşturulması için kullanılan sözdizimine benzer.

#### JSON ile yapılabilecek en yaygın işlemler şunlardır :

- Veri oluşturma : JSON, verileri nesne ve dizi olarak tanımlamanıza olanak tanır. Örneğin :

```bash
  {
    "name": "Tolga",
    "address": {
      "city": "Kocaeli",
      "country": "Turkey"
    }
  };
```

- Veri okuma (parse): JSON verileri, JavaScript'te nesne olarak okunabilir. Bu nedenle, JSON verileri `JSON.parse()` yöntemiyle işlenerek **nesnelere** dönüştürülebilir ve ardından özelliklerine erişilebilir.

```bash
  const json = '{"name": "Ali", "age": 52}'
  const person = JSON.parse(json);


  console.log(person.name) # Ali
  console.log(person.age) # 42
```

- Stringification (veri yazma) : JSON verileri `JSON.stringify()` yöntemiyle bir JavaScript nesnesinden JSON dizgisine dönüştürülebilir.
