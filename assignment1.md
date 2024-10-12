# Assignment 1

By

Stephen Kerr
041165225

<div style="border:1 px solid red;">
<p style="text-align:center;">Text_content</p>
</div>
Introduction

In this assignment, I will choose to use a real-time chat application.


# Section 1

Both REST and GraphQL could be used in a chat application.  (OpenAI, ChatGPT)

Authorization requests can be done with REST.  Configuration files can be handled with GraphQL.  WebSockets will handle live comminication.

OAuth2 could be the authorization tool used for the chat app.  OAhuth2 can be used to allow users to sign in using an account from a different app such as their bank or Facebook or Apple or Google.  Remembering a new username and password for every application can be overwhelming.  Using a known app for signin is a great solution for a customer support app that is not expected to be used on a daily basis.  OAuth2 is generally used with REST, although GraphQL could be used.  We will go with the usual in this case and use REST.

Configuration settings can use a GraphQL implementation.  There are two reasons for this: the first the configuration options can change from version to version as new features are introduced, and the second is that only the changed information needs to be sent and received.  GraphQL presents a single endpoint that can be adapted to a variety of payloads.  

For the live communication aspects of the application WebSockets will be used because we want a communication tunnel that will be fixed for the duration of the chat.

# Section 2

## WebSockets for Real-time Communication

The WebSockets module would be implemented in python using the FastAPI() library. (OpenAI, ChapgGPT).  FastAPI is a framework that implements WebSockets (Fastapi).  

Alternatively, python can use websockets directly using the websockets module.  

Sample code of using websockets in python:

```
import asyncio
import websockets

async def echo(websocket, path):
    async for message in websocket:
        print(f"Received message: {message}")
        await websocket.send(f"Echo: {message}")

# Start the WebSocket server on ws://localhost:8765
start_server = websockets.serve(echo, "localhost", 8765)

# Run the WebSocket server forever
asyncio.get_event_loop().run_until_complete(start_server)
asyncio.get_event_loop().run_forever()
```

## Websockets vs. REST and GraphQL

The key features of WebSockets are: (openAI, ChatGPT)
- Persistent Connection
- Low Latency
- Bidirectional

REST and GraphQL are: (openAI, ChatGPT)
- stateless
- Unidirectional
- Polling for Real-Time Data 

The differences between WebSockets and REST (and GraphQL) are that a new connection needs to be made and authorized with each message using REST, REST is unidirectional, and REST would need to implement polling.  GraphQL does have a subscription feature.  However, it is often implemented using websockets (OpenAI, ChatGPT).

Section 3: Techologoy Recommendation and Justification

The recommended coding language is python.  That is for me.  Pretty much all languages will be able to implement code to acheive the task, but I know and like python.  It has the FastAPI library which can save a lot of time figuring out websockets.  Or it can use the websocket library directly.  Also, there is lots of documentation for python.

Python has many different webservers that can be used.  I saw a lot of examples using uvicorn, which I assume is an upgrade from gunicorn.  These are production quality servers for running python code.  Python has two frameworks that can be used: Flast and Django.  they are both suitable.  Finally, containerizing a python Flask project has a lot of examples online.







References

Fastapi. (n.d.). FASTAPI. FastAPI. https://fastapi.tiangolo.com/ 

OpenAI. (2024). ChatGPT (Oct 13 version) [Large language model]. https://chatgpt.com/

