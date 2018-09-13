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
