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

[4. Finding sum of choosing row pyramid of odd numbers?](https://www.codewars.com/kata/55fd2d567d94ac3bc9000064/train/javascript)


Solution
```js
function rowSumOddNumbers(n) {

    let sum = 1
    let Sum = 0
	for(let i = 1; i <= n; i++){
        for(let j = 1; j <= i; j++){
            if(i === n){
                Sum += sum
            }
            sum += 2
        }
    }

    return Sum
}

```
---

[5. Build cone with stars?](https://www.codewars.com/kata/576757b1df89ecf5bd00073b/train/javascript).



Solution
```js 
function towerBuilder(n){
    const arr = []
    let odd = 1
    let value = '*'
    let valeSpace = ' '

    for(let i = 1; i <= n; i++){

        const a = ((n * 2 - 1 ) - odd) / 2

        const valSpace = valeSpace.repeat(a) 
        const valStar = value.repeat(odd)
        let val = valSpace + valStar + valSpace

        odd += 2

        arr[i - 1] = val
    }

    return arr
}



```
---

[5. Find this is a triangle or no?](https://www.codewars.com/kata/56606694ec01347ce800001b/train/javascript)

Solution

```js 
const isTriangle = (a,b,c) =>  a + b > c && a + c > b && b + c > a ? true : false

```
---


[6. Changing string letters](https://www.codewars.com/kata/520b9d2ad5c005041100000f/train/javascript)
```js 
function pigIt(str){
    const arr = str.split(' ')
    const arrChanged = arr.map(item => {
        if(item === '!' || item === '?' ){
            return item
        }
        else{
      return item.slice(1) + item[0] + 'ay'

        }
    })
    return arrChanged.join(' ')
}

console.log(pigIt('Pig latin is cool !'));


```
---


[7. isPanga checking function](https://www.codewars.com/kata/545cedaa9943f7fe7b000048/train/javascript)
```js
function isPangram(string){
    const base = 'abcdefghijklmnopqrstuvwxyz'
  
    let stringLower = string.toLowerCase()
    
    for(let key of base){
      if(!stringLower.includes(key)){
        return false
      }
    }
    return true
  }
```
---


[8. Finding odd times repeating number](https://www.codewars.com/kata/54da5a58ea159efa38000836/train/javascript)
```js
  function findOdd(Arr) {

    const oddTime = {}

    let differentNumber = ''
    const differentNumberArr = []

    Arr.sort((a, b) => a - b).map(item => {
        if(item !== differentNumber){
            differentNumber = item
            differentNumberArr.push(differentNumber)
        }
    })





    let repeating = 0
    for(let i = 0; i < differentNumberArr.length; i++){
        Arr.map(item => {
            if(item === differentNumberArr[i]){
                repeating++
            }
        })

        oddTime[`${differentNumberArr[i]}`] = repeating
        repeating = 0

    }

    for(let key in oddTime){
       if(oddTime[key] === 1 || oddTime[key] % 2 == 1){
        return +key
       }
    }

  }


```
---



[9. Multiply roommate numbers.](https://www.codewars.com/kata/55bf01e5a717a0d57e0000ec/train/javascript)
```js
function persistence(num) {
    let sumRepeating  = 0
    let num2 = num + ''
    let multiply = 1



        if(num2.length === 1){
            return sumRepeating
        }
        else{
            while(num2.length > 1){
                const arr = num2.split('')
                arr.map(item => multiply *= +item)
                num2 = multiply + ''
                multiply = 1
                sumRepeating++
            }
        }
          return sumRepeating

 }


```
---



[10. Plays banjo.](https://www.codewars.com/kata/53af2b8861023f1d88000832/train/javascript)
```js
function areYouPlayingBanjo(name) {
    let firthLetter = name[0]

    if(firthLetter.toLowerCase() === 'r'){
        return `${name} ${'plays banjo'}`;
    }else{
        return `${name} ${'does not play banjo'}`;
    }    
}

areYouPlayingBanjo('rohan')

```
---



[11. Make negative](https://www.codewars.com/kata/55685cd7ad70877c23000102/train/javascript)

```js
function makeNegative(num) {
   
    if(0 < num){
        return -1 * num
    }
    if(0 >= num){
        return num
    }
  }

```
---



[12. Make DNA to RNA](https://www.codewars.com/kata/5556282156230d0e5e000089/train/javascript)

```js
const DNAtoRNA = dna =>  {

    let rna = ''

    for(let i = 0; i < dna.length; i++){
        dna[i] === 'T' ? rna += 'U' : rna += dna[i]
    }

    return rna;
}

```
---





[13. Find everage](https://www.codewars.com/kata/55cbd4ba903825f7970000f5/train/javascript)

```js
const  getGrade = (s1, s2, s3) => { 
    const sum = (s1 + s2 + s3) / 3; 
   return sum >=90 ? 'A' : 
          sum < 90 && sum >= 80 ? 'B' :
          sum < 80 && sum >=70 ? 'C' :
          sum < 70 && sum >= 60 ? 'D':
          sum < 60 && sum >= 50 ? 'F' : 'F'
}

```
---


[14 "scissors, paper, rock"](https://www.codewars.com/kata/5672a98bdbdd995fad00000f/train/javascript)

```js


const rps = (p1, p2) => {
    const w = p1 + p2

    if(
        w[0] === 's' && w[w.length - 1 ] === 'r' ||
        w[0] === 'p' && w[w.length - 1] === 'k' || 
        w[0] === 'r' && w[w.length - 1] === 's'
       ){
        return 'Player 1 won!'
    }
    else if(
        w[0] === 's' && w[w.length - 1 ] === 's' ||
        w[0] === 'p' && w[w.length - 1] === 'r' || 
        w[0] === 'r' && w[w.length - 1] === 'k'
    ){
        return 'Draw!'
    }
    else{
        return 'Player 2 won!'
    }

};
```
---


[15 split  strings](https://www.codewars.com/kata/515de9ae9dcfc28eb6000001/train/javascript)

```js
function solution(str){
    const arr = []
    for(i = 0; i < str.length; i += 2){

        arr[i / 2] = i === str.length - 1  ? str[i] + '_' :  str[i] + str[i + 1] 
    }

    console.log(arr);
}

solution('')




```
---





