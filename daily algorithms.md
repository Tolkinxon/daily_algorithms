[1. Against order?](https://www.codewars.com/kata/5467e4d82edf8bbf40000155/train/javascript)

Solution
```js

# React_JSX
learn JSX practice first practica
function descendingOrder(n){
    let a = String(n)
    a = a.split('')

    for(key of a){
        for(let i = 0; i < a.length; i++){
            if(a[i] < a[i + 1]){
                let b = a[i + 1]
                a[i + 1] = a[i]
                a[i] = b
            }
        }
    }
    const v = a.join('')
    return +v

  }

  console.log(descendingOrder(79248088));
  ```
---

[2. Removing same item?](https://www.codewars.com/kata/5467e4d82edf8bbf40000155/train/javascript)

Solution
```js

function arrayDiff(a, b) {
    const newArr = []
    let bool = false
    for(keyA of a){
       for(keyB of b){
        if(keyA === keyB){
            bool = true
            break; 
        }
       }
       if(!bool){
        newArr.push(keyA)
       } 
       bool = false;
    }
    return newArr
  }

 console.log( arrayDiff([1,2, 5, 7, 0,3,2], [7])); 
 
   ```
---
