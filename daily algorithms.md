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

[16 split  camel case](https://www.codewars.com/kata/5208f99aee097e6552000148/train/javascript)

```js

function solution(string) {
   
   const camelCase = [...string].filter(item => {
                                                    return item != item.toLocaleLowerCase()
                                                })
    let strr = ''
    camelCase.map(item => {
        strr.search(item) === -1 ? strr += item : strr
    })

    const camelCase2 = [...strr]

   let str = string
   camelCase2.forEach(item => str = str.split(item).join(` ${item}`))

   return str
    
}

```
---


[17 find norepeating letter](https://www.codewars.com/kata/52bc74d4ac05d0945d00054e/train/javascript)

```js
function firstNonRepeatingLetter(s) {
    // Add your code here
    const arr = [...s]

    const arr2 = arr.filter(item => {
               
               return arr.filter( thing => { return item.toLowerCase() === thing.toLowerCase() }  ).length === 1 

             
            })[0] 
            
    return arr2 === undefined ? '' : arr2
}
```
---


[18 sameStructureAs](https://www.codewars.com/kata/520446778469526ec0000001/train/javascript)

```js
Array.prototype.sameStructureAs = function (other) {
    
    const arr1Str = JSON.stringify(this)
    const arr2Str = JSON.stringify(other)
    
    let i = 0
    let check = 0
    
        for(let key of arr1Str){
    
    
            if(isNaN((+key + 0)) && key === arr2Str[i]){
                check++
                if(key === "\"" ){
                    return true
                }
            }
    
            if(!isNaN((+key + 0))){
                check++
            }
    
            i++
        
        }
    
    
        if(check === arr1Str.length){
            return true
        }
        else{
            return false
        }
    }


```
---




[19 decode Morse ](https://www.codewars.com/kata/54b724efac3d5402db00065e/train/javascript)

```js    
function cuttingSpace(string){

    let assingingString = string 
  
    for(let i = 0; i < 2; i++){
  
      for(let j = 0; j < assingingString.length; j++){
        if(assingingString[j] !== ' '){
          assingingString = assingingString.slice(j)
          break;
        }
      }
  
      if(i === 1){
        return [...assingingString].reverse().join('')
      }
  
      assingingString = [...assingingString].reverse().join('')
  
    }
  }
  

  
  
  function decodeMorse(string){
  
  const compressString = cuttingSpace(string)
    
  const arr = compressString.split(' ')
  
  
  let word = ''
  
  for(let key of arr){
    switch(key){
      case '.-': word += 'A'; break;
      case '-...': word += 'B'; break;
      case '-.-.': word += 'C'; break;
      case '-..': word += 'D'; break;
      case '.': word += 'E'; break;
      case '..-.': word += 'F'; break;
      case '--.': word += 'G'; break;
      case '....': word += 'H'; break;
      case '..': word += 'I'; break;
      case '.---': word += 'J'; break;
      case '-.-': word += 'K'; break;
      case '.-..': word += 'L'; break;
      case '--': word += 'M'; break;
      case '-.': word += 'N'; break;
      case '---': word += 'O'; break;
      case '.--.': word += 'P'; break;
      case '--.-': word += 'Q'; break;
      case '.-.': word += 'R'; break;
      case '...': word += 'S'; break;
      case '-': word += 'T'; break;
      case '..-': word += 'U'; break;
      case '...-': word += 'V'; break;
      case '.--': word += 'W'; break;
      case '-..-': word += 'X'; break;
      case '-.--': word += 'Y'; break;
      case '--..': word += 'Z'; break;
  
      case '.----': word += '1'; break;
      case '..---': word += '2'; break;
      case '...--': word += '3'; break;
      case '....-': word += '4'; break;
      case '.....': word += '5'; break;
      case '-....': word += '6'; break;
      case '--...': word += '7'; break;
      case '---..': word += '8'; break;
      case '----.': word += '9'; break;
      case '-----': word += '0'; break;
      case '...---...': word += 'SOS'; break;
      case '-.-.--': word += '!'; break;
      case '.-.-.-': word += '.'; break;

  
      case '': word += ' '; break;
    }
  }
  
   const readyWord = word.split('  ').join(' ')
   return readyWord
  
  }

  
```
---



[20 Snail Sort ](https://www.codewars.com/kata/521c2db8ddc89b9b7a0000c1/train/javascript)

```js
snail = function(array) {

if(array.length === 1){
  return array[0]
}

//  taking firth row and cleaning this row
    let returningArr = array[0]
    array[0] = 0
    let newArr = array.filter(item => item !== 0)

// taking last item each array and clearing them
    for(let i = 0; i < newArr.length; i++){
      returningArr[returningArr.length] = newArr[i][newArr[i].length - 1]
      newArr[i] = newArr[i].splice(0, newArr[i].length - 1)
    }

// taking last array by reverse and clearing it
  if(newArr.length === 1){
    returningArr = [...returningArr, ...newArr[0]]
    return returningArr
  }
  else{
    returningArr = [...returningArr, ...newArr[newArr.length - 1].reverse()] 
    newArr = newArr.filter((item, ind) => ind !== newArr.length - 1)
  }




// taking firth item each array 
  for(let i = 0; i < newArr.length; i++){
    returningArr[returningArr.length] = newArr[newArr.length - (i + 1)][0]
    newArr[newArr.length - (i + 1)] = newArr[newArr.length - (i + 1)].splice(1, newArr[i].length)
  }



  if(newArr.length === 1){
    returningArr = [...returningArr, ...newArr[0]]
    return returningArr
  }
  else{
    return [...returningArr,...snail(newArr)]
  }
}


```
---



[21 Making number from words ](https://www.codewars.com/kata/525c7c5ab6aecef16e0001a5/train/javascript)

```js



function numberMaker(string) {     
    
    const arr = ['zero','one', 'tw', 'th', 'four', 'five', 'six', 'seven', 'eight', 'nine', 'ten',  'eleven','twelve', 'for', 'fif', 'hundred', 'thousand','million']

    const integerObj = {'zero': 0, 'one': 1, 'tw': 2, 'th': 3, 'four': 4, 'five': 5, 'six': 6, 'seven': 7, 'eight': 8, 'nine': 9, 'ten': 10, 'eleven': 11,'twelve': 12,'for': 4, 'fif': 5, 'hundred': 100, 'million': 1000000, 'thousand': 1000}


    // separating to items
    

    const separatingArray = string.split(' ')

    const preparingList = []


     // converting to numbers
    for(let i = 0; i < separatingArray.length; i++){

        const item = separatingArray[i] 

        if(!item.includes('-') && (item.slice(-2) === 'ty') && !(item.slice(-4) === 'teen')){

            for(let key of arr){
                 if(item.includes(key)){
                     preparingList[i] = integerObj[key] * 10
                 }
             }
         }
         else if(!item.includes('-') && !(item.slice(-2) === 'ty') && (item.slice(-4) === 'teen')){
            for(let key of arr){
                 if(item.includes(key)){
                     preparingList[i] = integerObj[key] + 10
                 }
             }
         }

        else if(item.includes('-') && !(item.slice(-2) === 'ty') && !(item.slice(-4) === 'teen')){

            let assignTens = 0
            item.split('-').map(itemMap => {
                for(let key of arr){

                    if(itemMap.includes(key)){
                        if(assignTens !== 0){
                            assignTens = assignTens * 10 + integerObj[key]
                        }
                        else{
                            assignTens = integerObj[key]
                        }
                    }
                }
            })
            preparingList[i] = assignTens
         }



         else if(!item.includes('-') && !(item.slice(-2) === 'ty') && !(item.slice(-4) === 'teen')){
            for(let key of arr){
                 if(item.includes(key)){
                     preparingList[i] = integerObj[key]

                 }
             }
         }           
    }

    //calculating number
    let preparingNumber = 0   

        if(preparingList.length === 3){
            preparingNumber = (preparingList[0] * 100) + preparingList[2]
        }
        else if(preparingList.length === 2){
            preparingNumber = (preparingList[0] * 100) 
        }
        else{
            preparingNumber = preparingList[0]
        }


return preparingNumber
}


function parseInt(string) {

    let millionArr = []
    let thousandArr = []


    if(string.includes('million')){
        let num = 0
        if(string.slice(-7) === 'million'){
           millionArr = string.split(' ').filter(item => item !== 'and').join(' ').split(' million')
           return numberMaker(millionArr[0]) * 1000000
        }

        millionArr = string.split(' ').filter(item => item !== 'and').join(' ').split(' million ')
        num = numberMaker(millionArr[0]) * 1000000
        
        if(millionArr[1].includes('thousand')){
            if(millionArr[1].slice(-8) === 'thousand'){
                thousandArr = millionArr[1].split(' thousand')
                return num += numberMaker(thousandArr[0]) * 1000
             }

            thousandArr = millionArr[1].split(' thousand ')
            console.log(thousandArr[0]);
            num += numberMaker(thousandArr[0]) * 1000
            if (thousandArr[1] !== '') {
                num += numberMaker(thousandArr[1])
            }

        }
        else if (millionArr[1] !== '') {
            num += numberMaker(millionArr[1])
        }

        return num      
    }

    else if(string.includes('thousand')){
        let num = 0
        if(string.slice(-8) === 'thousand'){
           thousandArr = string.split(' ').filter(item => item !== 'and').join(' ').split(' thousand')
           return numberMaker(thousandArr[0]) * 1000
        }

        thousandArr = string.split(' ').filter(item => item !== 'and').join(' ').split(' thousand ')
        num = numberMaker(thousandArr[0]) * 1000
        
        
        if (thousandArr[1] !== '') {
            num += numberMaker(thousandArr[1])
        }

        return num      
    }
    else{
        const string1 = string.split(' ').filter(item => item !== 'and').join(' ')
        return numberMaker(string1)
    }
}



```
---




[22 Roman number to simple number and reverse ](https://www.codewars.com/kata/51b66044bce5799a7f000003/train/javascript)

```js

const listOfNumbers = {
    "0": '',
    "00": '',
    "000": '',
    "1": 'I',
    "2": 'II',
    "3": 'III',
    "4": 'IV',
    "5": 'V',
    "6": 'VI',
    "7": 'VII',
    "8": 'VIII',
    "9": 'IX',
    "10": 'X',
    "20": 'XX',
    "30": 'XXX',
    "40": 'XL',
    "50": 'L',
    "60": 'LX',
    "70": 'LXX',
    "80": 'LXXX',
    "90": 'XC',
    "100": 'C',
    "200": 'CC',
    "300": 'CCC',
    "400": 'CD',
    "500": 'D',
    "600": 'DC',
    "700": 'DCC',
    "800": 'DCCC',
    "900": 'CM',
    "1000": 'M',
    "2000": 'MM',
    "3000": 'MMM',
    "4000": 'MMMM',
}

const listOfRomanNumbers = {
    "I": '1',
    "V": '5',
    "X": '10',
    "L": '50',
    "C": '100',
    "D": '500',
    "M": '1000',
}



class RomanNumerals {
    static toRoman(num) {
        const stringNum = `${num}`.split('')

        let result = ''
        
        stringNum.forEach((item, idx, arr) => {
     
        const numWidthZero = item.padEnd((arr.length - idx), '0')

        result += listOfNumbers[numWidthZero]
       })
       return result
    }

  
    static fromRoman(str) {
    
        const romanNumbersArr = str.split('')

        const changedRomeNumbers = romanNumbersArr.map(item => {
            return +listOfRomanNumbers[item]
        })

        for (let i = 0; i < changedRomeNumbers.length; i++) {
            if(changedRomeNumbers[i] < changedRomeNumbers[i + 1]){
                changedRomeNumbers[i] = +`-${changedRomeNumbers[i]}`
            }
        }

        let result = 0

        changedRomeNumbers.forEach(item => result += item)
        return result
    }
  }





```
---


 


 








