# CS-465
Full Stack Development
## Architecture

### Compare and contrast the types of frontend development you used in your full stack project, including Express HTML, JavaScript, and the single-page application (SPA).

The Express HTML and Javascript I used for this full stack project were needed to create the customer-facing static HTML Travlr website, while Angular was used to create the admin SPA used to edit trip details. The static Express HTML website requires a full reload in order to see any changes made, whereas the Angular SPA updates automatically if anything is changed. This often made the SPA more pleasant to work with, however the SPA also relies on the Express website for the API used to access trip data. Despite being static, the Express HTML and JavaScript had dynamic elements in the form of handlebars that were used to fill in parts of the Travel page automatically.

### Why did the backend use a NoSQL MongoDB database?
The backend used a NoSQL MongoDB database as doing so allows the website to be scalable and it works well with the Express HTML and SPA frontends. Rather than needing to hardcode every trip detail, the data in the MongoDB database can simply be referenced. This makes the application far more maintainable, as editing or adding trips only requires changing the information in the database as opposed to editing code. To ease this process further, add and edit functions that change the database by sending POST and PUT statements to the database were added to the SPA. This is far more user-friendly as it allows admins to change trips without touching the database directly.

## Functionality

### How is JSON different from JavaScript and how does JSON tie together the frontend and backend development pieces?
JSON is a data format as opposed to a programming language. On the other hand, JavaScript is a programming language that uses JSON as its data format, with JSON literally standing for Java Script Object Notation. JSON ties together the frontend and backend development pieces as both use JSON to perform their functions and transmit data back and forth. One example of this was the trips.json file that was used during development to define trips for the Express HTML application without the use of a database. Along with this, many config files in both the Express HTML and Angular application are written using JSON.

### Provide instances in the full stack process when you refactored code to improve functionality and efficiencies, and name the benefits that come from reusable user interface (UI) components.
One example of code refactoring to improve functionality and efficiency that came early on in the project was making use of handlebars in the Express HTML application. Prior to using handlebars, a significant amount of duplicated code was used to display the trips on the Travel page. By using handlebars, this code was able to simplified greatly, with each trip's details being pulled from data and filled in systematically. This makes the code more readable and more maintainable. Adding or editing trips details no longer involves editing the travel.hbs file, and also avoids risking bugs caused by improperly copied code or changes not being carried over to all instances of copied code.

Another example of code refactoring to improve functionality and efficiency came from adding the TripCard component when working on the SPA. Prior to doing so, the trip listing in the SPA application was only designed to be displayed as cards. After adding the TripCard component and doing some code refactoring, the program can now easily support other ways of displaying the trip listings should they be added in the future. This also makes the TripCard component reusable, making the code easier to work with and being well-aligned with Separation of Concerns principles.

## Testing

### Methods for request and retrieval necessitate various types of API testing of endpoints, in addition to the difficulties of testing with added layers of security. Explain your understanding of methods, endpoints, and security in a full stack application.
In a full stack application like this one, methods are functions like GET, POST, PUT, and DELETE used to interact with endpoints to obtain or manipulate data and change what is displayed to the user. Security is used to guard the application against malicious actors exploiting weaknesses at the connections between endpoints. In its current state, the admin SPA lacks many of the security features one would hope to see in a publicly released application and is only really protected by an authentication system that requires a Java Web Token obtained from a valid login before trips can be added or edited.

Testing methods was often first done using Postman to see if the requests were properly being sent and received. To further confirm a method used to manipulate the data in the MongoDB database like a POST or PUT command was successful, MongoDB Compass could be used to view the database directly and observe any changes. When on the SPA in a web browser, opening the developer tools panel was also a great way to debug and confirm that everything was working correctly and no errors were being output to console. Lastly, testing involves attempting to actually use the application and confirming that it is working as intended, as it could be that a feature is not properly implemented despite no errors being output.

## Reflection

### How has this course helped you in reaching your professional goals? What skills have you learned, developed, or mastered in this course to help you become a more marketable candidate in your career field?
This course has helped me in reaching my professional goals as it has given me the opportunity to go through the complete full stack development of a web application. This experience will be important when working on my own websites or working on websites for employers. On top of this, it showed me how to have a static HTML client-side frontend and an admin-facing SPA that are connected, with both referencing the data in one MongoDB database. In the very least, the concept and methodology I learned will be useful even if the exact structure or programs used in future projects differ.
