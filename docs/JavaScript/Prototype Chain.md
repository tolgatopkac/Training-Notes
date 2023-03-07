---
sidebar_position: 2
---

#### Prototip zinciri nedir ?

![Prototip zinciri](./img/prototype_chain.png)

JavaScript'te her nesnenin bir prototip zinciri (prototype chain) vardır. Bu, nesnelerin prototip özelliklerini diğer nesnelere aktarmasına olanak sağlar.

Bir prototip zinciri, bir nesnenin prototipinin diğer bir nesne olduğu ve prototip zincirindeki tüm nesnelerin birbirine bağlı olduğu bir zincirdir.

Örneğin, bir nesne oluşturulduğunda, bu nesnenin prototipi Object.prototype'dir. Object.prototype nesnesi de kendi prototipine sahiptir, bu nedenle prototip zinciri bu şekilde devam eder.

Bir nesne üzerindeki bir özellik veya yöntem çağrısı yapıldığında, önce nesne üzerinde bu özellik veya yöntem aranır. Eğer özellik veya yöntem nesnede bulunamazsa, prototip zincirindeki diğer nesnelere bakılır ve bu şekilde özellik veya yöntem aranır. Bu işlem, zincirin sonuna kadar devam eder ve eğer özellik veya yöntem hiçbir nesnede bulunamazsa, sonuç undefined veya null olur.

Prototip zinciri, JavaScript'te kalıtımı mümkün kılar ve nesneler arasındaki ilişkileri kolaylaştırır.

```bash
  #  Bir Tool sınıfı oluşturalım
  function Tool(name, price){
    this.name = name;
    this.price = price;
  }

  # Tool sınıfına özellik ekleyelim.
  Tool.prototype.description = function (){
    return "This is a " + this.name + " which costs $" + this.price + ".";
  }

  # Saw sınıfı oluşturalım ve Tool sınıfından kalıtalım
  function Saw(name, price, teeth) {
    Tool.call(this, name, price);
    this.teeth = teeth;
  }

  # Saw sınıfına prototip özellikleri ekleyelim
  Saw.prototype = Object.create(Tool.prototype);
  Saw.prototype.constructor = Saw;
  Saw.prototype.description = function (){
    return "This is a " + this.name + " saw with " + this.teeth + " teeth, which costs $" + this.price + ".";
  };

  #  Yeni bir Test Saw nesnesi oluşturalım
  let testSaw = new Saw("Test Saw", 25.00, 8);

  #  testSaw nesnesinin description() metodunu çağıralım
  console.log(testSaw.description());
```

Bu örnekte, "Tool" sınıfı ve "Saw" sınıf oluşturuyoruz. "Saw" sınıfı "Tool" sınıfından kalıtım alır ve yeni özellikler ekler. "Saw" sınıfının prototipinde, "description()" adlı yeni bir özellik ekliyoruz ve bu özelliği "Tool" sınıfndan kalıtım alıyoruz.

Daha sonra, "testSaw" adlı bir "Saw" nesnesi oluşturuyoruz ve "description()" metodu çağırıyoruz. Bu metodu çağırdığımızda, JavaScript prototip zincirini takip ederek önce "Saw" sınıfındaki metodu arar, eğer bulamazsa "Tool" sınıfındaki metodu arar ve sonunda bir sonuç döndürür. Bu örnek, prototip zincirini kullanarak nesneler arasında özelliklerin ve yöntemlerin paylaşımını göstermektedir.
