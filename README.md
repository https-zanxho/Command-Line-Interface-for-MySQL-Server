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

### Install dependencies
pip install -r requirements.txt
# If you don't have requirements.txt:
pip install typer mysql-connector-python