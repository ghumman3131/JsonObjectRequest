# JsonObjectRequest

<?php

$connection = mysqli_connect('localhost','root','');

mysqli_select_db($connection , 'library');

$result = mysqli_query($connection , "select * from user ");


$namesArray = array();


while ( $row = mysqli_fetch_array($result))
	
	{
		
		$pass = $row['password'];
		$mobile = $row['mobile'];
		
		$keyValuePair['n'] = $row['name'];
		
		array_push($namesArray , $keyValuePair);
		
		
		
	}
	
	$response['result'] = $namesArray;
	
	echo json_encode($response);
	
	
	?>
