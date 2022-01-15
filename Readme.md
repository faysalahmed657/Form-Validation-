## Form Validation with file upload 
This is a practice class of php where we have to make form validation with file upload\

<img src = "form.png">

```php

	if(isset($_POST[ 'insert' ])){
		echo $name = $_POST[ 'name' ];
		echo $email = $_POST[ 'email' ];
		echo $cell = $_POST[ 'cell' ];
		echo $username = $_POST[ 'username' ];

		/**
		 * Check Email
		 * @coderstrustbd.com
		 */
		$email_arr = explode('@',$email);
		print_r($email_arr);
		$inst_mail = end($email_arr);
		print_r($inst_mail);

		$cell_start= substr($cell, 0, 3);


		if(empty($name)){
			$err['name'] = "<p style= \"color:red\">*Required</p>";
		}
		if(empty($email)){
			$err['email'] = "<p style= \"color:red\">*Required</p>";
		}
		if(empty($cell)){
			$err['cell'] = "<p style= \"color:red\">*Required</p>";
		}
		if(empty($username)){
			$err['username'] = "<p style= \"color:red\">*Required</p>";
		}

	
		if(empty($name) || empty($email) || empty($cell) || empty($username) ){
		$msg = "<p class = \" alert alert-danger\">All fields are required <button class= \"close \" data-dismiss=\"alert\">&times;</button></p>";
		}
		else if(filter_var($email, FILTER_VALIDATE_EMAIL)== false ){
		$msg = "<p class = \" alert alert-warning\">Invalid Email Address<button class= \"close \" data-dismiss=\"alert\">&times;</button></p>";
		}
		else if($inst_mail != 'coderstrustbd.com'){
			$msg = "<p class = \" alert alert-info\">Only Coderstrust Email Granted<button class= \"close \" data-dismiss=\"alert\">&times;</button></p>";
		}
		else if(in_array($cell_start,['017','018','019','015','016','013','014'])== false){
			$msg = "<p class = \" alert alert-info\">Invalid Cell Number ! !<button class= \"close \" data-dismiss=\"alert\">&times;</button></p>";
		}

		else{
		$msg = "<p class = \" alert alert-success\">Data Stable <button class= \"close \" data-dismiss=\"alert\">&times;</button></p>";
		}
	}
```

## Error Message Show
```php


```