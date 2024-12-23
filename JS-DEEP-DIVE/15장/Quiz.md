### **Quiz🙋🏻‍♀️** 

<br>

1. **let과 var 차이**
   ```javascript
   console.log(x); // undefined (var)
   console.log(y); // ReferenceError (let)
   ```

2. **블록 레벨 스코프**
   ```javascript
   console.log(typeof a); // "undefined" (블록 밖 접근 불가)
   console.log(typeof b); // "undefined"
   ```

3. **TDZ**
   - `let`, `const`는 선언 전에 접근 시 `ReferenceError` 발생.

4. **const의 불변성**
   ```javascript
   const obj = { name: "JavaScript" };
   obj.name = "Deep Dive";
   console.log(obj.name); // "Deep Dive"
   ```

5. **변수 호이스팅**
   ```javascript
   console.log(a); // ReferenceError (let)
   ```

6. **const 키워드**
   - 선언 시 반드시 초기화 필요, 재할당 불가.

7. **반복문과 let**
   ```javascript
   for (let i = 0; i < 3; i++) {
     setTimeout(() => console.log(i), 100);
   }
   // 출력: 0, 1, 2
   ```

8. **블록 레벨 스코프와 클로저**
   ```javascript
   let a = 5;
   const b = () => a + 10;
   console.log(b()); // 15
   ```

9. **var와 let의 스코프 차이**
   ```javascript
   console.log(x); // 10 (var)
   console.log(y); // ReferenceError (let)
   ```

10. **키워드 선택**
   - 상수 → `const`  
   - 변경 가능 → `let`  
   - 전역 변수 (비권장) → `var`


<br>
