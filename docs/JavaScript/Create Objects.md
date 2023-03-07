---
sidebar_position: 1
---

#### JavaScript'te nesne oluşturmanın yolları nelerdir ?

Aşağıdaki gibi JavaScript'te nesne oluşturmanın birçok yolu vardır.

### **Object constructor**

Boş bir nesne oluşturmanın en basit yolu, Object constructor kullanmaktır. Şu anda bu yaklaşım önerilmiyor.

```bash
  let object = new Object();
```

`new Object( )` yaklaşımının önerilmemesinin nedeni daha okunaklı ve daha performanslı alternatiflerinin bulunmasından dolayıdır.

### **Object's create method**

Object'in create yöntemi, prototip nesnesini parametre olarak ileterek yeni bir nesne oluşturur.

```bash
let object = Object.create(null);
```

### **Object literal syntax**

Nesne literal sözdizimi (veya object initializer), süslü parantezlerle `{ }` çevrelenmiş virgülle ayrılmış bir ad-değer (name - value) çiftleri kümesidir.

```bash
let object = {
  name:'Tolga',
}
```

Oluşturulan nesne literal property değerleri dizi, fonksiyon ve iç içe geçmiş nesne de dahil olmak üzere herhangi bir veri türü olabilir.

**Note :** Nesne oluşturmanın en kolay yoludur.

### **Function constructor**

Fonksiyon ile birlikte new operatörüyle nesne oluşturma

```bash
  function Person(name) {
    this.name = name;
    this.age = 21;
  }

  let object = new Person("Tolga");
```

### **Function constructor with prototype**

Function constructor ile benzerdir prototype ve methods için protip kullanılır.

```bash
  function() {
    Person.prototype.name = "Tolga";
    let object = new Person();
  }
```

```bash
  function func() {
    new func(x, y, y)
  }
```

**(ya da)**

```bash
let newInstance = Object.create(func.prototype)

let result = func.call(newInstance,x,y,z)

console.log(result && typeof result === 'object' ? result : newInstance);
```

### **ES6 Class syntax**

```bash
  class Person {
    constructor(name) {
      this.name = name;
    }
  }

  let object = new Person("Tolga");
```

### **Singleton Pattern**

```bash
  let object = new (function (){
    this.name = "Tolga";
  })();
```

**Note:** Singleton, bir nesnenin yalnızca bir kez örneklendirilebildiği bir tasarım kalıbıdır. Yapıcısına yapılan ardışık çağrılar yeni bir nesne yerine aynı örneği döndürür ve bu sayede nesnenin sadece bir örneği oluşturulur.

[Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)
