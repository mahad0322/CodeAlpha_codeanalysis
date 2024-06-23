to do code analysis in KALI LINUX
FIRST INSTALL BANDIT
using
pip install bandit
then change the directory to that one in which your python code is located after that
 in the cli write
bandit filename.py
and it will do the analysis and the vulnerabilities 
will be show 
use the code given below

import sqlite3

def get_user(username):
    conn = sqlite3.connect('example.db')
    c = conn.cursor()
    # Vulnerable to SQL injection
    query = f"SELECT * FROM users WHERE username = '{username}'"
    c.execute(query)
    user = c.fetchone()
    conn.close()
    return user

# Example usage
print(get_user("admin' OR '1'='1"))