# MySQL CLI Tool (Python + Typer + mysql-connector)

A simple interactive **command-line tool** to manage a local MySQL server:
- Create and drop **databases** and **tables**
- **Alter** tables (add columns)
- **Insert** data into tables
- Show a **man page** of allowed commands

> ⚠️ This version runs in a **manual input loop** (type commands like `CREATE DATABASE`, `DROP TABLE`, etc.).  
> Although `typer` is imported and decorators exist, the CLI **does not** expose Typer subcommands yet.

---

## 🚀 Features

- ✅ Test connection to MySQL on startup
- ✅ Create/Drop Database
- ✅ Create/Drop Table
- ✅ Alter Table (add columns of type `VARCHAR(100)` or `INT`)
- ✅ Insert rows interactively with validation on column count
- ✅ Built-in manual page (`--HELP`)
- 🧩 Uses `mysql.connector` with parameterized inserts

---

## 📦 Tech Stack

- Python 3.10+
- [Typer](https://typer.tiangolo.com/) (decorators present, not used to run the app)
- [mysql-connector-python](https://dev.mysql.com/doc/connector-python/en/)

---

## ⚙️ Prerequisites

- **MySQL Server** running on `localhost`
- A MySQL user that can connect locally.  
  The code currently uses:
    host="localhost"
    user="visualstudio"
    password="user1"

> You can change these in the code or refactor to use environment variables.

---

## 🔧 Installation

```bash
# 1) (Optional) create and activate a virtual env
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate

# 2) Install dependencies
pip install -r requirements.txt
# If you don't have requirements.txt:
pip install typer mysql-connector-python
---
##  ▶️ Run
python3 src/main.py
---

## 🕹️ Supported Commands (Manual Loop)

CREATE DATABASE: 
Creates a database after prompting for its name.

CREATE TABLE
Lists databases
Asks which DB to use
Asks for table name, first column name, and type (int or varchar)
Creates the table with a single column

DROP DATABASE
Lists DBs and prompts which one to drop.

DROP TABLE
Lists DBs and prompts which DB to use
Lists tables and prompts which one to drop

ALTER TABLE
Lists DBs and prompts which DB to use
Lists tables and prompts which one to alter
Prompts a new column name and type (int or varchar) and adds it

INSERT INTO
Lists DBs → choose DB
Lists tables → choose table
Shows table schema (DESCRIBE)
Prompts values as comma-separated list, e.g. john, 42
Validates the number of values equals the number of columns
Inserts using placeholders (%s)
Type conversion is not enforced here; ensure your input matches column types

--HELP
Prints the tool’s manual page.

EXIT
Ends the program.