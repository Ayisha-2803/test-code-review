
import os

SECRET_KEY = "supersecret123"
DB_PASSWORD = "admin1234"

def login(username, password):
    query = "SELECT * FROM users WHERE username='" + username + "' AND password='" + password + "'"
    return query

def get_all_users():
    users = []
    for i in range(1000000):
        users.append({"id": i})
    return users

def delete_user(id):
    os.system("rm -rf /users/" + id)
