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

![image](https://user-images.githubusercontent.com/54924665/134267117-a2f97532-b74e-4f1f-8dde-c469200908b5.png)

From the menu configuration panel, you can also drag and drop pages or sections around

### Setting up an equipment class

Navigate to Configuration -> Equipment Classes

You should be able to see some preconfigured examples, and you can create a new one by clicking the + 

![image](https://user-images.githubusercontent.com/54924665/134268966-85c331d8-f0d9-4755-80b2-40680b8d13fe.png)

You can configure the various aspects of the equipment class through the top toolbar

![image](https://user-images.githubusercontent.com/54924665/134269843-ceb69289-51a9-4e13-b975-72f581a77dde.png)

In the general tab you can edit the name an description of the class

In the properties tab you can set up properties for the class. Click the + next to the search bar to start writing a new property and press save when you're done

![image](https://user-images.githubusercontent.com/54924665/134270460-b777f581-07ba-4742-8259-0bf59b3b3ec6.png)

In the events tab, you set up triggers for Libre to record various states of the equipment.

![image](https://user-images.githubusercontent.com/54924665/134272075-28ca16f2-0b88-4acb-b1d0-0d5fadc9da27.png)
Breaking down this image we have a few different fields
  1. Event Name - the name of the event being established
  2. Message Class - specifies the type of event. Here we use PerformanceLog as it is a measurement of the run rate of the machine
  3. Trigger Property - the property that causes the data to be written
  4. Trigger expression - the trigger that causes the data to be written.
    * The example provided here means that the edge will be monitoring the Rate property of any connected equipment, and when the Rate > 1, will trigger the expression
  5. Field properties - configures the fields that get written to the database
    * This can be properties and/or user defined fields

In the reasons tab you can add downtime reasons similarly to how you would add properties. Once you add a reason, whenever you add another reason you can assign it as a parent reason as follows
![image](https://user-images.githubusercontent.com/54924665/134272914-645fbfb7-3cbd-4272-b658-8f8886f8fbd7.png)
Here, the reason we are creating would have Lunch as its parent.


## Grafana
Found at http://localhost:3000

## GraphQL Playground
Found at http://localhost:4000/graphql

## Influx
Found at http://localhost:8086

## EMQX Broker
Found at http://localhost:18083
