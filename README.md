# myRetail
MyRetail is a REST style API that provides product informaton including pricing details. The API uses a third-party API (Target) to fetch the product details. The pricing details are retrieved from MongoDB that stores the price information.

#Pre-requisites
Java-1.8
All the setup commands given below assume linux environment.

#Setup
##MongoDB -
The project uses MongoDB to store the pricing details.
Install MongoDB based on the environment specific documentation given [here](https://www.mongodb.com/download-center)
After succesful installation and start the server, we need to seed the data with some sample pricing.

Steps to seed the data

1. Sample pricing data is available in the pricing-data.json
2. Import the Pricing data
  1. mongoimport --db test --collection price --drop --file /home/ec2-user/code/myRetail/price-data.json
3. Verify the import by using mongo console
  1. mongo - Start the mongo console
  2. use test - Switch the database to test
  3. db.price.find() - This command should display all the records in test database

##Webapplication
The web application hosting the REST API is build using spring boot. The final executable jar is uploaded in the repository.
To run the web application, download the jar file and execute the following command
  java -jar myRetail-0.1.0.jar 
 The server by default stars on port 8080.
 
#Accessing the REST API
Product details can be search by accessing this url
http://localhost:8080/product/<product_id>
 
