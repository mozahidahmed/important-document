#server teke man ana

async function run(){
 try{
    await client.connect();
    const userCollection=client.db('car-service').collection('service');
    
  
          app.get('/service',async (req,res)=>{
            const query={};
          const cursor=userCollection.find(query);
          const service=await cursor.toArray();
          res.send(service);
          });
   } finally{}
}
run().catch(console.dir);
