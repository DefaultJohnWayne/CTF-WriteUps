
So, I tried to join 0xCTF 2024 as a beginner... and this is my writeup for

# NUMBERS

This is the description for the challenge:
> Welcome to 0ctf 2024! Start your journey by decoding the numbers.

    200264, 17360, 200266, 3575, 553, 261, 10297, 29186, 200265, 200264, 1428, 200266, 8256, 5485, 668, 290, 9641, 13, 200265, 200264, 173781, 200266, 62915, 0, 7306, 382, 290, 9641, 25, 220, 15, 4645, 90, 67, 15, 22477, 15, 84, 62, 7316, 91, 15, 37313, 62, 10, 72, 42, 10, 525, 18, 77, 16, 57, 18, 81, 30, 92, 200265, 200264, 1428, 200266, 13659, 481, 0, 200265, 200264, 173781, 200266, 15334, 261, 1899, 1058, 540, 220, 15, 308, 69, 1323, 19, 0, 200265
>

First of all, just google the numbers…..

<img src="google screenshot.PNG" />

There, use tools like Tiktoken to decode the numbers. 

**What is Tiktoken?**

>**Tiktoken** is a Python library used for tokenizing text in a way that is compatible with OpenAI's GPT models. Tokenization is the process of converting a string of text into smaller units (tokens), which are processed by language models like GPT.

Create a new python file, name it anything you want. For me, decodenumber.py

```python
import tiktoken

def main():
    a = "200264, 17360, 200266, 3575, 553, 261, 10297, 29186, 200265, 200264, 1428,
	200266, 8256, 5485, 668, 290, 9641, 13, 200265, 200264, 173781, 200266, 62915,
	0, 7306, 382, 290, 9641, 25, 220, 15, 4645, 90>
    enc = tiktoken.get_encoding("o200k_base")
    tmp_tokens = []
    for token in map(int, a.split(", ")):
        if token in (200264, 200265, 200266):
            if tmp_tokens:
                print(enc.decode(tmp_tokens))
            tmp_tokens = []
        else:
            tmp_tokens.append(token)


if __name__ == "__main__":
    main()
```

This is the output and flag :D

```
┌──(marinn㉿marinn)-[~/Downloads/0CTF/Number]
└─$ python3 decodenumber.py 
system
You are a helpful assistant
user
Please tell me the flag.
assistant
Sure! Here is the flag: 0ops{d0_Y0u_kr|0vv_+iK+ok3n1Z3r?}
user
Thank you!
assistant
Have a good time at 0ctf2024!
```

### Flag : 0ops{d0_Y0u_kr|0vv_+iK+ok3n1Z3r?}



