# SSJSON
ssjson is JSON based python library with various json operation



# USAGE 

#creating file<br>
conn = ssjson.connect("testing")

#creating table<br>
conn.create([{'name':'','age':''}])

#inserting data into json<br>
conn.insert({'name':'abcd','age':'2345'})

#renaming data in json<br>
conn.alter_rename_column('name','full_name')

#adding key in json<br>
conn.alter_add_column('height')

#removing a key <br>
conn.delete('height')

#updating key  with value<br>
conn.update_with_where({'full_name':'hello world','age':'22'},{'age':'2345'}) 

#select and print multiple keys<br>
conn.select_multiple(['full_name','age'])

#selecting multiple keyc with condition<br>
conn.select_multiple_with_where(['full_name','age'],{'age':'22','full_name':'hello world'})

#selecting all data with condition<br>
conn.select_all_with_where({'full_name':'hello'})

##printing all data<br>
conn.select_all()








# USAGE Using SQL

## Below is the SQL query for all the operation happened above


conn = ssjson.connect("testfile")<br>


query="create table tablename(id text , name text , dob text)"<br>
conn.execute(query)<br>


query="INSERT INTO tablename (full_name,dob) valuesss(Bud,22);"<br>
conn.execute(query)<br>

query="ALTER TABLE table_name RENAME COLUMN full_name TO name;"<br>
conn.execute(query)<br>


query="ALTER TABLE table_name ADD COLUMN code;"<br>
conn.execute(query)<br>


query="ALTER TABLE table_name DROP COLUMN code;"<br>
conn.execute(query)<br>


query="UPDATE tablename set dob=23,name=sand where name=Bud"<br>
conn.execute(query)<br>


query="select id,name,dob from tablename"<br>
conn.execute(query)<br>


query="select id,name from tablename where name=sand"<br>
conn.execute(query)<br>


query="select * from tablename where name=sand"<br>
conn.execute(query)<br>


query="select * from tablename"<br>
conn.execute(query)<br>

