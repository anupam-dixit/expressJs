### id validation
```js
mongoose.Types.ObjectId.isValid(req.body._id)
```
### Validate ids in database
```js
let objectIdArray = req.body.categories.map(s => mongoose.Types.ObjectId(s));
    const correctIds = await Category.find({ '_id': { $in: objectIdArray } })
    res.json(myLib.sendResponse(0, {'correct':correctIds.length,'inreq':req.body.categories.length}))
```
