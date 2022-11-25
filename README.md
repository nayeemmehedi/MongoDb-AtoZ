##  :grinning: MongoDb First Terminal Command


doc link : https://www.mongodb.com/docs/manual/introduction/

/////////////////
1st Part
😮‍💨

##### First start Mongodb - 😋 mongo

##### clean command - 😁 cls

start hy jbe..😊

##### database dekhao command - 😋  show dbs

##### database create - 😋 use nayeem (database name deo ,jdi na thake create krbe, jdi thake oitai swtch hbe)

##### 😃 table banaono 1 ta - 🤩 db.nayDb.insertOne({name:"nayeem"})

##### konta database active command - 😄 db

##### database r vtr collection command - 😆 show collections

##### collection r vtr koto documents ase command - 🙂 db.naydb.find() -> db.naydb.find().pretty()

ber hyr jnno - quit()
or clrt c

🙂
2nd part
🙂

### crud oparations

😮‍💨 create : 

###### insert one - db.collection.insertOne({something:"something"})
###### insert many - db.collection.insertMany( [{something:"something"} , {something:"something"}]) 

😮‍💨 read :

##### all Value  ki ase dekte chay - db.naydb.find(query={name:"nayeem"}, projection ={j j value ase tate 0 and 1 use kore show krbo ki na thik kore deya jai like name="nayeem" name : 0 dei thle name bade sob dkhbe})

#### value limit first - db.nayd.find().limit(1)
#### value limit first - db.nayd.findOne()
##### value first skip command - db.nayd.limit(1).skip(1)


😮‍💨 update :

##### db.collection.updateOne(<filter>,<update>)   -> filter - {nameL:'nayeem'}  => update {$set:{name:"mehedi"}}
  
##### db.collection.updateMany(<filter>,<update>)
  
  #### db.collection.updateMany ( {age : {$gt : 20 }} , {$inc : {age : 2}} )
  
  
  '''''
  skills : ["javascript","python"] => ["js","python"]

  db.collection.updateMany ({skills : {exists : true} , {$set : { "skills.1" :" js "}}})
  
  
  jdi push krte chai
  
  db.collection.updateMany ({skills : {exists : true} , {$push : { "skills" :" bangla "}}})
  
  #### jdi onkk gula value dete chai skills r
  
   db.collection.updateMany ({skills : {exists : true} , {$push : { "skills" :{$each :["bangla","english","torrent"] }}})
  
  ### jodi konta bad dete chai ["bangla ","english "] , er vtr thke 1 ta bad dete chai
   db.collection.updateMany ({skills : {exists : true} , {$pull : { "skills" :" bangla "}}})
  
  ### onk gula soraite chaile 1 sthe
  db.collection.updateMany ({skills : {exists : true} , {$pullAll : { "skills" :["bangla","english","torrent"] }})
  
  
  ### RENAME COLLUME
  
  {name :"saad",age :23}
  
   db.cl.updateOne({name :"saad"},{$rename : {age :"base"}})
  
   {name :"saad",base :23}
  .....
  
 #####  ...column delete
  
     db.cl.updateOne({name :"saad"},{$unset : {base :""}})
  

  
  
  
  
  
  
  
  😮‍💨 delete :
  
  db.collection.deleteMany()
  db.collection.deleteOne()
  
  
  ....................................
  
  Quearing Data :
  
  .....................................
  
  db.collection.find() - sob chole asbe
  db.collection.find().count()  - koto gula ase
  db.collection.find().limit(2) - limit
  
  db.collection.find().skip(2).limit(2) - first skip 2 ta koro trpr 2 ta dekhao
  
  db.collection.find().sort({age : -1})  -> -1 mane boro thke choto sort  hy jabe
  db.collection.find().sort({age : 1})  -> 1 mane choto thke boro sort  hy jabe
  
  db.collection.find().sort({age : 1,name:1}) =>age 2 ta samne hy name dara short krbe
  db.collection.find().projection({name:1,age:0}) =>name e onle lgbe, age lgbe na
  
  db.collection.find({name:"saad}) -> saad name filter koro
  
  skills = ["js","py"]
  
  db.collection.find({skills:"py"})
  
  db.collection.find({skills : ["js","py"]}) -> exact amn vbei hbe
  
  
  exm. { name : [ {city :dhaka} ] }
  
   db.collection.find({"name.city":"dhaka"})
  
  
  
  
  .....................
  operator
  .....................
  
  
  gt - greater then
  gte -greater then equal

  lt- less then
  lte - less then equal
  eq - qual
  ne -not equal  (value r soman na like 20 thkle ota bade sob)
  in - array nei jar vtr j ase tai khujbe
  nin - array r vtr j ase ta bad khujbe
  
  
  
------------query operatror
  ------------
  
  age 22 find--> db.user.find({age:22})
  
  age 22 greater then find --> db.user.find({age : {$gt : 22 }}) 
  
  age 22 less then find --> db.user.find({age : {$lt : 22 }}) 
  
  saad and jarif j kono pailei deo find --> db.user.find({name : {$in : ["saad","jarif"]}}) 
  
  saad and jarif 2 ta bade deo deo find --> db.user.find({name : {$nin : ["saad","jarif"]}}) 
  
  and condition --> db.user.find({$and : [{name : 'nayeem', age : 20 } ]  })
  same - db.user.find({name : 'nayeem', age : 20 })
  
  
  .....
  
  exists -->  db.user.find({age : {$exists : true }})  false -> jdr age nai tdr 
  
  type --> db.user.find( {address : {$type :"string"})
  
  ...
  
  { name :"robin", spent : 400, budget:400 },
  {name :"sakil",  spent  :300, budget:400 },
  {name :"joni",  spent  : 200 ,budget:400 },
  
  kar tk kom sevbe sort koro  -- > db.user.find({expr : {$lt : ["$budget ","$spent"] })
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  🙂 Mongoose


  
  

