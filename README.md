# **HRMS Cucumber Framework**

This repository contains a Selenium-based Cucumber framework for testing HRMS (Human Resource Management System) applications. The framework follows Behavior-Driven Development (BDD) principles and is written in Java. It provides a structure for writing readable, maintainable, and automated tests.

## **Project Structure**

The project is organized as follows:

- `src/test/resources/`: Contains the feature files, written in Gherkin syntax.
- `src/test/java/`: Contains the step definition files, page objects, and test runners.
  - `steps/`: Step definition files that map the steps in feature files to the corresponding test actions.
  - `pages/`: Page Object Model classes that encapsulate the web elements and actions for specific pages.
  - `runners/`: The test runner class for executing the Cucumber features.
- `target/`: Output directory where test reports are generated.

## **Installation**

To get started with this framework, follow these steps:

### **1. Clone the Repository**

mvn clean install
git clone https://github.com/Selbinyyaz/Hrms_Cucumber_Framework.git
cd Hrms_Cucumber_Framework

### **2. Set Up the Project**
Make sure you have Java installed and your IDE is set up (e.g., IntelliJ IDEA or Eclipse). Then, you can build the project using Maven.

If you haven't installed Maven, you can get it from here.
Run the following command to install the dependencies:

```sh
mvn clean install
```

### **3. WebDriver Setup**
Ensure that you have the ChromeDriver or other WebDriver binaries installed and set in your system PATH or specify the path in the config.properties file.

### **4. Running Tests**
You can run the tests using Maven with the following command:
```sh
mvn test
```
This will execute all Cucumber feature files and display the results in the console. The generated test reports will be located in the target/cucumber-reports/ directory.

Alternatively, you can run a specific feature or scenario using:

```sh
mvn -Dcucumber.options="--tags @Login" test
```
## **Writing Tests**
### **1. Feature Files**
The feature files are written in Gherkin syntax and are located in the src/test/resources directory. Here's an example of a simple login feature:

```sh
Feature: User Login

  Scenario: Valid user logs in successfully
    Given I open the login page
    When I enter valid username and password
    Then I should be redirected to the dashboard
```
## **2. Step Definitions**
Step definition files map the steps in the feature files to the actual Selenium WebDriver actions. These are written in the steps/ package in Java. Here’s an example of a step definition for opening a page:

```sh
@Given("^I open the login page$")
public void iOpenTheLoginPage() {
    driver.get("http://example.com/login");
}
```
## **3. Page Object Model**
The page objects are located in the pages/ package. A page object encapsulates the interactions with the web elements on a page, making the code more maintainable. For example:

```sh
public class LoginPage {
    WebDriver driver;
    
    @FindBy(id = "username")
    WebElement usernameField;
    
    @FindBy(id = "password")
    WebElement passwordField;
    
    @FindBy(id = "loginButton")
    WebElement loginButton;
    
    public LoginPage(WebDriver driver) {
        this.driver = driver;
        PageFactory.initElements(driver, this);
    }

    public void login(String username, String password) {
        usernameField.sendKeys(username);
        passwordField.sendKeys(password);
        loginButton.click();
    }
}
```
## **4. Test Runner**
The test runner class is used to execute the Cucumber tests. It is typically located in the runners/ package. Here’s an example:
```sh
@RunWith(Cucumber.class)
@CucumberOptions(
  features = "src/test/resources/features",
  glue = "steps",
  plugin = {"pretty", "html:target/cucumber-reports"}
)
public class TestRunner {
}
```
## **Reporting**
After running the tests, Cucumber generates detailed HTML and JSON reports that provide insights into the test execution. The reports are generated in the target/cucumber-reports/ directory.

## **Contributing**
Feel free to fork the repository and submit pull requests for improvements. If you find any issues or bugs, please open an issue on GitHub.

## **Code Guidelines**
Follow Java naming conventions for classes and methods.
Ensure your feature files are clear, concise, and follow Gherkin syntax.
Write clean, reusable, and maintainable step definitions.
