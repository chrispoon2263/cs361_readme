- Directions for sending requests and receiving response from calculate microservice
    - Overview 
        - You will create a microservice server that will send out two random poylnomial functions for whenever a user clicks the random button on the UI microservice.
        - NOTE MAKE SURE YOU ARE LOGGED ONTO OSU VPN!
        - UI microservice: http://flip1.engr.oregonstate.edu:63861/

    - A) Create Server:
        - You will need to create a server listening on PORT 65398 on the Flip 1 servers
        - IMPORTANT to make sure to build the server on Flip 1 since the UI microservice will only create a connection on FLIP 1 with a port of 65398
        - The UI microservice will be hosted on the flip1 servers
        - Once a user clicks the random button, my microservice will try to make a connection on PORT 65398 and request 2 polynomial functions
        -  Example:
               - app.run(host='localhost', port=65398)
        - If the PORT is taken by another student send me a message, and I will pick another port.

    - B) Create 2 random functions and wrap into a json object:
         - It is recommended to have a data structure or list to hold all your random functions
             - ex: random_list = ["x^2", "x^3", "x + 1", "x + x + x", "x^5"]
         - Randomly get two functions from the list and wrap into json:
             - Example:
                 - input_1 = get_random_function(random_list)
                 - input_2 = get_random)function(random_list)
                 - data = { input_1: "x^2", input_2: "x^3"}
                 - json_data = jsonify(data)
                 - It is important make sure the key in the key/value pair is "input_1" and "input_2" respectively since I will be using those as key's on my end
               
    - C) Send out message
          - Have the server send out the message
              send_response(data, localhost, port)     


    - D) UML Sequence Diagram
        - UML sequence diagram via Lucidchart 
            - https://lucid.app/lucidchart/4f7f271f-dfd9-4e4d-8098-d71a9c222b90/edit?viewport_loc=-73%2C1219%2C3602%2C1786%2C0_0&invitationId=inv_58bf306c-930f-43db-af31-113b6fc7357f
         
    - E) TIPS
        - Use a webframework like flask to create a quick server in less 10 lines of code
            - https://github.com/osu-cs340-ecampus/flask-starter-app
        - Recommend to create a fake route that does not lead to any website but just sits and listens
            - Then create the 2 random functions
            - Then jsonify
            - Then return the json object back 
