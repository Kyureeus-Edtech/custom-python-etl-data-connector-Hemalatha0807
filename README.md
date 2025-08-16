

# ExploitDB ETL Data Connector

This project extracts data from the ExploitDB CSV feed, transforms it, and loads it into MongoDB.
It is designed for cybersecurity threat intelligence ingestion and analysis.

---

## 1. Clone the Repository

```bash
git clone https://github.com/Kyureeus-Edtech/custom-python-etl-data-connector-Hemalatha0807.git
cd custom-python-etl-data-connector-Hemalatha0807
```

---

## 2. Create and Activate Virtual Environment

**Windows (CMD or PowerShell):**

```bash
python -m venv venv
venv\Scripts\activate
```

**macOS / Linux:**

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Create and Configure `.env` File

The `.env` file stores *private configuration values* that your script uses.
It should be placed in the *root folder* of the project (next to `exploit_db_etl.py`).

**Steps to create it:**

1. Make a new file in the project folder called `.env`
2. Open it with a text editor
3. Add the following *placeholders* and replace them with your own values:

```env
# ExploitDB CSV Feed URL
EXPLOITDB_URL=https://raw.githubusercontent.com/offensive-security/exploitdb/master/files_exploits.csv

# MongoDB Configuration
MONGO_URI=your_mongodb_connection_string_here
DB_NAME=your_database_name_here
COLLECTION_NAME=your_collection_name_here
```

---

## 5. Run the ETL Script

```bash
python exploit_db_etl.py
```

The script will:

* Download the ExploitDB CSV feed
* Parse and structure the data
* Upsert records into your MongoDB collection

---

## 6. Verify Data in MongoDB

If MongoDB is running locally:

```bash
mongo
use your_database_name
db.your_collection_name.find().pretty()
```

---


