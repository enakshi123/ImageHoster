# ImageHoster

# This is an Image Hoster project dealing with various functionalities as different endpoints where users can signup to upload the image to the database by proper authentication check passes. The admin user can fetch the image details from the database and can make the necessary changes if needed.
In this project, we learnt how to build Rest APIs and see the results in the swagger and pgAdmin. The database is accessed using Postgres servers at default port no 5432.

(I) Here are the API Endpoints we worked upon in this.

1. Signup-controller: In this controller, the user will able to sign up for an account.

2. Authentication-controller: After signing up, the user needs to sign in. This controller authenticates the user based on the credentials provided. After authentication, the user will be given an ‘access token’, which will be required to perform any further operation.

3. Image-upload-controller: Using the ‘access token’, the user can upload an image through this controller. But the image is not ‘ACTIVE’ until reviewed by the admin.

4. Admin-controller: The admin needs to review all the images uploaded by users. This controller provides the admin with the details about all the images. Once the admin has reviewed the image, he can update it (if needed) and make it ‘ACTIVE’ through this controller.

(II) These are the commands we used to create a schema in our database
1. ‘mvn clean install -DskipTests’ command to build the project.
2. ‘mvn clean install -Psetup’ command, to create the schema and tables in the database

(III) Functionalities:

step 1: New users will signup by providing all the necessary details through the signup endpoint. Then a base 64 header will be generated using an online encoder with the help of the email id and password of the signed up user.

step 2: This header generated after step1 will be provided in the authorization field in the authentication endpoint and this will generate an access token for further use of other functionalities.

step 3: Now to upload an image user will have to put in the image details as needed and the access token generated at the previous step that as the authentication one. This step will generate an image id as the response body which will be used by admin to fetch the image details from the database.

step 4: The by default role of each user who’s signing in is set to nonadmin. For the person to have access to functionalities like getting and updating the image he/she is required to set role is to admin through the query tool in pgAdmin.
Now the functionalities of Admin Controller Endpoint are to get and update image details and to mark the image status as active if needed. This could be done easily by providing the image id as generated in step 3 and by providing the access token as generated in step 2.

(IV) We worked on the project collaboratively through Github and by dividing the endpoints among our team. Each members’ responsibilities are as mentioned below

Riya Gupta(1710991671) @riya242k 
Worked on the user signup and user authentication endpoints.

Enakshi(1710991925) @enakshi123 
Worked on the image upload with use of access token endpoint

Riya Goyal(1710991669) @Riyagoyal02 
Worked on the Admin-Controller API endpoint.
