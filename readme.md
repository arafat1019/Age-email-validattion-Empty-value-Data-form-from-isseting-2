 #### Data form 
 
 
<?php

 /* echo"<pre>";
  print_r($_POST['name']);
  echo"</pre>";
  


 ?>
    



    <div class="user-form">
        <h2>ADD YOUR INFO</h2>
        <form action="" method="POST" >
            <input name="name"   type="text" placeholder="Name">
            <input name="email"  type="text" placeholder="Email">
            <input name="number" type="text" placeholder="Number">
            <input name="age"    type="text" placeholder="Age">
            <input name="submit" type="submit" value="Send">
        </form>
    </div> 

    
    
    
    
#### form isseting
By using isset function we can solve error  notice
    
    /**
     * form isseting
     */
    if ( isset( $_POST['submit'] ) ) {
       
        $name = $_POST['name'];
        $email = $_POST['email'];
        $number = $_POST['number'];
        $age = $_POST['age'];

    }

#### Empty value check
we can check Empty value by Empty function


***php

//Empty value check

    if ( empty($name) || empty($email) || empty($number) || empty($age)  ) {
        $bat =  "<p style=\" color: red; \">All fields are required</p>";
    }else {
        $bat =  "<p style=\" color: green; \">Data stable</p>";
    }
 
 ***php

 <?php
        // show validation message
        if ( isset($bat) ) {
            echo $bat;
        }  
 ?>

#### Email validattion check


if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
    echo "Email";
}else { 
    echo "Not Email";
}


//Empty value check

    if ( empty($name) || empty($email) || empty($number) || empty($age)  ) {
        $bat =  "<p style=\" color: red; \">All fields are required</p>";
    }elseif( !filter_var($email, FILTER_VALIDATE_EMAIL) ){
        $bat =  "<p style=\" color: red; \">Invalid email address</p>";
    }else {
        $bat =  "<p style=\" color: green; \">Data stable</p>";
    }
 

 #### Age validattion check
***php

  /**
    * Age validation
    */


    if ( $age >= 20 && $age <= 70 ) {
        $age_validation = true;
    } else {
        $age_validation = false;
    }


      //Empty value check

    if ( empty($name) || empty($email) || empty($number) || empty($age)  ) {
        $bat =  "<p style=\" color: red; \">All fields are required</p>";
    }elseif( !filter_var($email, FILTER_VALIDATE_EMAIL) ){
        $bat =  "<p style=\" color: red; \">Invalid email address</p>";
    }elseif( $age_validation == false ){
        $bat =  "<p style=\" color: red; \">Your age not support for this app</p>";
    }else {
        $bat =  "<p style=\" color: green; \">Data stable</p>";
    }
 