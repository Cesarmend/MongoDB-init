1) Update your environment by running this command:

        sudo apt update

2) Install MongoDB:   

        sudo apt install mongodb

3) Check status:

        sudo service mongodb start
        sudo service mongodb status

4) Creation of the docker-compose.yml file:

    ![image](https://github.com/user-attachments/assets/3536357c-0fda-45c5-b706-fb32cc7a9562)

5) Enter the following script with MONGO's credentials:

    ![image](https://github.com/user-attachments/assets/40ea8f14-2474-4bb5-8aaa-ccc23ef1d447)

        version: '2.2'

        services:
          mongo:
            image: mongo:4.0.4
            restart: always
            container_name: monguito
            environment:
              MONGODB_USER: "user"
              MONGODB_PASS: "pass"  
            volumes:
              - ./monguitodata:/data/db
              - ./monguitodata/log:/var/log/mongodb/
            ports:
              - "27017:27017"

6) The docker-compose file was expected after creating the new folder monguitodata :

        mkdir monguitodata && cd monguitodata

        sudo docker-compose up -d

7) Pulling mongo from the library

    ![image](https://github.com/user-attachments/assets/5c06fc4f-c682-480a-8fc5-21ab53337ea5)

8) Run:

        sudo docker exec -it monguito bash

    ![image](https://github.com/user-attachments/assets/41550716-b62e-4536-a489-443200981733)

# Ready to use mongoo






