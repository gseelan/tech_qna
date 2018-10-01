# tech_qna
Some small code work

Q1: For the given number, find the max zero occurence in its binary number. 32 = 10000, No closure of zeros hence no max zero.

function solution(N) {
    var num = [];
    while(N!==0 && N!==1){
        num.unshift(N%2);
        N = Math.floor(N/2);
    }
    num.unshift(N);
    var max=0;
    var temp = 0;
    for(i=0;i<num.length;i++){
        if(num[i]===1){
            if(temp>max){
                max = temp;
            }
            temp = 0;
        }else{
            temp++;
        }
    }
    return max;
}

Q2: Odd occurences of a number in an Array of length N.

function solution(A) {
    var ta= {};
    var len = A.length;
    for(var i=0;i<len;i++){
        ta[A[i]]? delete ta[A[i]] : ta[A[i]] = 1;
    }
    return parseInt(Object.keys(ta)[0]);
}

Q3: Fib with memo

//Outer function
function fib(num){
  let res = {}; //To cache
  let count = 0;

  function f(n){
    
    //checking if it is in the cache
    if(res[n]){
      return res[n]
    }
    
    count++; //just to count the calls
    //regular fib. But adding the value to the cache
    if(n===0||n===1){
      res[n] = n;
      return n;
    }
    //again regular and adding the cache
    res[n] = f(n-1)+f(n-2);
    return res[n];
  }
  console.log(f(num),count);
  return res;
}

console.log(fib(30))
