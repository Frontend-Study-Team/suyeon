### 1. **원시값 비교**

<br>

```jsx
let a = 10;
let b = 10;

console.log(a === b);

```

<br>

```jsx
let str1 = "hello";
let str2 = "hello";

console.log(str1 === str2);

```

<br>
<br>

### 2. **객체 비교**

<br>

```jsx
let obj1 = { name: "Alice" };
let obj2 = { name: "Alice" };

console.log(obj1 === obj2);

```

<br>
<br>

### 3. **객체의 참조 비교**

<br>

```jsx
let obj3 = { name: "Alice" };
let obj4 = obj3;

console.log(obj3 === obj4);

```

<br>
<br>

### 4. **원시값을 객체처럼 다루기 (박싱)**

<br>

```jsx
let str = "hello";
console.log(str.toUpperCase());

```

<br>
<br>

### 5. **`null`과 `undefined` 비교**

```jsx
let a = null;
let b = undefined;

console.log(a === b); 
console.log(typeof a);  
console.log(typeof b);  

```
<br>
<br>
