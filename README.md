#### Mongo db Find method : 

doc -> https://www.mongodb.com/docs/manual/reference/operator/query/

 :two_hearts: rules 1 : 
 
   :skull: sob value payar jnnno..
       
       db.collection_name.find({})  
       
       
:two_hearts: rules 2 : 
 
   :skull: koita user ase total 
   
         db.collection_name.find().count()  
         
  
 :two_hearts: rules 3 : 
  
   :skull: first 10 ta skip koro and porer 50 ta dkhao
  
            db.collection_name.find().skip(10).limit(50)  
            
            
            
:two_hearts:  rules 4 : 
  
   :skull:  short koro ,age deye sort koro jdi age same hy thle name deye kro
    
            db.collection_name.find().sort({age : 1 , name : 1})
            
:two_hearts:  rules 5 : 
  
  :skull: projection
       
   kichu properties bad deye value patahano jay like amra password user r kase response pathabo na,
       
   specific kichu jnis like amr name lgbe suddhu..
       
       
             db.collection_name.find().projection({name : 1}
             
   name only deo .sthe id auto asbe ,jdi oita o na chai
       
              db.collection_name.find().projection({name : 1,_id : 0 })
       
       
 
  
:two_hearts: rules 6 : 
   
  :skull:  speecific kono kichu search krte
      
               db.collection_name.find({name :"bangla"})
               
               
 
:two_hearts: rules 7 : 
  
               user : {    skills : ["js","py"]  }
               
  :skull: jdi amn thake queary hbe ,
      
               db.collection_name.find({skills :"js"})
               
  :skull: jdi amn hy just ei array tai cacchi 
       
                db.collection_name.find({skills : ["js","py"] })
                
                
                
:two_hearts: rules 8 : 

                skills :  {  name : "nayeem",   age:30 }  ,
              
              
atar queary  

              db.collection_name.find({"skills.name" : "somrat"})

             
  
:two_hearts: rules 8 :  

                skills : [ {  name : "nayeem",   age:30 }  , {  name : "somrat",   age:20 }  ]
                         
                         
atar queary  

                 db.collection_name.find({"skills.name" : "somrat"})
                 
                 
                 
*************************:revolving_hearts:	
     
************************** :revolving_hearts:	
     
     
                   $gt  +  $gte 
                   $lt  +  $lte
                   $in  +  $nin
                   $eq  +  $ne 
                   
                   
                   {
                     in : array r vtr j thkbe ta match krte hbe,
                     nin :  array r vtr j thkbe ta bade dbe sob
                     
                   }
                     
     
     
 #### Logical :revolving_hearts:	
     
                 and  +  or  + nor  + not  =>        
           
           
EXAMPLE 
     
     
   ##### $gte
          
                    
                    db.name.fine({ age : { $gte :20 } })
                    
   ###### $in 
                     
                     db.name.find({name : {$in : ["saad ", "jarif"]}})
                     
                     
   in mane array r vtr j thkbe tai e match hyle asbe 
           
           
           
           
           
           ============
          +++++++++++++++
          ==============
          
          
   ##### and  and or array nbe always
 
                    db.name.find( {  $and : [ {name :"saad"} , {age :20 }   ]    }  )
                         
                         
 
  and akta array nbe condition sotti hyte hbe 2 tai  
  
  
  ##### not 
  
                    db.name.find({age : {$not : {$gt :20 }}})
                    
                    
                    
  #### operator  and logic
  
  
                     db.name.find({$and : [ {name : "saad"} , {age : { $gte : 20, $lt : 30 } } ]})
                     
                     
  
  ##### exist 
  
   jdr value ase tdr e only return ,  false dele nai j j seta dkhbe
   
                       db.name.find({age : {$exists : true }})
                       
                       
  ##### type 
  
                       db.name.find({age : {$type : "object" }})
         
         
  
  
  ##### regex 
  
  
                    db.name.find({ name : {$regex : //kshzh// }})
                    
                    
                    
 ************************
 %%%%%%%%%%%%%%%%%%%%%%%%
 ************************
 
 
