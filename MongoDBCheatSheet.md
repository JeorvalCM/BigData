# Cheat sheet


# Student: Jeorval Jose Cano Morales

## First Steps

#### Command: show dbs


As its name says shows all the databases in the server
<img src = imagenes/showdbs.jpg>

#### db


Shows the name of the current database you are in



<img src = imagenes/db.jpg>

#### Use


This command works to switchs between the databases of the server


<img src = imagenes/switch.jpg>

#### Show collections 


Shows all the collections of the database you are currently in


<img src = imagenes/colllections.jpg>

#### Insert


It adds a new value inside the colecction you specified and if this collection doesn't exits this command makes it 


<img src = imagenes/insert.jpg>


As you can see in the image if the value is correctly inserted returns 1



The syntas is must be in the following way


db.COLLECTIONNAME.insert({CATEGORY1: value, CATEGORY2: Value})

#### Find and pretty



Find: Return the elements found with the arguments you passed if there is nor arguments returns all the documents
Pretty: Print the document as a JSON format

<img src = imagenes/find.jpg>


Using one argument in find()


<img src = imagenes/find2.jpg>



Using two arguments n find() and pretty


<img src = imagenes/findpretty.jpg>



Find inside document, to find inside a document inside a document you use the name of the category and you add a dot and the name of the attribute, for example, find({rate.Calificador2: 10})
<img src = imagenes/find3.jpg>


#### findOne()


return only one and it is the first to be found



<img src = imagenes/findone.jpg>

#### Remove


Eliminate the document matched with your arguments


<img src = imagenes/remove.jpg>


In this case removed two elements

#### Update 


Command to modify information of the documents


<img src = imagenes/update.jpg>


Using multi
<img src = imagenes/updatemulti.jpg>


Other arguments for update, $inc, increments the value by the nmber you pass


<img src = imagenes/updateinc.jpg>


Eliminating fields in all the documents


<img src = imagenes/unset.jpg>



Renaming a field


<img src = imagenes/rename.jpg>

#### Comparison query editors


There exists comparison commands an are:


$gte: greater than or equal to


$gt: greater than


$lte: less than or equal to


$ne: not equal to


example: 



<img src = imagenes/lt.jpg>


combaining ranges


<img src = imagenes/combaining.jpg>



Using find and excluiding fields we don't want to see



<img src = imagenes/findes.jpg>



##### Count method


<img src = imagenes/count.jpg>

##### sort method


ascending
<img src = imagenes/ascending.jpg>


descending
<img src = imagenes/descending.jpg>

##### limit
limit the printing
<img src = imagenes/limit.jpg>


##### skip
skips the elements 
<img src = imagenes/skip.jpg>

#### Aggregations


<img src = imagenes/group.jpg>


<img src = imagenes/totalsum.jpg>
