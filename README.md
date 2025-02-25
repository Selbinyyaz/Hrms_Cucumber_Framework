# **Hrms Cucumber Framework**

## **Overview**
This project is a **Cucumber-based automation framework** designed for testing the **HRMS (Human Resource Management System)** application. It utilizes **Cucumber with WebDriverIO** for writing and executing **BDD (Behavior Driven Development)** test scenarios.

## **Tech Stack**
- **Cucumber** - **BDD testing framework**
- **WebDriverIO** - **Web automation framework**
- **Node.js** - **JavaScript runtime**
- **TypeScript** - **Strongly-typed JavaScript**
- **Chai** - **Assertion library**
- **Allure Reporter** - **Test reporting**

## **Prerequisites**
Before running the tests, ensure you have the following installed:
- **Node.js** (Latest **LTS** version recommended)
- **npm** or **yarn**
- **Google Chrome** (Latest version recommended)

## **Installation**
Clone the repository and install dependencies:
```sh
git clone https://github.com/Selbinyyaz/Hrms_Cucumber_Framework.git
cd Hrms_Cucumber_Framework
npm install
```

## **Running Tests**
To execute the test suite, use the following command:
```sh
npm run test
```
For running specific feature files:
```sh
npm run test -- --spec ./features/login.feature
```

## **Test Reports**
Test execution results can be viewed using **Allure Reports**:
```sh
npm run allure:generate
npm run allure:open
```

## **Project Structure**
```
Hrms_Cucumber_Framework/
│-- **features/**           # Cucumber feature files
│-- **step-definitions/**   # Step definitions
│-- **pages/**              # Page object models
│-- **reports/**            # Test reports
│-- **wdio.conf.js**        # WebDriverIO configuration
│-- **package.json**        # Dependencies and scripts
```


