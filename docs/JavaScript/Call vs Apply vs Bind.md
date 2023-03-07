---
sidebar_position: 3
---

#### Call, Apply ve Bind arasındaki farklar nelerdir ?

`call( ):` yöntemi, bir fonksiyonu çağırmak ve bu fonksiyonu belirli bir nesneye bağlamak için kullanılır. Fonksiyona iletilen ilk argüman, fonksiyon içinde kullanılacak `this` anahtar kelimesinin değerini belirler.

```bash
  let employee1 = {firstName: "John", lastName:"Rodson"};
  let employee2 = {firstName: "Jimmy", lastName: "Baily"};

  function invite(greetingMsg1, greetingMsg2) {
    console.log(greetingMsg1 + " " + this.firstName + " " + this.lastName + " ", + greetingMsg2);
  }

  invite.call(employee1, "Hello", "How are you?");  # Hello John Rodson, How are you?
  invite.call(employee2, "Hello", "How are you?"); # Hello Jimmy Baily, How are you?

```

`apply ( ): ` yöntemi `call()` yöntemi gibi, bir fonksiyonu çağırmak ve belirli bir nesneye bağlamak için kullanılır. Ancak, `call( )` farklı olarak argüman olarak array iletilir.

```bash
  let employee1 = {firstName: "John", lastName:"Rodson"};
  let employee2 = {firstName: "Jimmy", lastName: "Baily"};

  function invite(greetingMsg1, greetingMsg2) {
    console.log(greetingMsg1 + " " + this.firstName + " " + this.lastName + " ", + greetingMsg2);
  }

  invite.call(employee1, ["Hello", "How are you?"]);  # Hello John Rodson, How are you?
  invite.call(employee2, ["Hello", "How are you?"]); # Hello Jimmy Baily, How are you?

```

`bind( ):` İletilen argüman sayısı fark etmeksizin yeni bir fonksiyon döndürür.

```bash
  let employee1 = {firstName: "John", lastName:"Rodson"};
  let employee2 = {firstName: "Jimmy", lastName: "Baily"};

  function invite(greetingMsg1, greetingMsg2) {
    console.log(greetingMsg1 + " " + this.firstName + " " + this.lastName + " ", + greetingMsg2);
  }

  let inviteEmployee1 = invite.bind(employee1);
  let inviteEmployee2 = invite.bind(employee2);
  inviteEmployee1("Hello", "How are you?"); // Hello John Rodson, How are you?
  inviteEmployee2("Hello", "How are you?"); // Hello Jimmy Baily, How are you?

```

Özet olarak

- `call()` ve `apply()` yöntemleri, fonksiyonu çağırmak ve belirli bir nesneye bağlamak için kullanılırken, `bind()` yöntemi yalnızca bir fonksiyonu bir nesneye bağlamak için kullanılır.

- `call()` yöntemi, argümanları virgülle ayrılmış şekilde alırken, `apply()` yöntemi argümanları bir array olarak alır.

- `call()` ve `apply()` yöntemleri fonksiyonu doğrudan çağırırken, `bind()` yöntemi bir fonksiyon döndürür ve bu fonksiyon çağrıldığında çalışır.
