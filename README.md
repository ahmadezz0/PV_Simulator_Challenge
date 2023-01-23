# PV-Simulator-Challenge

## Project Description
This project illustrates the pub-sub process by implementing a scenario of home power consumption. It constitute of three major modules name Meter, broker, and PV Simulator. Finally, data, power consumption, are stored in a file. Data directory holds the message body and all its functionalities to go from the meter to the pv_simulator including parsing

### Meter: 
This should produce messages to the broker with random but continuous values from 0 to 9000 Watts. This is to mock a regular home power consumption.

### PV simulator: 
It must listen to the broker for the meter values, generate a simulated PV power value and the last step is to add this value to the meter value and output the result.

### Writing to a file:
We want the result to be saved in a file with at least a timestamp, meter power value, PV power value and the sum of the powers (meter + PV). The period of a day with samples every couple of seconds would be enough.

## How to run
To run this project, you need to have **docker** installed in your machine. A **docker-compose** file starts up all the services. Services includes meter, rabbitmq, and pv-simulator.


### Run Steps
 1. `docker-compose build` (to build the image)
 2. `docker-compose start` (start the broker)
 3. Open two terminals
 4. In First terminal `cd pv_simulator`
 5. Then `cargo run`
 6. In Second terminal `cd meter`
 7. Then `cargo run`
 8. `docker-compose stop` (stop the broker)
 
 ## Output
 ### PV Output
 Please find the pv output file as **pv_simulator/output.csv**
 ### UI
 Please visit http://localhost:15672 to have a look at the broker. with default credentials username:guest and password:guest



### Improvements
- dockerize meter and pv_simulator then add then to docker-compose
- Add unit tests
- remove hard-coded config values and export them to the relevant containers as environment vars or have a config file