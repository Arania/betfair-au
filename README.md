Betfair JSON-RPC API for Node.js
================================================

**Important Notice**. *This library utilizes the beta version of the Betfair next generation JSON API. 

## Installation ##

    npm install betfair
    
## Synopsis ##

Login to Betfair
```JavaScript
var betfair = require('betfair');
var session = betfair.newSession('yourApllicationKey')

session.login('name','password', function(err) {
    console.log(err ? "Login OK" : "Login failed");
});
```

Request countries list
```JavaScript
var invocation = session.listCountries({}, function(err,res) {
    if(err) {
        console.log('listCountries failed');
    } else {
        for(var index in res.response.result) {
            var item = res.response.result[i];
            console.log("country:%s markets:%s", item.counry, item.markets)
        }
    }
});
```

Logout from Betfair
```JavaScript
session.logout(function(err) {
    console.log(err ? "Logout OK" : "Logout failed");
});
```
