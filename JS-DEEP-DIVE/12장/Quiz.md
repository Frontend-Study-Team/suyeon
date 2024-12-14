
### **📝 퀴즈 1: 함수 선언문과 표현식**


```jsx
console.log(add(2, 3)); // ❓
console.log(subtract(5, 2)); // ❓

function add(x, y) {
  return x + y;
}

const subtract = function (x, y) {
  return x - y;
};

```

---

### **📝 퀴즈 2: 화살표 함수**


```jsx
const multiply = (x, y) => x * y;

console.log(multiply(3, 4)); // ❓

```

---

### **📝 퀴즈 3: 매개변수 기본값**

```jsx
function greet(name = "Guest") {
  return `Hello, ${name}!`;
}

console.log(greet("Alice")); // ❓
console.log(greet());        // ❓

```

---

### **📝 퀴즈 4: arguments 객체**

```jsx
function sum() {
  let total = 0;
  for (let i = 0; i < arguments.length; i++) {
    total += arguments[i];
  }
  return total;
}

console.log(sum(1, 2, 3, 4)); // ❓

```

---

### **📝 퀴즈 5: 함수 표현식과 화살표 함수의 차이**

```jsx
const person = {
  name: "Alice",
  sayHello: function () {
    console.log(`Hello, ${this.name}!`);
  },
  arrowHello: () => {
    console.log(`Hello, ${this.name}!`);
  }
};

person.sayHello(); // ❓
person.arrowHello(); // ❓

```

---

### **📝 퀴즈 6: 함수의 반환값**

```jsx
function makeAdder(x) {
  return function (y) {
    return x + y;
  };
}

const add5 = makeAdder(5);
console.log(add5(3)); // ❓
console.log(add5(10)); // ❓
 
```

---

### **📝 퀴즈 7: 즉시 실행 함수 (IIFE)**

```jsx
(function () {
  console.log("IIFE is running!");
})();

```
