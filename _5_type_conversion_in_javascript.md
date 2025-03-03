--> What would happen when you try to add  a number and string in js?
<script>
let x = 2 + '2';
console.log(x); // 22
</script>
-> this is because js will try to take the simpler path while trying to convert add a number and string, first it will convert a number into a string then would concat them together to form an output.


--> 
<script>
let x = 2 + 2+ '2';
console.log(x); // 22
</script>
->the answer is 42, as it will read from left to right so when it will se 2 + 2, it will add them then when it will encounter '2', it will convert 4 into a string and concat them to '42'.

--> 
<script>
let x = 2 + true;
console.log(x); // 3
</script>
-> converting a boolian into number is easy so js will convert boolean 'true' into number 1 and will add them into 3.

--> 
<script>
let x = 2 + true + '2';
console.log(x); // 32
</script>
-> converting a boolian into number is easy so js will convert boolean 'true' into number 1 and will add them into 3. and then convert 3 into a string and concat them into 32

-->
<script>
let x =  true + '2';
console.log(x); // true2
</script>
-> Converting bolian into a string is earier so it will convert bool into a string and concat them 'true2'

-->
<script>
let x = Number(2);
console.log(x); // 2 in number
</script>

--> 
<script>
let x = Number(Hello);
console.log(x); // NaN i,e not in number
console.log(typeof(x)); //But if i try to find the type of x then it would be a number
</script>

--> 
<script>
let x = Boolean(1);
console.log(x); // true
</script>

--> 
<script>
let x = Boolean(5);
console.log(x); // true , only value that will give false is 0
</script>

-->
<script>
let x = Boolean('hello');
console.log(x); // true , only for empty string, undefined and null  it will give false
</script>

--> R