# Sayata Fullstack Home Assignment

Your goal is to implement a client-server application that will be used by insurance brokers to manage and track their
submission records. The application should consist of:

1. A server exposing HTTP based API allowing various operations on the submissions book.
2. A client side web application to be used by the insurance broker to create, update and upload an application file to
   submissions.

For your convenience we have created empty templates for both applications as part of this repository -

1. in the */server* directory you'll find an empty Python [Flask](https://flask.palletsprojects.com/en/2.0.x/)
   application.
2. In the */client* directory you'll find an empty React application, generated by
   the [Create React App](https://reactjs.org/docs/create-a-new-react-app.html) utility.

In addition, we have created
an [Figma Prototype](https://www.figma.com/file/w5FhhOtk0KBRWm6O9Zt5EJ/Full-Stack-Home-Assignment?node-id=0%3A1&t=3faG55rVJQgdsMm8-0) that contains
mockups for the various pages required for the client web application.  
Use the mockups as a guide to better understand the required user experience. Bonus points will be awarded to those who
match the mockups in their solution.
Login credentials to the Figma platform will be sent to you separately.
To view the flow in figma, click on the play button in right top corner.

## How will we run your program

1. Clone your repository
2. Start the server
    1. `cd ./server`
    2. `pip install -r requirements.txt`
    3. start main.py
3. Start the client
    1. `cd ./client`
    2. `npm install`
    3. `npm start`

## Definitions

A ***submission*** is a system record submitted by an insurance broker that represents a company which intends to
purchase insurance. Submission fields should include -

* Submission id - A unique identifier of the submission.
* Company name - The company name. e.g. "Sayata Labs Ltd".
* Physical address - The company's main office address. e.g. "177 Huntington Ave, Boston, MA 02115, USA"
* Annual revenue - The company's revenue last year in US Dollars. e.g. 1000000.
* Status - (Either NEW or UPLOADED): The status of the submission. Default is set to NEW. UPLOADED means, application file was
  uploaded for this submission.
* Application file - nullable BLOB. Defaults to null. After uploading, it should hold the PDF of the application file.

## The client side

The client is a React web application that allows the broker to perform the following operations:

1. List all the submissions in the system.
2. Create a new submission.
3. Update an existing submission.
4. Upload an application file.

For that matter the application should contain the following main pages:

1. [Submissions page](https://www.figma.com/file/w5FhhOtk0KBRWm6O9Zt5EJ/Full-Stack-Home-Assignment?node-id=1%3A1408&t=WihbXBry3g4KJgyf-4)
    1. Lists all the existing submissions and their statuses. Clicking a submission will navigate the user to that update
       submission page.
2. [Create/ Update submission page](https://www.figma.com/file/w5FhhOtk0KBRWm6O9Zt5EJ/Full-Stack-Home-Assignment?node-id=1%3A6546&t=WihbXBry3g4KJgyf-4)
    1. Allows filling the appropriate submission fields to create a new submission or update existsing one.

Once an application file was uploaded to a submission no further changes may be performed on it.

## The server side API

The server is the brain behind this whole operation. It holds all the data and manages it according the system's set of
rules. It exposes an HTTP based API that allows clients to accomplish the functionality described above. Feel free to
design it as you'd like.  
The API does not have to persist data between runs.  
Multiple clients may call the API at the same time. Assume they all share the same submissions book.

## General guidelines

* Write code as if you're shipping it. We're going to review and score it based on architecture, quality, cleanliness
  and coding standards. If you have a time constraint, it would be much smarter to concentrate on good architecture and
  following coding best practices than on a nice UI and animations.
* We expect this solution to be written in React (client side) and Python (server side).
* Bonus points -
    * Got an idea for a cool feature to add? Go for it! We would love to see your creative side.
    * Introduce some security features into the solution -
        * Add a login page before the submissions page where the broker can register/login with an email and password
          and be authenticated.
        * Allow each broker to see and manipulate only his/her own submissions.
    * Implement the UI in a responsive design.
