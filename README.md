<?php
   $host        = "host = data.ecu-shop.com";
   $port        = "port = 5432";
   $dbname      = "dbname = ecu";
   $credentials = "user = ecuapi password=b6EpF7XC2Uf7eQBj";

   

   $db = pg_connect( "$host $port $dbname $credentials"  );
   if(!$db) {
      echo "Error : Unable to open database\n";
   } else {
      echo "Opened database successfully\n";
   }

   $sql =<<<EOF
      SELECT * from data WHERE product = 'SuperConnext';
EOF;

   $ret = pg_query($db, $sql);
   if(!$ret) {
      echo pg_last_error($db);
      exit;
   } 
 
   while($row = pg_fetch_row($ret)) {

  
??????????????????????????????????????


      echo "ID = ". $row[0] . "\n"; 
   }
   echo json_encode($arr2);
   pg_close($db);
?>


