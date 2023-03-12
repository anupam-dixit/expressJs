### Update 
```const data=await Category.update({_id:req.body._id}, {
        title:req.body.title,
        description:req.body.description,
        active:req.body.active,
    })
```
This returns response like this:
```json
"acknowledged": true,
"modifiedCount": 1,
"upsertedId": null,
"upsertedCount": 0,
"matchedCount": 1
```        
