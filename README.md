mongoose

#### schema

##### basic schema

         const { Schema } = mongoose;

         const blogSchema = new Schema({
           title:  String, // String is shorthand for {type: String}
           author: String,
           body:   String,
           comments: [{ body: String, date: Date }],
           date: { type: Date, default: Date.now },
           hidden: Boolean,
           meta: {
             votes: Number,
             favs:  Number
           }
         });







#### email: {
   --> :carousel_horse: type: String,
    
  --> :carousel_horse:  required: true,
  
            required : [true , "please provide a name in this product"],
   
    
 --> :carousel_horse:  unique: true,
    
 --> :carousel_horse:  lowercase: true,
    
-->  :carousel_horse:  validate: (value) => {
      return validator.isEmail(value)
    },
    
    ..
    
-->  :carousel_horse:   enum : {
      values : ["kg", " litre" , "pcs"],
      message : "value must be kg/litre/pcs"
    },
    
    ..
    
 -->  :carousel_horse: trim : true,
    
 -->  :carousel_horse:  minLength : [3, "Min Length be at least 3 charactors"],

 --> :carousel_horse:  maxLength : [10, "Max Length be at least 3 charactors"],
    
 -->  :carousel_horse:  min : [0,"price can't be negative"],
     
-->  :carousel_horse:  max : [10,"price can't be negative"],

 ..
    
 --> :carousel_horse:  validate :{
      validator : (value)=>{
        const inInteger = Number.isInteger(value)
        if(isInteger){
          return true
        }else{
          return false
        }
      },
      
    },
    
    
  }
  
  ambet and reference
  
  ### ref
  jdi suppier alada akta jaiga thke ashe onno model thke 
  
           supplier {
           type : mongoose.Schema.Types.ObjectId,
           ref : "supplier"

           }
  
  #### same jnis embet kore rkte hbe 
  
  catagories : [{
  type : String,
  
  _id : mongoose.Schema.Types.ObjectId
  }
  ]
  
  
  .##
  .##
  
  ## post korar way mongoose e 2 ta 
  
  1 .save
  model r akta instance create krte hbe 
  const product = new Product(req.body)
  product.save()
  
  #### example
  
            app.post("/", async (req, res) => {
            
              try {
                const value = new Number(req.body);
                const result = await value.save();

                res.send({
                  status: "success",
                  data: result,
                });
                
              } catch (error) {
                res.status(400).send({
                  status: "failed",
                  message: error.message,
                });
              }
             });
             
             
  2.create 
  
  #### example 
  
                   app.post("/", async (req, res) => {
                   
                    try {

                      const value = await Number.create(req.body)
                      
                      res.send({
                        status: "success",
                        data: value,
                      });
                      
                      
                    } catch (error) {
                    
                      res.status(400).send({
                        status: "failed",
                        message: error.message,
                        
                      });
                    }


                  });
                  
                  
                  
 #### midddleware
 
 datasave hyr thik ager muhutte,jokhn post kora hy tkhn first eikhne asbe pore save hbe..
    

                  valueSchema.pre("save", function (next) {
                    console.log(this)
                    if(this.product == "ballon") {
                      this.product = "biscuit";
                      console.log(this)
                    }

                    next();
                  });
                  

                     valueSchema.post("save", function (doc, next) {
                       next();
                     });
                     
                     
 ### query method
 
 

