# Employee Management System (Python + MySQL)

A command-line employee management application built using **only Python and MySQL**.
It demonstrates CRUD operations, object-oriented programming, input validation,
parameterized SQL, exception handling, joins/aggregations, and transaction-safe updates.

## Features

- Add, view, search, update, and delete employees
- Prevent duplicate email addresses
- Validate employee data
- View department-wise employee counts and salary totals
- View highest-paid employees
- Store data persistently in MySQL
- Separate database, model, report, and application layers

## Technology

- Python 3.10+
- MySQL 8+
- `mysql-connector-python`

No Flask, Django, web framework, ORM, or frontend is used.

## Project structure

```text
employee_management_system/
├── src/
│   ├── __init__.py
│   ├── config.py
│   ├── database.py
│   ├── employee.py
│   ├── reports.py
│   └── main.py
├── sql/
│   └── schema.sql
├── .gitignore
├── requirements.txt
└── README.md
```

## 1. Create the database

Open MySQL Workbench or the MySQL command line and run the contents of
`sql/schema.sql`.

Or from a terminal:

```bash
mysql -u root -p < sql/schema.sql
```

This creates the `employee_management` database and its `employees` table.

## 2. Configure the connection

Open `src/config.py` and update the MySQL username and password to match your
local MySQL installation.

Do not upload real database passwords to GitHub. For a public repository,
use environment variables or a local configuration file excluded by `.gitignore`.

## 3. Install the dependency

Create and activate a virtual environment if desired:

```bash
python -m venv venv
```

Windows:

```powershell
venv\Scripts\activate
```

macOS/Linux:

```bash
source venv/bin/activate
```

Install:

```bash
pip install -r requirements.txt
```

## 4. Run the application

Run from the project root:

```bash
python -m src.main
```

## Example workflow

1. Choose **Add employee** and enter the employee details.
2. Choose **List employees** to view saved records.
3. Search by employee ID.
4. Update an employee's department or salary.
5. Open reports to see department summaries and top salaries.
6. Delete a record only after confirming the employee ID.

## Database design

`employees` contains:

| Column | Type | Rule |
|---|---|---|
| employee_id | INT | Primary key, auto increment |
| employee_name | VARCHAR(100) | Required |
| email | VARCHAR(150) | Required, unique |
| department | VARCHAR(80) | Required |
| salary | DECIMAL(10,2) | Must be non-negative |
| hire_date | DATE | Defaults to current date |

## Resume description

**Employee Management System | Python, MySQL**

- Built a menu-driven employee management application using Python and MySQL.
- Implemented CRUD operations with parameterized SQL queries.
- Applied OOP principles, input validation, and exception handling.
- Designed relational database constraints to enforce primary-key and unique-email rules.
- Developed SQL reports using `GROUP BY`, aggregate functions, and sorting.

Only list features you can explain and demonstrate in an interview.

## Troubleshooting

- `Access denied`: check `MYSQL_USER` and `MYSQL_PASSWORD` in `src/config.py`.
- `Unknown database`: run `sql/schema.sql`.
- `ModuleNotFoundError: mysql`: activate your virtual environment and run
  `pip install -r requirements.txt`.
- MySQL service unavailable: start your local MySQL server.
