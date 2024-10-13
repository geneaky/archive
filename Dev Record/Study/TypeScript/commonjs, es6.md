두 방식에 내보내기, 불러오기 차이가 있다

##### CommonJS

module이라는 객체 내 exports라는 키를 가진 프로퍼티를 사용해 객체를 내보낼 수 있음
단일 객체의 경우 module.exports로 내보낼 수 있고, 여러객체를 내보내야하는 경우 exports 객체에 각 객체 프로퍼티를 지정,할당하여 내보낼 수 있음.
```js
//export
const a = 3;
const b = () => console.log("b")

class C {
    constructor(name) {
        this.name = name
    }
}
const c = new C("c")

// module.exports = { a, b, c }
exports.a = a
exports.b = b
exports.c = c

//required
// const {a, b, c} = require("./commonjs-export.cjs")
const {a} = require("./commonjs-export.cjs")
const {b} = require("./commonjs-export.cjs")
const {c} = require("./commonjs-export.cjs")

console.log(a, b, c)
```


##### ES6
