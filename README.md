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
