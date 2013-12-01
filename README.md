Web page for all output =>http://web.njit.edu/~bar25/prg2.php

Ans 1  input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, ENROLLMENT
FROM effy2011, hd2011
WHERE effy2011.UNITID = hd2011.UNITID
ORDER BY ENROLLMENT DESC 
LIMIT 10") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th>Headcount</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['ENROLLMENT'];
	echo "</td></tr>"; 
}
?>

Ans 2 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, Liabilities
FROM f1011_f1a, hd2011
WHERE f1011_f1a.UNITID = hd2011.UNITID
ORDER BY Liabilities DESC 
LIMIT 10") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th>Headcount</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Liabilities'];
	echo "</td></tr>"; 
}
?>

Ans 3 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, Netassets
FROM hd2011, f1011_f1a
WHERE hd2011.UNITID = f1011_f1a.UNITID
ORDER BY Netassets DESC 
LIMIT 10") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Netassets</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Netassets'];
	echo "</td></tr>"; 
}
?>


Ans 4 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, Netassets
FROM hd2011, f1011_f1a
WHERE hd2011.UNITID = f1011_f1a.UNITID
ORDER BY Netassets DESC 
LIMIT 10") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Netassets</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Netassets'];
	echo "</td></tr>"; 
}
?>

Ans 5 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, Revenues
FROM hd2011, f1011_f1a
WHERE hd2011.UNITID = f1011_f1a.UNITID
ORDER BY Revenues DESC 
LIMIT 10") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Revenues</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Revenues'];
	echo "</td></tr>"; 
}
?>


Ans 6 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, (Revenues / ENROLLMENT) AS Summ
FROM hd2011, f1011_f1a, effy2011
WHERE hd2011.UNITID = f1011_f1a.UNITID
AND hd2011.UNITID = effy2011.UNITID
AND f1011_f1a.UNITID = effy2011.UNITID
ORDER BY Summ") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Total Revenues per Student</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Summ'];
	echo "</td></tr>"; 
}
?>

Ans 7 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, Netassets / ENROLLMENT AS Summ
FROM hd2011, f1011_f1a, effy2011
WHERE hd2011.UNITID = f1011_f1a.UNITID
AND hd2011.UNITID = effy2011.UNITID
AND f1011_f1a.UNITID = effy2011.UNITID") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Total Netassets per Student</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Summ'];
	echo "</td></tr>"; 
}
?>
Ans8 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, Liabilities / ENROLLMENT AS Summ
FROM hd2011, f1011_f1a, effy2011
WHERE hd2011.UNITID = f1011_f1a.UNITID
AND hd2011.UNITID = effy2011.UNITID
AND f1011_f1a.UNITID = effy2011.UNITID") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Total Liabilities per Student</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Summ'];
	echo "</td></tr>"; 
}
?>
Ans 9 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, ENROLLMENT, Liabilities, Netassets, Revenues, (
Revenues / ENROLLMENT
) AS total, (
Netassets / ENROLLMENT
) AS net, (
Liabilities / ENROLLMENT
) AS lib
FROM hd2011
INNER JOIN effy2011 ON hd2011.UNITID = effy2011.UNITID
INNER JOIN f1011_f1a ON hd2011.UNITID = f1011_f1a.UNITID
ORDER BY INSTNM DESC ") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th>ENROLLMENT</th><th>Liab</th><th> Netassets</th><th>Revenues</th><th>T_Revenues</th><th>T_Net</th><th>T_Liab</th></tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td></tr>"; 
	echo $row['ENROLLMENT'];
	echo "</td></tr>"; 
	echo $row['Liabilities'];
	echo "</td><td>"; 
	echo $row['Netassets'];
	echo "</td><td>"; 
	echo $row['Revenues'];
	echo "</td><td>"; 
	echo $row['total'];
	echo "</td><td>"; 
	echo $row['net'];
	echo "</td><td>"; 
	echo $row['lib'];
	echo "</td><td>"; 
}
?>
Ans 10 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


/*$form = '<form name= "search" action="prg2.php?page=ans10" method="post">
    	<P>              
        <INPUT type=text name=find><BR>
    	<INPUT type= submit name= search value= "Search"><BR>
    	</P>
		</form>';
		
		return $form;

*/
		$result = mysql_query("select INSTNM, STABBR from hd2011 where STABBR LIKE $find");


		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>State</th> </tr>";

		while($row = mysql_fetch_array($result)){
			echo "<tr><td>";
			echo $row['INSTNM'];
			echo "</td><td>";
			echo $row['STABBR'];
			echo "</td></tr>";
} 

		echo "</table>";

		return $result;
	
?>
Ans 11 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, (
(
(
f1011_f1a.Liabilities - f0910_f1a.F1A13
) / f0910_f1a.F1A13
) *100
) AS Percentage
FROM f1011_f1a, f0910_f1a, hd2011
WHERE f1011_f1a.UNITID = f0910_f1a.UNITID
AND f1011_f1a.UNITID = hd2011.UNITID
AND f0910_f1a.UNITID = hd2011.UNITID
ORDER BY Percentage DESC ") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Percentage</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Percentage'];
	echo "</td></tr>"; 
}
?>
Ans 12 input
<?php
// Make a MySQL Connection
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


// Get all the data from the "example" table
$result = mysql_query("SELECT DISTINCTROW INSTNM, (
(
(
effy2011.ENROLLMENT - effy2010.EFYTOTLT
) / effy2010.EFYTOTLT
) *100
) AS Percentage
FROM effy2011, effy2010, hd2011
WHERE effy2011.UNITID = effy2010.UNITID
AND effy2011.UNITID = hd2011.UNITID
AND effy2010.UNITID = hd2011.UNITID
ORDER BY Percentage DESC  ") 
or die(mysql_error());  

echo "<table border='1'>";
echo "<tr> <th>College Name</th> <th> Percentage</th> </tr>";
// keeps getting the next row until there are no more to get
while($row = mysql_fetch_array( $result )) {
	// Print out the contents of each row into a table
	echo "<tr><td>"; 
	echo $row['INSTNM'];
	echo "</td><td>"; 
	echo $row['Percentage'];
	echo "</td></tr>"; 
}
?>
