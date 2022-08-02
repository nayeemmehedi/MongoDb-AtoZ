## MongoDb First Terminal Command


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

  
  😮‍💨 delete :
  
  db.collection.deleteMany()
  db.collection.deleteOne()
  
  🙂 Mongoose


  
  

