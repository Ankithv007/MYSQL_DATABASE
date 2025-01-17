# Database Schema and Sample Data

This file contains the details for creating a basic database schema with three tables, adding primary and foreign keys, and inserting sample data into them. Additionally, indexes are created for efficient queries.

## Schema Details

### 1. Table: `departments`
- **Description**: Stores department information.
- **Columns**:
  - `department_id`: Primary key, Auto-incremented.
  - `department_name`: Name of the department.
- **Indexes**:
  - `idx_department_name` on `department_name`.

### 2. Table: `employees`
- **Description**: Stores employee details.
- **Columns**:
  - `employee_id`: Primary key, Auto-incremented.
  - `name`: Name of the employee.
  - `department_id`: Foreign key referencing `departments(department_id)`.
- **Indexes**:
  - `idx_name` on `name`.
  - `idx_department_id` on `department_id`.

### 3. Table: `projects`
- **Description**: Stores project details.
- **Columns**:
  - `project_id`: Primary key, Auto-incremented.
  - `project_name`: Name of the project.
  - `employee_id`: Foreign key referencing `employees(employee_id)`.
- **Indexes**:
  - `idx_project_name` on `project_name`.
  - `idx_employee_id` on `employee_id`.

---

## SQL Script

```sql
-- Create Table: departments
CREATE TABLE departments (
    department_id INT AUTO_INCREMENT PRIMARY KEY,
    department_name VARCHAR(100) NOT NULL,
    INDEX idx_department_name (department_name)
);

-- Insert Data: departments
INSERT INTO departments (department_name)
VALUES
    ('HR'),
    ('Finance'),
    ('Engineering'),
    ('Marketing'),
    ('Operations'),
    ('Sales'),
    ('Customer Support'),
    ('IT'),
    ('Legal'),
    ('Research');

-- Create Table: employees
CREATE TABLE employees (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    department_id INT NOT NULL,
    FOREIGN KEY (department_id) REFERENCES departments(department_id),
    INDEX idx_name (name),
    INDEX idx_department_id (department_id)
);

-- Insert Data: employees
INSERT INTO employees (name, department_id)
VALUES
    ('Alice', 1),
    ('Bob', 2),
    ('Charlie', 3),
    ('Diana', 4),
    ('Eve', 5),
    ('Frank', 6),
    ('Grace', 7),
    ('Heidi', 8),
    ('Ivan', 9),
    ('Judy', 10);

-- Create Table: projects
CREATE TABLE projects (
    project_id INT AUTO_INCREMENT PRIMARY KEY,
    project_name VARCHAR(100) NOT NULL,
    employee_id INT NOT NULL,
    FOREIGN KEY (employee_id) REFERENCES employees(employee_id),
    INDEX idx_project_name (project_name),
    INDEX idx_employee_id (employee_id)
);

-- Insert Data: projects
INSERT INTO projects (project_name, employee_id)
VALUES
    ('Project Alpha', 1),
    ('Project Beta', 2),
    ('Project Gamma', 3),
    ('Project Delta', 4),
    ('Project Epsilon', 5),
    ('Project Zeta', 6),
    ('Project Eta', 7),
    ('Project Theta', 8),
    ('Project Iota', 9),
    ('Project Kappa', 10);
