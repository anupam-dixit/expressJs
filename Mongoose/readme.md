### Or
```js
var user = await User.find({$or:[{'phone': req.body.phone},{'email': req.body.email}]}).lean().exec()
```
