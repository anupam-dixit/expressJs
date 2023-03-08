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
