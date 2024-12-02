# API Testing with TestNG and RestAssured

---

## Overview

This project demonstrates API testing using **TestNG** and **RestAssured**. It focuses on:
- Implementing temporary solutions (stopgap measures).
- Addressing technical debt.
- Laying a foundation for future enhancements.

---

## Setup and Dependencies

### Prerequisites

To run this project, you need:
- Java JDK (8 or higher).
- Maven (Build tool).
- Eclipse IDE or any Java IDE.

### Dependencies

The following dependencies are required and included in the `pom.xml` file:

```xml
<dependencies>
    <dependency>
        <groupId>org.testng</groupId>
        <artifactId>testng</artifactId>
        <version>7.4.0</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>io.rest-assured</groupId>
        <artifactId>rest-assured</artifactId>
        <version>4.4.0</version>
    </dependency>
</dependencies>

Running the Tests
Using the IDE
Open the project in your IDE (e.g., Eclipse or IntelliJ IDEA).
Ensure all Maven dependencies are downloaded.
Locate the testng.xml file in the root directory.
Right-click the testng.xml file and select Run As > TestNG Suite.
Using the Command Line
Open a terminal and navigate to the project directory.

Run the following command:

bash
Copy code
mvn test
Temporary Solutions
Description
The tests include basic validation, such as checking the HTTP status code for API responses.
This approach allows rapid feedback but is not robust for production systems.
Limitations
Only the status code is verified for GET and POST requests.
Minimal response body validation.
Error handling is not implemented for different scenarios.
Example
The following code snippet represents a temporary solution for validating the status code:

java
Copy code
@Test
public void testGetRequest() {
    Response response = RestAssured.get("https://jsonplaceholder.typicode.com/posts/1");
    Assert.assertEquals(response.getStatusCode(), 200);
    // Temporary validation: Verifies only the status code.
}
Technical Debt
Known Issues
GET Request Test:

Only validates the status code.
Does not validate the response structure or content.
Lacks data-driven testing for multiple endpoints.
POST Request Test:

Minimal validation for the response.
Lacks detailed error handling for API failures.
Planned Improvements
Add detailed assertions to validate the response body (e.g., fields and values).
Implement data-driven testing with TestNG’s @DataProvider.
Integrate robust error handling for different scenarios.
Create reusable methods for API requests to avoid redundancy.
Implement logging and reporting tools for better visibility.
Repository
This project is hosted on GitHub. You can view and clone the repository using the link below:

GitHub Repository
(Replace with the actual GitHub repository URL.)

Contact
For questions or suggestions, feel free to contact me at:

Email: dpatel82551@conestogac.on.ca
GitHub: https://github.com/Dipali8982551/Modern_Automation_Assignment4/tree/main/assignment4