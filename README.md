# Home-Budget-Manager

**Summary**

Welcome to still-to-be-finished project - Home Budget Manager. HBM allows you to supervise your finances and optimize money flow within your household. This application will allow you to plan your expenses and incomes monthly, and keep track of money flow with every spedning or money income. Money charts will help you keep your finances under control easily.

Check in later for new updates.

**About The Project**

**1. Project Requirements**
Your project must meet all of the requirements below:
- Include a microservices Java/Spring Boot back-end and an Angular frontend.
- Include at least 2 SQL database tables.
- Include at least 4 services plus at least 1 edge service.
- Include at least 1 GET, POST, PUT/PATCH, and DELETE route.
- Include adequate and complete documentation.

**2. Built With**
Technologies used in this project:

- Java

- Spring

- MySQL

- GitHub

- Node.js

- Angular

**Setup**

**1. Backend Application**
Clone the backend repositories:
- gateway-service: https://github.com/jegor-chomczuk/gateway-service
- discovery-service: https://github.com/jegor-chomczuk/discovery-service
- user-service: https://github.com/jegor-chomczuk/hbm-user-service
- expense-service: https://github.com/jegor-chomczuk/hbm-expense-service
- income-service: https://github.com/jegor-chomczuk/hmb-income-service
- planned-expense-service: https://github.com/jegor-chomczuk/hbm-planned-expense-service
- planned-income-service: https://github.com/jegor-chomczuk/hbm-planned-income-service

Run the following command to start the spring application: mvn spring-boot:run, or by using an IDE like IntelliJ IDEA
The edge service will be available at: http://localhost:8000/

**2. Local Database**
Setup the following database name and user, or setup your own database by changing the values in the application.properties file

CREATE USER 'ironhacker'@'localhost' IDENTIFIED BY '1ronhacker';

GRANT ALL PRIVILEGES ON *.* TO 'ironhacker'@'localhost';

FLUSH PRIVILEGES;

CREATE DATABASE HomeBudgetManager;

USE HomeBudgetManager;

Run the following command to start the spring application: mvn spring-boot:run, or by using an IDE like IntelliJ IDEA
The application will be available at: http://localhost:8000/

**3. Frontend Application**
Clone the frontend repository: 
- home-budget-manager-client: https://github.com/jegor-chomczuk/home-budget-manager-client
Install the dependencies: npm install
Run the following command to start the frontend application: npm start
The application will be available at: http://localhost:4200/

**Backend API**

All routes are using gateway-service port - http://localhost:8000. There are following routs:
1. userController:
- [GET] http://localhost:8000/user/all - get all user,
- [GET] http://localhost:8000/user/id/{id} - get user by id,
- [GET] http://localhost:8000/user/username/{username} - get user by username,
- [GET] http://localhost:8000/user/username/{username}/password/{password} - get user by username and password,
- [DELETE] http://localhost:8000/user/delete/id/{id} - delete user by id.

2. categoryController:
- [GET] http://localhost:8000/category/all - get all categories,
- [GET] http://localhost:8000/category/id/{id} - get category by id, 
- [GET] http://localhost:8000/category/type/{type} - get categories by type,
- [GET] http://localhost:8000/category/type/{type}/user-id/{userId} - get category by type and user id,
- [PUT] http://localhost:8000/category/update/id/{id} - update category,
- [POST] http://localhost:8000/category - add new category,
- [DELETE] http://localhost:8000/category/delete/id/{id} - delete category,
- [DELETE] http://localhost:8000/category/delete/type/{type} - delete categories by type.

3. expenseController:
- [GET] - http://localhost:8000/expense/all - get all expenses,
- [GET] - http://localhost:8000/expense/id/{id} - get expense by id,
- [GET] - http://localhost:8000/expense/user-id/{id}/year/2021 - get expense by id and year,
- [GET] - http://localhost:8000/expense/user-id/{id}/year/2021/?month={monthName} - get expense by userId, year and month,
- [GET] - http://localhost:8000/expense/user-id/{id}/year/2021/?category={categoryName} - get expense by userId, year and category,
- [GET] - http://localhost:8000/expense/user-id/{id}/year/2021/?month={monthName}category={categoryName} - get expense by userId, year, month and category,
- [DELETE] - http://localhost:8000/expense/delete/id/{id} - delete expense by id,
- [DELETE] - http://localhost:8000/expense/delete/user-id/{userId} - delete expense by user id
- [DELETE] - http://localhost:8000/expense/delete/category/{categoryName} - delete expense by category name,
- [POST] - http://localhost:8000/expense/add - add new expense,
- [PUT] - http://localhost:8000/expense/update/id/{id} - update expense by id.

4. plannedExpenseController:
- [GET] - http://localhost:8000/planned-expense/all - get all planned expenses,
- [GET] - http://localhost:8000/planned-expense/id/{id} - get planned expense by id,
- [GET] - http://localhost:8000/planned-expense/user-id/{id}/year/2021 - get planned expense by id and year,
- [GET] - http://localhost:8000/planned-expense/user-id/{id}/year/2021/?month={monthName} - get expense income by userId, year and month,
- [GET] - http://localhost:8000/planned-expense/user-id/{id}/year/2021/?category={categoryName} - get planned expense by userId, year and category,
- [GET] - http://localhost:8000/planned-expense/user-id/{id}/year/2021/?month={monthName}category={categoryName} - get planned expense by userId, year, month and category,
- [DELETE] - http://localhost:8000/planned-expense/delete/id/{id} - delete planned expense by id,
- [DELETE] - http://localhost:8000/planned-expense/delete/user-id/{userId} - delete planned expense by user id
- [DELETE] - http://localhost:8000/planned-expense/delete/category/{categoryName} - delete planned expense by category name,
- [POST] - http://localhost:8000/planned-expense/add - add new planned expense,
- [PUT] - http://localhost:8000/planned-expense/update/id/{id} - update planned expense by id.

5. incomeController:
- [GET] - http://localhost:8000/income/all - get all incomes,
- [GET] - http://localhost:8000/income/id/{id} - get income by id,
- [GET] - http://localhost:8000/income/user-id/{id}/year/2021 - get income by id and year,
- [GET] - http://localhost:8000/income/user-id/{id}/year/2021/?month={monthName} - get income by userId, year and month,
- [GET] - http://localhost:8000/income/user-id/{id}/year/2021/?category={categoryName} - get income by userId, year and category,
- [GET] - http://localhost:8000/income/user-id/{id}/year/2021/?month={monthName}category={categoryName} - get income by userId, year, month and category,
- [DELETE] - http://localhost:8000/income/delete/id/{id} - delete income by id,
- [DELETE] - http://localhost:8000/income/delete/user-id/{userId} - delete income by user id
- [DELETE] - http://localhost:8000/income/delete/category/{categoryName} - delete income by category name,
- [POST] - http://localhost:8000/income/add - add new income,
- [PUT] - http://localhost:8000/income/update/id/{id} - update income by id.

6. plannedIncomeController:
- [GET] - http://localhost:8000/planned-income/all - get all planned incomes,
- [GET] - http://localhost:8000/planned-income/id/{id} - get planned income by id,
- [GET] - http://localhost:8000/planned-income/user-id/{id}/year/2021 - get planned income by id and year,
- [GET] - http://localhost:8000/planned-income/user-id/{id}/year/2021/?month={monthName} - get planned income by userId, year and month,
- [GET] - http://localhost:8000/planned-income/user-id/{id}/year/2021/?category={categoryName} - get planned income by userId, year and category,
- [GET] - http://localhost:8000/planned-income/user-id/{id}/year/2021/?month={monthName}category={categoryName} - get planned income by userId, year, month and category,
- [DELETE] - http://localhost:8000/planned-income/delete/id/{id} - delete planned income by id,
- [DELETE] - http://localhost:8000/planned-income/delete/user-id/{userId} - delete planned income by user id
- [DELETE] - http://localhost:8000/planned-income/delete/category/{categoryName} - delete planned income by category name,
- [POST] - http://localhost:8000/planned-income/add - add new planned income,
- [PUT] - http://localhost:8000/planned-income/update/id/{id} - update planned income by id.


**Frontend Application**

The frontend application allows a user to register and to log into the application. Within the app, user can see his monthly overview of his finances and modify them.Frontend application can be devided into:

- **Home page**: welcome message and links to Login and Register processes are presented;

- **Register page**: user can regoster himself;

- **Login page**: registered user can login into the application;

- **Annual summory**: user can see his annual summory of home finances;

- **Monthly summory** (per each month): user can see overall summory of planned and real expenses, also he/she can plan and mark acctual incomes for particular month and check the overall progress;

- **Settings**: user can make global change regarding expense and income categories, which are available for him/her. 
