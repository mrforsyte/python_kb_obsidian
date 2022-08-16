```py
import sqlite3
#just to use sqlite3 database within our programm
```

## NOT THE BEST STUFF BUT TO START WITH SOMETHING THERE IT GOES


````py

import sqlite3
#connection = sqlite3.connect(':memory:')

#connection = sqlite3.connect('customer.db')

#create a cursor
#cursor = connection.cursor()


#create a table

#cursor.execute(" CREATE TABLE customers (id integer primary key autoincrement,first_name text, last_name text, email_address text);")
#cursor.execute("INSERT INTO customers VALUES(3,'JB','El','jb@gma.com');")

many_customers = [
(4,'Bro','Ho','ggg@gmail.com'),
(5,'Gro','Do','broho@gmail.com'),
(6, 'Flo','Mo','flo@gmail.com')

]


def delete_one(id):
	connection = sqlite3.connect('customer.db')
	cursor = connection.cursor()
	cursor.execute("DELETE  FROM customers WHERE id = (?)", id)
	connection.commit()
	connection.close()


def show_all():
	connection = sqlite3.connect('customer.db')
	cursor = connection.cursor()
	cursor.execute("SELECT * FROM customers;")
	results = cursor.fetchall()

	for item in results:
		print(item)


	connection.commit()
	connection.close()

	return results



def add_user(id,first_name,last_name,email_address):
	connection = sqlite3.connect('customer.db')
	cursor = connection.cursor()
	cursor.execute("INSERT INTO customers VALUES (?,?,?,?)", (id,first_name,last_name, email_address))
	connection.commit()

	result = cursor.execute("SELECT * FROM customers WHERE first_name =(?)",[first_name])
	print(result.fetchone())
	connection.close()





# Update records


#DELETE 
#cursor.execute("DELETE FROM customers WHERE rowid = 6;")

'''
cursor.execute("""

	UPDATE customers SET first_name = "Bob"
					WHERE rowid = 1

	""")

'''

#Order by
#cursor.execute("SELECT rowid, * FROM customers ORDER BY rowid ASC LIMIT 3 ")


#cursor.execute(" CREATE TABLE customers_2 (first_name text, last_name text, email_address text);") 
#cursor.execute("DROP table customers_2")
#connection.commit()
#cursor.executemany('INSERT INTO customers VALUES(?,?,?,?)', many_customers)

#cursor.execute("SELECT rowid,* FROM customers;")
#cursor.execute("SELECT * FROM customers WHERE email_address LIKE '%gmail.com' ")
#results = cursor.fetchall()


#for item in results:
#	print(item)







'''
Data types in Sqlite

#NUILL
#INTEGER
#REAL
#TEXT
#BLOB

FANCY commands in sqlite


#"SELECT rowid,* FROM customers; - to select everything and rowid, sqlite does it automatically, no need to bother with silly stuff
cursor.execute("SELECT rowid, * FROM customers WHERE  first_name LIKE '%Rro' OR last_name = 'Do' ")
"SELECT rowid, * FROM customers ORDER BY rowid ASC LIMIT 3 ")

fetchone()
fetchmany(6)
fetchall()

'''
#PRAGMA table_info(tablename); # to list all column names from the table


#fancy query
#WHERE email_address LIKE '%gmail.com'
"""
print('executed succesfully;')
connection.commit()
connection.close()
"""






from database import show_all
from database import add_user
from database import delete_one


show_all()
print('===============================')
#add_user(13,'geeeee','gg','gggg@ggeee.com')
delete_one(['13'])
print('===============================')
show_all()





```