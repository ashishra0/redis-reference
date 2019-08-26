## Advanced Commands


### MSET

→ Sets multiple keys to respective values
→ Replaces existing values with new ones

### MSETNX

→ Sets multiple keys to respective values as long as none of the keys exists.
→ Will not overwrite existing values
→ Even if one key already exits this command wont work

### MGET

→ Returns values of all specified keys
→ Returns nil if keys don’t hold a value

### APPEND

→ if a key already exists and is a string, the value will be appended at the end of the string
→ if the key does not exist, it works as a SET command

```
SET foo ashish
APPEND foo rao
```
This will return “ashishrao”


### GETRANGE

→ returns the substring of a string value
→ Determined by offsets start and end
→ Negative offsets can be used to start from the end of the string
```
GETRANGE foo 0 1
```
This will return “as”


### RENAME

→ renames a key
→ returns an error if the key doesn’t exist
```
RENAME foo bar
```
Here the key foo is renamed to bar


### GETSET

→ Automatically sets key to value and returns the old value
→ Returns an error when key exists
```
 GETSET bar 100
```
This will set the bar key to a new value of 100 and will return the old value i.e “ashishrao”


### SETEX

→ set key to hold a string value and timeout after a given seconds
```
    SETEX foo 10 hello
```
This will set the value of hello to key foo for a duration of 10 seconds


### PERSIST

→ remove existing timeout on a key
```
    PERSIST foo
```

This will remove the timeout of 10 seconds on foo key

---