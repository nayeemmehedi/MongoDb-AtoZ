### Vs code Crud operation example :

##### create

                     
                     const savemodule =async(req,res,next)=>{
                     
                                 try{
                                     const db = getdb()
                                     
                                     const result = await db.collection("tools").insertOne(req.body)
                                     
                                      if(!result.insertedId){
                                     
                                      res.status(400).send({status :"failed"})
                                     
                                     
                                     } else {
                                     
                                     res.send("done")
                                     
                                     
                                    }
                                    
                                  }
                                     
                      
                                 }catch(err){
                                 
                                      next(err.message)
                                
                                 }
                     


#### Find 


                         
                     const savemodule =async(req,res,next)=>{
                     
                                 try{
                                     const db = getdb()
                                     
                                     const result = await db.collection("tools").find().toArray()
                                     
                                 
                                     
                                    
                                     res.send("done")
                                     
                                     
                                 
                                    
                                  }
                                     
                      
                                 }catch(err){
                                 
                                      next(err.message)
                                
                                 }



#### Find by Id 

 
                                const savemodule =async(req,res,next)=>{
                     
                                 try{
                                     const db = getdb()
                                     
                                     const  {id} =  req.params
                                     
                                     if (!ObjectId.isValid(id)){
                                     res.status(400).send("Id havent organazation properly..")
                                     }
                                     
                                     const result = await db.collection("tools").findOne({_id : ObjectId(id)})  
                                     
                                     
                                     if (!result){
                                        res.status(400).send("Cant find anything in this id")
                                     
                                     }else{
                                      res.send("done")
                                     }
                                     
                                     
                                     
                                    
                                 
                                     
                                     } else {
                                     
                                     res.send("done")
                                     
                                     
                                    }
                                    
                                  }
                                     
                      
                                 }catch(err){
                                 
                                      next(err.message)
                                
                                 }
                                 
                                 
                                 
 ### FIND limit page ->      
                                
                                
                            allroute = async (req, res, next) => {
                                  const db = getDb();

                                  const {limit, page } =req.query

                                  try {
                                    const value = await db
                                      .collection("newUser")
                                      .find()
                                      .skip(+limit * page)
                                      .limit(+limit)
                                      .toArray();
                                    res.status(200).send({ success: true, data: value });
                                  } catch (error) {
                                    res.send(error.message);
                                    next(error)
                                  }
                                };

                                 
                                 
                                 



### update  by Id
                         
                          const   Updatemodule =async(req,res,next)=>{
                     
                                 try{
                                     const db = getdb()
                                     
                                     const  {id} =  req.params
                                     
                                     if (!ObjectId.isValid(id)){
                                        return res.status(400).send("Id havent organazation properly..")
                                     }
                                     
                                     
                                     const result = await db.collection("tools").updateOne({_id : ObjectId(id)},{$set : req.body})  
                                     
                                     
                                      if (!result.modifiedCount){
                                        return  res.status(400).send("Cant find anything in this id")
                                     
                                    }
                                     
                                     res.send("done")
                                 
                                     
                                   
                                     
                                    }
                                    
                                  }
                                     
                      
                                 }catch(err){
                                 
                                      next(err.message)
                                
                                 }
                                 
                                 
### delete count : 

                       
                        const   deletemodule =async(req,res,next)=>{
                     
                                 try{
                                     const db = getdb()
                                     
                                     const  {id} =  req.params
                                     
                                     if (!ObjectId.isValid(id)){
                                        return res.status(400).send("Id havent organazation properly..")
                                     }
                                     
                                     
                                     const result = await db.collection("tools").deleteOne({_id : ObjectId(id)},{$set : req.body})  
                                     
                                     
                                      if (!result.deletedCount){
                                        return  res.status(400).send("Cant delete anything in this id")
                                     
                                    }
                                     
                                     res.send("done")
                                 
                                     
                                   
                                     
                                    }
                                    
                                  }
                                     
                      
                                 }catch(err){
                                 
                                      next(err.message)
                                
                                 }

                       
                     
                     
