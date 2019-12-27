# How to Serve Static File

In App.js
```
const path = require("path");
```

Create a Folder named "public" and put your static file
Now:
```
app.use('/pub', express.static('./public'));
```
```
app.get('/pub/style.css', (req, res) => {
  res.sendFile(path.resolve(__dirname, './public/style.css'));
});
```

Ref: 5.4 (Anam Ahmed)
