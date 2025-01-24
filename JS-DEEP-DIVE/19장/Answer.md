### **Level.1 🌱**

1. **프로토타입 생성**
   ```javascript
   function Person(name) {
     this.name = name;
   }
   const john = new Person("John");

   console.log(Person.prototype === john.__proto__); // true
   ```
   - **이유**:  
     생성자 함수 `Person`으로 생성된 객체 `john`의 `__proto__`는 `Person.prototype`을 참조한다. 이는 프로토타입 체인의 기본 동작으로, 객체는 자신의 생성자 함수의 `prototype`과 연결된다.

---

2. **Object.create**
   ```javascript
   const parent = { role: "parent" };
   const child = Object.create(parent);
   child.role = "child";

   console.log(child.role); // "child"
   delete child.role;
   console.log(child.role); // "parent"
   ```
   - **이유**:  
     `child.role = "child";`로 인해 `child` 객체에 자체 속성이 생성된다. 하지만 `delete child.role;`로 이 속성을 삭제하면, 프로토타입 체인을 통해 `parent` 객체의 `role` 속성을 참조하게 된다.

---

3. **`__proto__`와 `prototype`의 차이**
   - **`__proto__`**: 객체의 실제 프로토타입을 가리킨다. 모든 객체가 `__proto__`를 통해 자신의 프로토타입에 접근할 수 있다.
   - **`prototype`**: 생성자 함수에만 존재하는 속성으로, 생성자를 통해 생성된 객체들의 공통 프로토타입을 정의한다.

---

### **Level.2 🌟**

4. **프로토타입 체인**
   ```javascript
   const parent = { sayHello: () => "Hello from parent" };
   const child = Object.create(parent);
   child.sayHello = () => "Hello from child";

   const obj = Object.create(child);
   console.log(obj.sayHello()); // "Hello from child"
   ```
   - **이유**:  
     `obj`에는 `sayHello` 메서드가 없으므로 프로토타입 체인을 따라 `child`에서 `sayHello`를 찾는다. 따라서 `child`의 `sayHello`가 실행된다.

---

5. **오버라이딩**
   ```javascript
   const obj = { value: 42 };
   obj.toString = function () {
     return `Value is ${this.value}`;
   };
   console.log(obj.toString()); // "Value is 42"
   ```
   - **이유**:  
     `toString` 메서드는 객체의 기본 메서드로, 오버라이딩하여 커스텀 로직을 정의할 수 있다. `obj.toString` 호출 시 오버라이딩된 메서드가 실행된다.

---

### **Level.3 🚀**

6. **instanceof 연산자**
   ```javascript
   function Animal() {}
   function Dog() {}

   Dog.prototype = Object.create(Animal.prototype);
   const myDog = new Dog();

   console.log(myDog instanceof Dog); // true
   console.log(myDog instanceof Animal); // true
   console.log(myDog instanceof Object); // true
   ```
   - **이유**:  
     - `myDog instanceof Dog`: `Dog.prototype`과 연결되어 있으므로 true.
     - `myDog instanceof Animal`: `Animal.prototype`이 프로토타입 체인 상에 존재하므로 true.
     - `myDog instanceof Object`: 모든 객체는 최상위 프로토타입인 `Object.prototype`과 연결되므로 true.

---

7. **정적 메서드**
   ```javascript
   class Calculator {
     static add(a, b) {
       return a + b;
     }
   }
   const calc = new Calculator();
   console.log(Calculator.add(3, 4)); // 7
   console.log(calc.add(3, 4)); // TypeError
   ```
   - **이유**:  
     정적 메서드는 클래스에 직접 연결되며, 인스턴스에는 포함되지 않는다. 따라서 `Calculator.add`는 호출 가능하지만, `calc.add`는 호출할 수 없다.

---

### **Level.4 🧠**

8. **프로퍼티 새도잉**
   ```javascript
   const obj = {
     get value() {
       return 42;
     },
   };
   obj.value = 50;

   console.log(obj.value); // 42
   ```
   - **이유**:  
     `get value()`는 접근자 프로퍼티로 정의되며, 새로운 데이터 프로퍼티 `value`를 추가해도 접근자 프로퍼티가 우선된다.

---

9. **프로토타입 체인과 속성 탐색**
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
   console.log(child.sayRole()); // "Role: child"
   ```
   - **이유**:  
     `Parent.call(this);`로 인해 `Child` 생성자에서 `this.role`이 "child"로 설정된다. `sayRole`은 프로토타입 체인을 따라 `Parent.prototype`에서 찾은 메서드로 실행된다. 메서드 내부의 `this.role`은 `child` 객체의 `role`을 참조하므로 "Role: child"가 출력된다.

---

<br>
