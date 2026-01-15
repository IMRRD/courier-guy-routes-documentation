# Swagger route

*`http://192.168.110.164:8823/swagger/index.html`*

- You need to be logged inside of session-server to be able to test.
- Always remember to read the ENTIRE file because all of the informations are important

# Courier Guy Portal Access

- **URL:** https://sandbox.shiplogic.com/login  
- **Login:** almadavic@live.com  
- **Password:** Will be sent via WhatsApp  

This portal allows us to manage **shipments and much more** within Courier Guy.  
It is useful for **testing OUR API via Swagger** and **validating the results directly on the website**, making it a valuable environment for integration tests.


Postman Collection:

- You need to have the postman installed on session-server.
- Download that json file and import on postman on session-server:

## 📥 Download configuration file

👉 [Click here to download the JSON file](https://github.com/IMRRD/courier-guy-routes-documentation/blob/main/CourierGuy.postman_collection.json)


- I have to attach the portal credentials here
- Add swagger doc on all of the endpoints


## Useful Info

Example of trackingReference to use on project: FV4XVM

To obtain the trackingReference, the value is initially provided when registering a shipment.
After that, access the portal, open the shipment details, and locate the Tracking Ref. field.
Use only the value that appears before the “/” character.