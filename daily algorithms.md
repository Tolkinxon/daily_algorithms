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

[2. Removing same item?](https://www.codewars.com/kata/523f5d21c841566fde000009/train/javascript)

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

[3. Reordering letters?](https://www.codewars.com/kata/5656b6906de340bd1b0000ac/train/javascript)

Solution
```js

function longest(s1, s2) {

  const sum = s1 + s2

  const validating = 'abcdefghijklmnopqrstuvwxyz'

  separatingLetter = ''

  for(key of validating){
    if(sum.includes(`${key}`))
        separatingLetter += key
  }

  return separatingLetter

}
```

---
