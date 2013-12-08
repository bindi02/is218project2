Web page for all output =>http://web.njit.edu/~bar25/prg2.php

<?php
mysql_connect("sql.njit.edu", "bar25_proj", "IsiRFkts") or die("Connection Failed");
mysql_select_db("bar25_proj")or die("Connection Failed");


$program = new program();


class program{
    function __construct(){
		$page = 'homepage';
		$arg = NULL;

		if(isset($_REQUEST['page'])) {
  		$page = $_REQUEST['page'];
		}
		
		if(isset($_REQUEST['arg'])) {
		$arg  = $_REQUEST['arg'];
		}
        
        $page = new $page($arg);
	}
	
    function __destruct(){
	}
}

abstract class page{
	public $content;

	function menu() {
		$menu = '<li><a href="./prg3.php">Homepage</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question1">Question 1</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question2">Question 2</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question3">Question 3</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question4">Question 4</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question5">Question 5</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question6">Question 6</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question7">Question 7</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question8">Question 8</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question9">Question 9</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question10">Question 10</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question11">Question 11</a> </li>';
		$menu .= '<li><a href="./prg3.php?page=question12">Question 12</a> </li>';

		return $menu;
	}

    function __construct($arg = NULL){
        if ($_SERVER['REQUEST_METHOD'] == 'GET'){
            $this->get();
		}
        else{
            $this->post();
		}
	}
    
    function get(){
	}
    
    function post(){
	}

	function __destruct(){
		echo $this->content;
	}  
}

class homepage extends page{
  	
    function get(){
		echo '<h2>Welcome to Project 2</h2> <br>';
		$this->content .= $this->menu();
	}
}
  
  
class question1 extends page{
  		
    function get(){
      	echo '<h2>Question #1</h2>';

		$this->content .= $this->question1table();
	}
	  
	function question1table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, ENROLLMENT
			FROM effy2011, hd2011
			WHERE effy2011.UNITID = hd2011.UNITID
			ORDER BY ENROLLMENT DESC 
			LIMIT 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Headcount</th> </tr>";

		while($row = mysql_fetch_array( $result )) {

		echo "<tr><td>";
		echo $row['INSTNM'];
		echo "</td><td>";
		echo $row['ENROLLMENT'];
		echo "</td></tr>";
		} 

		echo "</table>";

	return $result;
	}

	function post(){	
		print_r($_POST);
	}
}

  
class question2 extends page{
    	
    function get(){
		echo '<h2>Question #2</h2>';
		$this->content .= $this->question2table();
	}
	
	function question2table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, Liabilities
		FROM f1011_f1a, hd2011
		WHERE f1011_f1a.UNITID = hd2011.UNITID
		ORDER BY Liabilities DESC 
		LIMIT 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Liabilities</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
	
		echo "<tr><td>"; 
		echo $row['INSTNM'];
		echo "</td><td>"; 
		echo $row['Liabilities'];
		echo "</td></tr>"; 
	} 

		echo "</table>";

		return $result;
	}	
	
	function post(){	
		print_r($_POST);
	}
}


class question3 extends page{
    	
    function get(){
      	echo '<h2>Question #3</h2>';
		$this->content .= $this->question3table();
	}
	
	function question3table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, Netassets
		FROM hd2011, f1011_f1a
		WHERE hd2011.UNITID = f1011_f1a.UNITID
		ORDER BY Netassets DESC 
		LIMIT 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Net Assets</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
		echo "<tr><td>";
		echo $row['INSTNM'];
		echo "</td><td>";
		echo $row['Netassets'];
		echo "</td></tr>";
		} 

		echo "</table>";

		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}
  
  
class question4 extends page{
    function get(){
      	echo '<h2>Question 4</h2>';
		$this->content .= $this->question4table();
	}
	
	function question4table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, Netassets
		FROM hd2011, f1011_f1a
		WHERE hd2011.UNITID = f1011_f1a.UNITID
		ORDER BY Netassets DESC 
		LIMIT 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Net Assets</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
		echo "<tr><td>";
		echo $row['INSTNM'];
		echo "</td><td>";
		echo $row['Netassets'];
		echo "</td></tr>";
		} 

		echo "</table>";

		return $result;
	}
	
		
	
	function post(){	
		print_r($_POST);
	}
  
}
  
  
class question5 extends page{
   	function get(){
   	  	echo '<h2>Question #5</h2>';
		$this->content .= $this->question5table();	
	}

	function question5table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, Revenues
		FROM hd2011, f1011_f1a
		WHERE hd2011.UNITID = f1011_f1a.UNITID
		ORDER BY Revenues DESC 
		LIMIT 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Total Revenue</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
			echo "<tr><td>";
			echo $row['INSTNM'];
			echo "</td><td>"; 
			echo $row['Revenues'];
			echo "</td></tr>";
		} 

		echo "</table>";

		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}
	
class question6 extends page{
    	function get(){
    	  	echo '<h2>Question #6</h2>';

    	  	$this->content .= $this->question6table();	
		}

	function question6table() {
		$result = mysql_query("SELECT DISTINCTROW INSTNM, (Revenues / ENROLLMENT) AS Summ
		FROM hd2011, f1011_f1a, effy2011
		WHERE hd2011.UNITID = f1011_f1a.UNITID
		AND hd2011.UNITID = effy2011.UNITID
		AND f1011_f1a.UNITID = effy2011.UNITID
		ORDER BY Summ") 
		or die(mysql_error());  

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Total Revenues per Student</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
			echo "<tr><td>"; 
			echo $row['INSTNM'];
			echo "</td><td>"; 
			echo $row['Summ'];
			echo "</td></tr>"; 
		} 

		echo "</table>";

		return $result;
	}
	
	function post() {	
		print_r($_POST);
	}
  
}	


class question7 extends page{
    	function get(){
    	  	echo '<h2>Question #7</h2>';

    	  	$this->content .= $this->question7table();
		}

	function question7table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, Netassets / ENROLLMENT AS Summ
		FROM hd2011, f1011_f1a, effy2011
		WHERE hd2011.UNITID = f1011_f1a.UNITID
		AND hd2011.UNITID = effy2011.UNITID
		AND f1011_f1a.UNITID = effy2011.UNITID limit 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Total Netassets per Student</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
			echo "<tr><td>";
			echo $row['INSTNM'];
			echo "</td><td>";
			echo $row['Summ'];
			echo "</td></tr>";
		} 

		echo "</table>";

		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}	


class question8 extends page{
    	function get(){
    	  	echo '<h2>Question #8</h2>';

		$this->content .= $this->question8table();
		}

	function question8table(){
		$result = mysql_query("SELECT DISTINCTROW INSTNM, Liabilities / ENROLLMENT AS Summ
		FROM hd2011, f1011_f1a, effy2011
		WHERE hd2011.UNITID = f1011_f1a.UNITID
		AND hd2011.UNITID = effy2011.UNITID
		AND f1011_f1a.UNITID = effy2011.UNITID limit 10") 
		or die(mysql_error());

		echo "<table border='1'>";
		echo "<tr> <th>College Name</th> <th>Total Liability per Student</th> </tr>";

		while($row = mysql_fetch_array( $result )) {
			echo "<tr><td>";
			echo $row['INSTNM'];
			echo "</td><td>";
			echo $row['Summ'];
			echo "</td></tr>";
		} 

		echo "</table>";

		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}


class question9 extends page{
    	
    function get(){
      	echo '<h2>Question #9</h2>';
		$this->content .= $this->question9table();
	}
	
	function question9table(){
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
	echo "</td><td>"; 
	echo $row['ENROLLMENT'];
	echo "</td><td>"; 
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
 
		echo "</table>";
		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}


class question10 extends page{
    	function get(){
    	  	echo '<h2>Question #10</h2>';
			

		
		$this->content .= $this->question10table();
		}

	
	function question10table(){
		$form = '<form name= "search" action="prg3.php?page=question10" method="post">
    	<P>              
        <INPUT type=text name=find><BR>
    	<INPUT type= submit name= search value= "Search"><BR>
    	</P>
		</form>';
		
		return $form;


		$result = mysql_query("select INSTNM,STABBR from hd2011 where stabbr LIKE $find");


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
	}
	
	function post(){	
		print_r($_POST);
	}
  
}


class question11 extends page{
    	function get(){
    	  	echo '<h2>Question #11</h2>';

		$this->content .= $this->question11table();
		}

	function question11table(){
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
		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}


class question12 extends page{
    	function get(){
    	  	echo '<h2>Question #12</h2>';

		$this->content .= $this->question12table();
		}

	function question12table(){
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
		return $result;
	}
	
	function post(){	
		print_r($_POST);
	}
  
}
?>
