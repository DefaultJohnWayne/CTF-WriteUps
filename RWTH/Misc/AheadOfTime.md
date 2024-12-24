# Ahead Of Time

This is the description of the challenge:

> 
    Nah, my maths teacher is crazy. 100 questions and only 1 second to solve for each?!?!?!

    p/s: please test it out locally first. please.
    nc 34.169.13.49 7001 
>

I received an attachment file called **ahead_of_time**

First of all, just run it locally first to ensure it can run. When you run it, a math quiz will appear and you have to answer within 1 second which is humanly impossible.....

But worry not, run the executeable file but it said no permission. So all you have to do is change the permission.

``` 
$chmod +x ahead_of_time
```

Once you are able to execute the file, actually just same math quiz with the local one, but yea this is the beginning !!

Create a new python script, name it anything you want, for me i name it calculator.py:

```python
import socket
import re
import time

HOST = "34.169.13.49"  # Replace with the correct host
PORT = 7001  # Replace with the correct port

# Create a socket object and connect to the server
sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
sock.connect((HOST, PORT))

while True:
    # Receive data from the server (up to 1024 bytes)
    output = sock.recv(1024).decode('utf-8')
    print(f"Server Output: {output}")  # Print output for debugging

    # Look for the math question in the format 'number operator number'
    question_match = re.search(r'(\d+)\s*([-+\*/])\s*(\d+)', output)

    if question_match:
        first = int(question_match.group(1))
        operator = question_match.group(2)
        second = int(question_match.group(3))

        # Solve the question based on the operator
        if operator == '-':
            result = str(first - second)
        elif operator == '*':
            result = str(first * second)
        elif operator == '+':
            result = str(first + second)
        elif operator == '/':
            # Perform division and handle floating-point results
            result = str(first / second)

        print(f"Solved: {first} {operator} {second} = {result}")

        # Send the result back to the server
        sock.send(result.encode() + b"\n")
    else:
        # If no math question was found, print the output and stop
        print("No question found or end of challenge. Output was:")
        print(output)
        break

    # Wait for 1 second before reading the next question
    time.sleep(1)

sock.close()  # Close the socket connection when done
```

When you execute the python script, the script will automatic answer 100 math quizzes. Just wait for it, be patient ^^

At the end of the output, you will get the flag!! Woohoo!

> Congrats Commando! Take this flag:UCC{2 plus 2 is 4, minus 1 is 3, quick mathss !@#}

### Flag: UCC{2 plus 2 is 4, minus 1 is 3, quick mathss !@#}

