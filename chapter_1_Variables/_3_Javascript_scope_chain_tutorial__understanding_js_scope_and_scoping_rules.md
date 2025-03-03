--> Overriding :- This happens when a function scoped var overrides a global scoped var

<script>
var global = "global";

function a(){
    global = "overriding global";
    console.log("from function a() "+ global); //showing : from function a() overriding global
}
a();
</script>

--> Now if try to call 'var global' outside the function scope then also the returned value would be overridded value over the global scoped 'var global'. such as:

<script>
var global = "global";

function a(){
    global = "overriding global";

}
a();
   console.log("after execution of function a() "+ global); //showing : after execution of function a() overriding global
</script>

--> Variable Shadowing: this occurs when a variable decleared within a certain scope { in this case it's the local scope of a() } has a same name as the variable decleared in the outer scope { in this case it's the global scope }

<script>
var global = "global";

function a(){
    var global = "redefining global"; //re-declearing global
    console.log("from function a() "+ global); //showing : from function a() redefining global
}
a();
</script>

--> Now if try to call 'var global' outside the function scope then  the returned value would be same value decleared on the global scoped 'var global'. such as:

<script>
var global = "global";

function a(){
    var global = "redefining global"; //re-declearing global

}
a();
    console.log("from function a() "+ global); //showing : from function a()  global
</script>