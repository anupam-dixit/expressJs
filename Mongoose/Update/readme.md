### Update 
```js
const data=await Category.updateOne({_id:req.body._id}, {
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
If updated document is needed
```js
const data=await Category.findOneAndUpdate({_id:req.body._id}, {
        title:req.body.title,
        description:req.body.description,
        active:req.body.active,
    },{returnDocument:'after'})
```
Here key part is returnDocument code
