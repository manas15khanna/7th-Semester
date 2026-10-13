[[Big Data/Unit 1|Unit 1]]
[[Unit 2]]
[[Unit 3]]

Experiment 7:
Create a collection product (Name, price, Units, discount)]
1. db.create Collection, "Product"
2. db.product.insertone({name:"washing machine", price:20000, Unit: 1, discount:2500})
3. To display all the documents 
	1. db.tname.find() 
4. To find discount more than 2000 
	1. db.product.find() => db.product.find ()
5. To display document where unit is less than or equal to 10 
	1. db.prodduct.find({"unit":{$less:10}})
6. To display documents where price is greater than 100 and discount is less than 10% 
	1. db.product.find({$and:discount:{lt:"10%"}},{price{gt:100}})
7. To display documents where discount is either or 10 or 20
	1. db.product.find{$or:\[ {discount :"10%"\},{discount:"20%"}]}
8. To remove all documents where unit=0
	1. db.product.deletemany({unit:0})
9. to identify and remove the last product of the list
	1. 