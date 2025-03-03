-->in Javascript negative index doesnot happen what happens is key: value pair
<script>
const ary = [1,2,3];
ary[-1] =0;
console.log(ary)  // [1,2,3,-1:0] // where -1:0 is akey value pair
console.log(ary.length) //3
console.log(ary[-1]); //0
</script>

-->Javascript arrays behaving like javascript objects

--> length is 0 as i do not have any regular array stuff, all i have is key value pair
<script>
const ary = [];
aray['a'] = 'aval';
aray['b'] = 'bval';
console.log(ary)  /*(0) [a: 'aval', b: 'bval']
snippt_test.html:11
a ='aval'
b ='bval'
length =0
*/

</script>

--> So in order to iterate through the objects we will use

<script>
const ary = [];
ary['a'] = 'aval';
ary['b'] = 'bval';
for(let key in ary){
    console.log(`${key} : ${ary[key]}`);
    /*a : aval
      b : bval*/
}
</script>

--> Note : There is not much difference between js object and arrays

<script>
const ary = [1, 2, 3];
const obj = {};
obj[0] = 1;
obj[1] = 2;
obj[2] = 3;
console.log(ary); // length is shown as it is array
/*
(3) [1, 2, 3]
snippt_test.html:13
0 =1
1 =2
2 =3
length =3
*/
console.log(obj);// length is not shown as it is object
/*
{0: 1, 1: 2, 2: 3}
snippt_test.html:13
0 =1
1 =2
2 =3
*/
</script>

?????????????????????????????????????????????????????????

--> Why array is expensive if we want to add a value in the middle of that array than doing the same operation on an object?

???????????????????????????????????????????????????????????????

--> since in a large array if we want to add any value in the middle of it we have to shift all indexes over, thus operation on array is expensive.
  But while performing same operation on objects we do not need to shif entire indexes, as they are like maps.

--> For array
<script>
console.time('a');
const a = [];
for(let i=0; i< 100000000; i++){
    a[i]= i;
}
console.timeEnd('a');  //a: 361.735107421875 ms
</script> 

--> For object
<script>
console.time('o');
const a = {};
for(let i=0; i< 100000000; i++){
    a[i]= i;
}
console.timeEnd('o');  //o: 616.693115234375 ms //very little but lesser than array ???????????
</script> 

--> Let's try to insert a value in array
<script>
const a = [];

for(let i=0; i< 100000000; i++){
    a[i]= i;
}
console.time('ain');
 a[5000000] = 5000000;
console.timeEnd('ain');  //ain: 0.011962890625 ms
</script> 

--> Let's try to insert a value in object
<script>
const o = {};

for(let i=0; i< 100000000; i++){
    o[i]= i;
}
console.time('oin');
 o[5000000] = 5000000;
console.timeEnd('oin');  //oin: 0.013916015625 ms   //very little but lesser than array??????????
</script> 
</script>