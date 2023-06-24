## How to setup Redis with Python
___

1. Open command prompt and start your redis server 

2. Open a second terminal and run `pip install redis` 

3. Create a python file, import redis library, and define host variables

```python

import redis

# Declare Redis host connection
redis_host = 'localhost'

#Define Redis listening port
redis_port = 6379
```
4. Create a connection to the redis server and (optional) run a hello world test to confirm connection

```python
def redis_string():
    try:
        #Creates the connection
        r = redis.StrictRedis(
            host=redis_host, port=redis_port, decode_responses=True)
        #OPTIONAL - Hello World Test

        #Creating the key value pair with the set command
        r.set("message", "Hello World!")

        #Retrieving the data with the get command
        msg = r.get("message")
        print(msg)

    #Error Handling
    except Execption as e:
        print(e)

```

5. Maintain the connection 

```python
if __name__ == "__main__":
    redis_string()

```



### Sources:

- Bek Brace : https://www.youtube.com/watch?v=R4Y0TBrEAak 