### Mongorestore
```
mongodb+srv://<user>:<password>@cpdcluster.k56ra36.mongodb.net/
```


### Or
```js
var user = await User.find({$or:[{'phone': req.body.phone},{'email': req.body.email}]}).lean().exec()
```
### Join
```js
data = await Invite.aggregate([
            { $lookup:
                    {
                        from: 'users',
                        localField: 'phone',
                        foreignField: 'phone',
                        // Below pipeline is used to show only name from Users joining
                        pipeline:[
                            {$project:{name:1}}
                        ],
                        as: 'user_data'
                    },
            }
        ]).exec()
 ```
 To work with _id join
 ```js
 data=await Category.aggregate([
        { "$addFields": { "converted_id": { "$toString": "$_id" }}},
        { $lookup:
                {
                    from: 'files',
                    localField: 'converted_id',
                    foreignField: 'additional',
                    as: 'user_data'
                },
        }
    ]).exec()
 ```
