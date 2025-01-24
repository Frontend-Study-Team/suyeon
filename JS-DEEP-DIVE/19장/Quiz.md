### **Level.1** 🌱

1. **프로토타입 생성**  
   다음 코드 실행 후, `Person.prototype`과 `john.__proto__`가 같은지 확인하는 코드를 작성하시오.  
   ```javascript
   function Person(name) {
     this.name = name;
   }
   const john = new Person("John");
   ```

2. **Object.create**  
   다음 코드의 출력값은 무엇인가요?  
   ```javascript
   const parent = { role: "parent" };
   const child = Object.create(parent);
   child.role = "child";

   console.log(child.role); // ?
   delete child.role;
   console.log(child.role); // ?
   ```

3. **`__proto__`와 `prototype` 차이**  
   - `__proto__`와 `prototype`의 차이를 간단히 설명하시오.

---

### **Level.2** 🌟

4. **프로토타입 체인**  
   다음 코드에서 `obj.sayHello()`를 호출하면 무엇이 출력되나요?  
   ```javascript
   const parent = { sayHello: () => "Hello from parent" };
   const child = Object.create(parent);
   child.sayHello = () => "Hello from child";

   const obj = Object.create(child);
   console.log(obj.sayHello()); // ?
   ```

5. **오버라이딩**  
   다음 코드에서 `obj.toString()`을 호출하면 무엇이 출력되나요?  
   ```javascript
   const obj = { value: 42 };
   obj.toString = function () {
     return `Value is ${this.value}`;
   };
   console.log(obj.toString()); // ?
   ```

---

### **Level.3** 🚀

6. **instanceof 연산자**  
   다음 코드의 결과를 설명하시오.  
   ```javascript
   function Animal() {}
   function Dog() {}

   Dog.prototype = Object.create(Animal.prototype);
   const myDog = new Dog();

   console.log(myDog instanceof Dog); // ?
   console.log(myDog instanceof Animal); // ?
   console.log(myDog instanceof Object); // ?
   ```

7. **정적 메서드**  
   다음 코드의 출력값은 무엇인가요?  
   ```javascript
   class Calculator {
     static add(a, b) {
       return a + b;
     }
   }
   const calc = new Calculator();
   console.log(Calculator.add(3, 4)); // ?
   console.log(calc.add(3, 4)); // ?
   ```

---

### **Level.4** 🧠

8. **프로퍼티 새도잉**  
   다음 코드의 결과를 설명하시오.  
   ```javascript
   const obj = {
     get value() {
       return 42;
     },
   };
   obj.value = 50;

   console.log(obj.value); // ?
   ```

9. **프로토타입 체인과 속성 탐색**  
   다음 코드의 출력값을 예측하시오.  
   ```javascript
   function Parent() {
     this.role = "parent";
   }
   Parent.prototype.sayRole = function () {
     return `Role: ${this.role}`;
   };

   function Child() {
     Parent.call(this);
     this.role = "child";
   }
   Child.prototype = Object.create(Parent.prototype);
   Child.prototype.constructor = Child;

   const child = new Child();
   console.log(child.sayRole()); // ?
   ```

---

