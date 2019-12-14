### TCP/IP: IP address / Port number  
**Port 80**: The port number most commonly used for HTTP requests. For example, when a client makes a request to a web server, this request is usually sent through port 80.  
![1.png](http://note.youdao.com/yws/res/181/WEBRESOURCEb7a1592e52ed0bae8f80d7c521054d5b)
**Port 5432:** The port number used by most database systems; default port for Postgres.

### Basic knowledge Postgres app
![postgres_cheatsheet.png](http://note.youdao.com/yws/res/186/WEBRESOURCE16042c3a6f49490307ee50eb620e21ff)

### Use psycopg2 to interact


```python
import psycopg2

conn = psycopg2.connect('dbname=example3')

cursor = conn.cursor()

# Open a cursor to perform database operations
cur = conn.cursor()

# drop any existing todos table
# cur.execute("DROP TABLE IF EXISTS todos;")

# (re)create the todos table
# (note: triple quotes allow multiline text in python)
cur.execute("""
  CREATE TABLE todos (
    id serial PRIMARY KEY,
    description VARCHAR NOT NULL
  );
""")

# commit, so it does the executions on the db and persists in the db
conn.commit()

cur.close()
conn.close()
```
