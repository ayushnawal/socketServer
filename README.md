# socketServer
An example server and client that functions like a full-fledged socket application.

Socket programming done here is complete with its own custom header and content. 

It supports simaltaneous multi-connection with the help of `selector` module in python .

First, let’s start the server:

``` 
$ ./app-server.py '' 65432
listening on ('', 65432)
```

Now let’s run the client and enter a search. Let’s see if we can find something:

```
$ ./app-client.py 10.0.1.1 65432 search morpheus
starting connection to ('10.0.1.1', 65432)
sending b'\x00d{"byteorder": "big", "content-type": "text/json", "content-encoding": "utf-8", "content-length": 41}{"action": "search", "value": "morpheus"}' to ('10.0.1.1', 65432)
received response {'result': 'Follow the white rabbit. 🐰'} from ('10.0.1.1', 65432)
got result: Follow the white rabbit. 🐰
closing connection to ('10.0.1.1', 65432)
```

My terminal is running a shell that’s using a text encoding of Unicode (UTF-8), so the output above prints nicely with emojis.

Troubleshooting can be done using tools / utilities like ping or netstat.
