# FireShip-RESTful-API
 I followed a FireShip API tutorial to create a RESTfull API using node and express 

```
const express = require('express');
const app = express();
const PORT = 8080;

app.use(express.json())

app.listen(
    PORT,
    () => console.log(`its alive at http://localhost:${PORT}`)
);

app.get('/tshirt', (req, res)=>
{
    res.status(200).send(
        {
            tshirt:'👕',
            size: 'large'
        }
    );
});

//post
app.post('/tshirt/:id',(req,res)=>{
    const{id} = req.params;
    const{logo} = req.body;

    if(!logo){
        res.status(418)
            .send({message:'We need a logo'});
    }

    res.send({
        tshirt:`👕 with your logo: ${logo} and ID of ${id}`,
    })
})
```

![Tux, the Linux mascot](https://github.com/vandor5676/FireShip-RESTful-API/blob/main/readmeMedia/RESTfullAPI1.gif)
