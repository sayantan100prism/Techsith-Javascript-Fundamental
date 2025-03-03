--> What is function scoping in var?
--><script>
    var x = function(){
        var y =1;
        console.log(y); //shows answer 1 //this is function scoped call 
    }
    console.log(y); //shows error //outside of function scope
    x()
</script>

--> <script>
    var x = function(){
        if(true){
            var y =1;
            console.log(y); //shows answer 1 //this is block scoped call

        }

        console.log(y); //shows answer 1 //this is function scoped call
    }
    console.log(y) //shows error //outside of function scope
    x()    
</script>

--> What does Hoisting in Javascript means?

--><script>
    var x=function(){

        console.log(y); //shows undefined which means it can find y inside the function() but to console.log(y), still no value is assigned

        console.log(z); // shows error, as "z" is not present anywhere in the function scope

        var y = 1;
    }
    x();
</script>

-> thus the term hoisting does is decleares the variable y, whenever it is called inside the function and wait for us to assign it a value.just like this:

--><script>
    var x=function(){
        var y;
        console.log(y); 
        var y = 1;
    }
    x();
</script>

--> global var or function scoped var which one is more prioritized, if the name is same and it is called inside function?

--> function scoped var will be prioritized, however if the function scoped var is called before it is decleared then the output will be "undefined"
<script>
    var y=2;
    var x=function(){
        
        console.log(y); // output = undefined
        var y = 1;
    }
    x();
</script> 
but if the function scoped var is removed then the output will be global scoped var's value
<script>
<script>
    var y=2;
    var x=function(){
        
        console.log(y); // output = 2
        
    }
    x();
</script> 
</script>