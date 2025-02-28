-> Javascript follow Lexical scoping i.e globally declared variable is available inside function too 

-> Difference between Var and Let ?
<script>
function checkVar() {
    // var is function scoped and not block scoped so it is accessible outside the block i.e for loop
    for (var i = 0; i < 5; i++) {
        console.log(i);
    }
    console.log('Finally: ' + i);
}
checkVar();
</script>

<script>
function checkLet() {
    // let is block scoped so it is not accessible outside the block i.e for loop
    for (let i = 0; i < 5; i++) {
        console.log(i);
    }
    console.log('Finally: ' + i); // This will throw error
}
checkLet();
</script>
//Thus we can identyfy errors easily in compile time itself in Typescript
//  but this error is not identified in Javascript as it is not a strongly typed language 
// and it is not compiled and it is interpreted at runtime thus no errors are thrown at compile time




-> Give an example about how const throws an error when we try to change its value.

<script>
    const i = 2;

    i = 9;

    console.log(i) // This will throw an error as the value of i can not be reassigned
</script> 