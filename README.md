# AB1import sqlite3
from datetime import datetime

# Connect to SQLite database (or create it if it doesn't exist)
conn = sqlite3.connect('jumps.db')
cursor = conn.cursor()

# Create a table to store jump records
cursor.execute('''
CREATE TABLE IF NOT EXISTS jumps (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    jump_time TEXT NOT NULL
)
''')
conn.commit()

# Function to add a new jump record
def add_jump():
    jump_time = datetime.now().strftime('%Y-%m-%d %H:%M:%S')
