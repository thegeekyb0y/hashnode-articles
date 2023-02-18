# A frustrating end to debugging my silly error in Python

Hey guys! I love coding. I think it's so cool to be able to make computers do whatever you want. But sometimes, things don't go as planned.

In this blog post, I'm going to talk about what it's like to debug Python code and share my own frustrating experience.

%[https://giphy.com/gifs/disneychannelofficial-xZsfgxuBCMdLU9I6Hl] 

* ### About the Project
    

I was working on a project that involved connecting to an API and getting some data. I thought I had everything figured out, but then I got an error message that made me go crazy.

```python
import requests

def get_response(url):
    response = requests.get(url)
    if response.status_code == 200:
        return response
    else:
        return None

def main():
    url = "https://api.example.com/data"
    response = get_response(url)
    if response is not None:
        print("Response received")
    else:
        print("Error: Failed to retrieve response")

if __name__ == '__main__':
    main()
```

In this code, the `get_response()` function makes a GET request to a specified URL using the `requests` library. If the response status code is 200 (indicating success), the response is returned. Otherwise, None is returned.

In the `main()` function, the `get_response()` function is called with a sample URL. If the response is not None, the message "Response received" is printed. Otherwise, the message "Error: Failed to retrieve response" is printed.

* ### About the Error
    

The error message was not very helpful, and it was like this: `AttributeError: 'NoneType' object has no attribute 'status_code'`

This error message was not very informative, and I didn't know where to start looking for the root cause of the issue. I first went to the internet to know why Attribute Error occurs. It was my first time facing this error 😕

---

* ### What did I do?
    

I started by going through the code line by line, trying to find the source of the problem. I checked the API documentation, re-read the code, and even tried to Google the error message. However, I still couldn't find the root cause of the problem. It was like I was hitting a brick wall and couldn't figure out what was wrong 😑💢

As time went on, I started getting more and more frustrated. I had been working on this for hours, and I still had no idea what was going on. I started to feel like I was wasting my time and getting nowhere.

**I decided to quit the project after wasting half the day sorting the error. I got hopeless.**

%[https://giphy.com/gifs/TRgyI2f0hRHBS] 

---

* ### New Day, New Motivation and the Error Sorted!
    

I came back again to the project, I decided to try a different approach this time. I debugged again and after researching some more time, I found the reason of the error.

#### Reason of the Error:

This error occurred when the `response` object returned by `get_response()` was None, which can happen if the request fails or if the URL is invalid. In this case, the `if response.status_code == 200` check in `get_response()` caused the error because the `status_code` attribute doesn't exist on the `None` object.

To solve this error, I checked if the `response` object is None before accessing its attributes. One way to do this was to change the `if response.status_code == 200` line to `if response is not None and response.status_code == 200`. This ensures that the `response` object is not None before checking its status code.

#### Here's the updated code with error fixed:

```python
import requests

def get_response(url):
    response = requests.get(url)
    if response is not None and response.status_code == 200:
        return response
    else:
        return None

def main():
    url = "https://api.example.com/data"
    response = get_response(url)
    if response is not None:
        print("Response received")
    else:
        print("Error: Failed to retrieve response")

if __name__ == '__main__':
    main()
```

Now, when we run this code, we get the message **"Error: Failed to retrieve response",** which indicates that the request failed. This could be due to an invalid URL or network connectivity issues, among other possible causes.

**And you know what?** **It worked! ⚡👀**

---

* ### Conclusion
    

Wow, that was quite an adventure! Debugging Python can be tough, but it's also really rewarding when you finally figure out what's going on.

I hope you guys enjoyed my story and learned something from it.

> If you get stuck on a coding problem, don't give up!
> 
> Take a break, ask for help, and keep trying. You never know when you might have a breakthrough.

And hey, if you want to follow my coding adventures(especially python) and see some coding memes, be sure to follow me on [Twitter](http://adicode.ml/twitter) and [Instagram!](http://adicode.ml/instagram)

Ending this blog with another gif. Sorry for the spam. I love Pikachu and coding.

%[https://giphy.com/gifs/nintendo-satoru-iwata-VelWewgR6CpNK]