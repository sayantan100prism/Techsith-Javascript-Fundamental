--> How to create objects in Javascript? and what are Non function objects and Function Objects?
   -> How to create empty object?
   <script>
    var x = new Object();
    console.log(x);
    var y = {};
    console.log(y);

    //also console.dir() gives same output but with more detail
    console.dir(x);
    console.dir(y);
   </script>

   --> "this.(public properties)" : helps to fetch any publiciy available properties into a METHOD


   <script>
    var pizza = {
        crust : 'thin',
        toppings : 3,
        hasBacon : true,
        howManyToppings : function(){  // NOTE : 'howManyToppings' is called METHOD
            return this.toppings;
        }
    };
    pizza.price = '12$'; //// in js we can access the feature of adding another property after creating object
    
    console.log(pizza.howManyToppings()); // 3

    console.log(pizza); // {crust: 'thin', toppings: 3, hasBacon: true, howManyToppings: ƒ, price: '12$'}

   </script>

--> Inorder to remove a Property use delete()

   <script>
        var pizza = {
        crust : 'thin',
        toppings : 3,
        hasBacon : true,
        howManyToppings : function(){  // NOTE : 'howManyToppings' is called METHOD
            return this.toppings;
        }
    };
    pizza.price = '12$'; //// in js we can access the feature of adding another property after creating object
    
    console.log(pizza.howManyToppings()); // 3


    delete(pizza.crust);

    console.log(pizza); // {toppings: 3, hasBacon: true, howManyToppings: ƒ, price: '12$'}

   </script>



   -->NOTE: JAVASCRIPT DOES NOT HAVE FORMAL SUPPORT FOR CLASSES WHICH MEANS, INSTEAD OF CREATING CLASS AND CREATING OBJECT FROM IT, 
                 IN JS WE CREATING FUNCTION OBJECT.

<script>
    var Pizza = function(){    // function object

    };
    console.log(Pizza);  
    /*
    ƒ (){

    }
    */
       
</script>

<script>
    var Pizza = function(){    // function object
        this.crust = 'thin';         //adding public properties using this.
        this.toppings = 3;
        this.hasBacon = true;
    };
    console.log(Pizza); 
    /* output
    ƒ (){    // function object
        this.crust = 'thin';         //adding public properties using this.
        this.toppings = 3;
        this.hasBacon = true;
    }
    */

   console.log(Pizza.crust);   //undefined /// here we cannot access object like this so:

   //WE WILL BW CREATING OBJECT FROM OBJECT
   var pizzaA = new Pizza();
   var pizzaB = new Pizza();
   console.log(pizzaA.crust); //thin
   console.log(pizzaB.crust);  // thin

   pizzaA.crust = 'pan'; //pizzaA.crust changed from 'thin' to 'pan'
   console.log(pizzaA.crust);// pan
   console.log(pizzaB.crust); // thin

   console.log(pizzaB  instanceof  Pizza);  // true
      console.log(pizzaB.constructor); 
   /*output
   ƒ (){    // function object
        this.crust = 'thin';         //adding public properties using this.
        this.toppings = 3;
        this.hasBacon = true;
    }*/
</script>



--> Private Variables