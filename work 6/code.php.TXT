<? php

$firstname=$_POST['firstname'];
$lastname=$_POST['lastname'];
$email=$_POST['email'];
$address=$_POST['address'];
$password=$_POST['password'];
$confirm password=$_POST['password'];



//database connection
$conn =new mysqli('localhost','root','test');

if( $conn->connection_error){
die('connection failed :' $conn->connection_error);
}else{
$stmt= $conn->prepare("insert into registration( firstname,lastname,email,address,password,password)
values(?,?,?,?,?,?)");

$stmt->bind_param("ssssss", $firstname, $lastname, $email, $password, $confirm password);

$stmt->execute();
echo "ok done..";
$stmt->close();
$conn->close();
}

?>
