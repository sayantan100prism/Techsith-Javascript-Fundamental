--> Array.from(): is a constructor method so it does not work on array like this below:
-> 
<script>
[1,2,3].splice(); //Array.from(): is a constructor method so it does not work on array like this

Array.from()
</script> 

-->
exmple
<script>
let str = "techsith";
console.log([...str]);  //(8) ['t', 'e', 'c', 'h', 's', 'i', 't', 'h']
const fromString = Array.from(str);
console.log(fromString);  //(8) ['t', 'e', 'c', 'h', 's', 'i', 't', 'h']
</script>

--> Creation of arrays from fly
<script>
const fromScratch = Array.rom({length:5}, (v,i)=>) // first argument={length:5} and second argument =callback function consisting value and index wheer value is undefined and index is 0,1,2,3,4.
console.log(fromScratch)//[undefined,undefined,undefined,undefined,undefined]
</script>

--->
<script>
const fromScratch = Array.rom({length:5}, (v,i)=>'') // first argument={length:5} and second argument =callback function consisting value and index wheer value is undefined and index is 0,1,2,3,4.
console.log(fromScratch)//output: [ '', '', '', '', '' ]
</script>

-->
<script>
const fromScratch = Array.rom({length:5}, (v,i)=>'') // first argument={length:5} and second argument =callback function consisting value and index wheer value is undefined and index is 0,1,2,3,4.
console.log(fromScratch)//output: [ 0, 1, 2, 3, 4 ]
</script>
 -->
<script>
const fromScratch = Array.rom({length:5}, (v,i)=>'') // first argument={length:5} and second argument =callback function consisting value and index wheer value is undefined and index is 0,1,2,3,4.
console.log(fromScratch)//output: [ 0, 1, 4, 9, 16 ]
</script>


--> Doing in older way first declearing a array, then filling it with 0 then filling it with value i want

<script>
const fromScratch = (new Array(5)).fill(0).map((,i)=> i) // first argument={length:5} and second argument =callback function consisting value and index wheer value is undefined and index is 0,1,2,3,4.
console.log(fromScratch)//output: [ 0, 1, 2, 3, 4 ]
</script>

--> inorder to get all unique values and remove any duplicates
<script>
const ary = [1, 1, 2];
const unique =  Array.from(new Set(ary)); // Set() holds the unique values and Array.from() convert it into array
console.log(unique);  // [1, 2]
const unique = [...new Set(ary)]; // [1, 2] //doing the same thing but not storing in array
</script>



-->
<script>
const func= function(){
    console.log(arguments); // Arguments(8) ['t', 'e', 'c', 'h', 's', 'i', 't', 'h', callee: ƒ, Symbol(Symbol.iterator): ƒ]
}
func('t', 'e', 'c', 'h', 's', 'i', 't', 'h')
</script>

--> Now if I want to join it
<script>
const func =function(){
    console.log(Array.from(arguments).join('')); // techsith
}
func('t', 'e', 'c', 'h', 's', 'i', 't', 'h')
</script>