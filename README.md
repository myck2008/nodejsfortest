# nodejsfortest

var express = require('express');
var app = express();
var fs = require("fs");


app.get('/countries', function (req, res) {
   fs.readFile( __dirname + '/countries.json', 'utf8', function (err, data) {
	if (err) throw console.log( err );

       console.log( data );
       res.end( data );
   });
})

app.post('/additems', function (req, res) {
   fs.readFile( __dirname + "/" + "items.json", 'utf8', function (err, data) {

	fs.writeFile('item.txt', JSON.stringify(data), function (err,data) {
  	    if (err) {
    	        return console.log(err);
	    }
  	});
   });
})

var server = app.listen(3000, function () {

  var host = server.address().address
  var port = server.address().port


})
