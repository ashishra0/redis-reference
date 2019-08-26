To set a key-value pair

- SET command
```
SET foo 100
```

foo is the key and 100 is the value.

To retrieve a value

- GET command
```
GET foo
```

This will output 100

To increment a value

- INCR command
```
INCR foo
```

This will output 101, since originally foo was set to 100

To decrement a value

- DECR command
```
DECR foo
```

This will output back to 100, since we had incremented foo by 1

To check if a value exists for a specified key

- EXISTS command
```
EXISTS foo
```

This will output either 1 or 0. 1 if the value exists and 0 if the value doesn’t exists

To remove a key-value pair

- DEL command
```
DEL foo
```

This will output in 1 or 0. 1 if the record was deleted, 0 if the record wasn’t deleted

To write to a file

- (>) sign
```
GET foo > filename.txt
```

This will create a file with specified name and will write the value of foo to that.

To monitor redis

- Go to redis-cli and type monitor.
- Then it will just monitor everything you do in redis-cli in another terminal

To remove all records

- FLUSHALL command
```
FLUSHALL
```

It will output ok to indicate that all records were deleted.

Using keyspaces when creating values

for ex: Let’s say we want to create a server object which will have different values associated with that server

```
SET server:name "name"
SET server:port "port number"
```

These don’t need to be permanent. Redis allows us to set expiration time on any data we want to.

- EXPIRE command
```
EXPIRE server:name 120
```

server:name key will expire in 120 seconds and after that the GET command on server:name will output 0 to indicate that it doesn’t exist anymore in the memory

To keep a check on the time left before the record expires

- TTL command
```
TTL server:name
```

It will output the seconds left to expire