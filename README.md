# ssjson
ssjson is JSON based python library with various json operation



# USUAGE 

#creating file<br>
conn = connect("testing")

#creating table
conn.create([{'name':'','age':''}])

#inserting data into json
conn.insert({'name':'abcd','age':'2345'})

#renaming data in json
conn.alter_rename_column('name','full_name')

#adding key in json
conn.alter_add_column('height')

#removing a key 
conn.delete('height')

#updating key  with value
conn.update_with_where({'full_name':'hello world','age':'2222222222222222'},{'age':'2345'}) 

#select and print multiple keys
conn.select_multiple(['full_name','age'])

#selecting multiple keyc with condition
conn.select_multiple_with_where(['full_name','age'],{'age':'2222222222222222','full_name':'hello world'})

#selecting all data with condition
conn.select_all_with_where({'full_name':'hello'})

##printing all data
conn.select_all()








# USUAGE Using SQL

## Below is the SQL query for all the operation happened above


conn = connect("testfile")


query="create table tablename(id text , name text , dob text)"
conn.execute(query)


print('--------------')
query="INSERT INTO tablename (full_name,dob) valuesss(Bud,22);"
conn.execute(query)

print('--------------')
query="ALTER TABLE table_name RENAME COLUMN full_name TO name;"
conn.execute(query)


print('--------------')
query="ALTER TABLE table_name ADD COLUMN code;"
conn.execute(query)


print('--------------')
query="ALTER TABLE table_name DROP COLUMN code;"
conn.execute(query)


print('--------------')
query="UPDATE tablename set dob=23,name=sand where name=Bud"
conn.execute(query)


print('--------------')
query="select id,name,dob from tablename"
conn.execute(query)


print('--------------')
query="select id,name from tablename where name=sand"
conn.execute(query)


print('--------------')
query="select * from tablename where name=sand"
conn.execute(query)


print('--------------')
query="select * from tablename"
conn.execute(query)

