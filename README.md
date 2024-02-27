- Directions for sending requests and receiving response from RNG microservice
    - Overview 
        - The microservice is an RNG or random number generator.
        - It is a server that when called upon gives back a random number between 1 and 100


    - A) Sending Request
        - To create a connection with the microservice connect on port=5555 and the host=localhost.
        - Make sure it is a TCP connection
        - Send any binary encodeded message to start the 3 way TCP protocol handshake
        - Example:
            - url = tcp://localhost:5555
            - socket = create_connection(url)
            - msg = "you string message".encode()
            - socket.send_msg(msg)

    - B) Getting Response
         - To get a response back make sure to hold the data back in a variable
         - In addition the message will be binary encoded so you will need to decode it to read the message
         - Afterwards the RNG microservice will close the connection and wait again for the next number
         - Example:
             -   response = socket.receive_response()
             -   data = response.decode()

    - C) UML Sequence Diagram
        - UML sequence diagram via Lucidchart 
            - https://lucid.app/lucidchart/a4e53cd5-6ccf-4751-9f21-5970b87c7604/edit?viewport_loc=-198%2C1260%2C2862%2C1417%2C0_0&invitationId=inv_81160091-a3ab-4dd6-aa8b-a5eb8750a120
          

