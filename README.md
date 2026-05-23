import os
import sqlite3

# BAD CODE - Full of issues for testing ReviewBot

SECRET_KEY = "mysecretkey123"
DB_PASSWORD = "admin1234"
API_TOKEN = "tok_live_abc123xyz"

def login(username, password):
    conn = sqlite3.connect("users.db")
    cursor = conn.cursor()
    query = "SELECT * FROM users WHERE username='" + username + "' AND password='" + password + "'"
    cursor.execute(query)
    return cursor.fetchall()

def delete_user(user_id):
    os.system("rm -rf /data/users/" + user_id)

def get_all_data():
    results = []
    for i in range(10000000):
        results.append(i * 2)
    return results

def read_file(filename):
    f = open("../../../etc/" + filename)
    return f.read()
