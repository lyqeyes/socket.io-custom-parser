#### 0 abstract
One kind of socket.io custom parser.  Based on official socket.io-parser. 
<br/> U can register the function that will be executed before encode message or after decode message
<br/>
So that u can have the union entrance if u want to monitor  every incoming or output  message. 

#### 1 Install
```
npm i socket.io-custom-parser

```

#### 2 Usage
<h5>set parser ↓</h3>

```
let parser = require('socket.io-custom-parser');

let beforeEncode = (obj) => {
    //do something before every encode operation.
    //...
    console.log('send message:', obj);
};

let afterDecode = (obj) => {
    //do something after every decode operation.
    //...
    console.log('receive message:', obj);
};

parser.setBeforeEncode(beforeEncode);

parser.setAfterDecode(afterDecode);

```
<h5>then in socket.io, use the defined parser above as the custom parser.  need  [socket.io custom-parser example?](https://github.com/socketio/socket.io/tree/master/examples/custom-parsers) </h3>

```
const io = require('socket.io')(httpServer, {
        path: 'xxxx',
        pingTimeout: 10000,
        pingInterval: 5000,
        parser: parser
    });
```

## Gratitude ##

Thanks for [socket.io-parser](https://github.com/socketio/socket.io-parser)



