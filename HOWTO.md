# Libre Core - System Demo
A brief walkthrough of the various components of Libre core

## NOT FOR PRODUCTION ENVIRONMENTS. 
The software contained in this project, and the images pulled by the docker-compose file contained in this repo are pre-release versions and are not intended for production environments. Use of this software is at your own risk.

If you would like to use Libre in a production environment, please get in touch with Libre Technologies to ensure you have the correct stable versions of services for you specific needs.

## Libre Admin
Found at http://localhost

Libre admin is the primary component of Libre core, it is the centrepoint of all user driven activity.

Every time you login you should be greeted with an empty screen

![image](https://user-images.githubusercontent.com/54924665/134123473-e5596b30-4844-493f-850a-39c4b5c5ccab.png)

### Configuring the menu

You can access the menu by clicking the top left hand corner of the screen, and configure it through Security -> Menu Config
![image](https://user-images.githubusercontent.com/54924665/134130952-0ec4c3a9-2236-4d78-803c-c775123f2412.png)

You can add new pages by clicking the + next to Menu Configuration Panel

![image](https://user-images.githubusercontent.com/54924665/134133992-72934de6-6796-4e15-a59a-6077897d6d4d.png)

If you click the checkbox Is Page, the drop down menu Menu Page will appear where you can select the type of page to add

## Grafana
Found at http://localhost:3000

## GraphQL Playground
Found at http://localhost:4000/graphql

## Influx
Found at http://localhost:8086

## EMQX Broker
Found at http://localhost:18083
