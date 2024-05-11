# nc (netcat)

Arbitrary TCP and UDP connections and listens.

## Listen to port 8080

```Shell
$ nc -L 8080
```

## Example Usage Making a HTTP Request

```Shell
$ nc example.com 80
```

After running the command, enter the HTTP request payload:

```
GET / HTTP/1.1
Host: example.com
User-Agent: nc
Accept: */*

```

The server will respond with the HTTP Response:

```
HTTP/1.1 200 OK
Age: 362563
Cache-Control: max-age=604800
Content-Type: text/html; charset=UTF-8
Date: Sat, 11 May 2024 19:13:57 GMT
Etag: "3147526947+gzip+ident"
Expires: Sat, 18 May 2024 19:13:57 GMT
Last-Modified: Thu, 17 Oct 2019 07:18:26 GMT
Server: ECAcc (dad/5FDE)
Vary: Accept-Encoding
X-Cache: HIT
Content-Length: 1256

<!doctype html>
<html>
<head>
    <title>Example Domain</title>
		...
</head>

<body>
<div>
    <h1>Example Domain</h1>
		...
</div>
</body>
</html
```


## Example Usage Responding to a HTTP Request

Terminal 1

```Shell
$ nc -l 8080
```

After curl on terminal 2 makes the request to port 8080, the request is printed out:

```
GET /foo/bar HTTP/1.1
Host: localhost:8080
User-Agent: curl/8.4.0
Accept: */*
Custom-Header: baz

```

A HTTP response can then be entered to be sent back to the curl client.

```
HTTP/1.1 200 OK
Date: Mon, 23 May 2005 22:38:34 GMT
Content-Type: text/plain; charset=UTF-8
Content-Length: 12
Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
Server: netcat/0.0.0.0 (Unix)
ETag: "3f80f-1b6-3e1cb03b"
Accept-Ranges: bytes
Connection: close

Hello World!
```

Terminal 2

```Shell
$ curl -i -H"Custom-Header: baz" http://localhost:8080/foo/bar
*   Trying [::1]:8080...
* connect to ::1 port 8080 failed: Connection refused
*   Trying 127.0.0.1:8080...
* Connected to localhost (127.0.0.1) port 8080
> GET /foo/bar HTTP/1.1
> Host: localhost:8080
> User-Agent: curl/8.4.0
> Accept: */*
> Custom-Header: baz
>
< HTTP/1.1 200 OK
< Date: Mon, 23 May 2005 22:38:34 GMT
< Content-Type: text/plain; charset=UTF-8
< Content-Length: 12
< Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
< Server: netcat/0.0.0.0 (Unix)
< ETag: "3f80f-1b6-3e1cb03b"
< Accept-Ranges: bytes
< Connection: close
<
* Closing connection
Hello World!
```

