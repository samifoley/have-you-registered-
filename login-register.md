# have-you-registered-
I have just learned how to use lists with Python 3, so I tried to write a code with almost 60 lines that looks like a simple log-in and sign-up page and you can make multiple account with passwords you want and it will check if the password is match with the username you have entered while logging in. If you see any bugs, tell me plz. Hope you like it ;)
usernames =[]
passwords =[]
question = input("do you want to log in or register? ")
answer =['log in', 'register', 'quit']

while question not in answer:
    print("just answer with 'log in', 'register', 'quit'")
    question = input("do you want to log in or register? ")
    
while question == 'register' :
    username = input("insert a name: ")
    password = input("insert a password: ")
    if username not in usernames :
        usernames.append(username)
        passwords.append(password)
    else:
        while username in usernames :
            username = input("username has been already used. please insert another: ")
            password = input("insert a password: ")
            usernames.append(username)
            passwords.append(password)
    print("registeration successful!")
    print("Now log in.")
    user = input("insert your username: ")
    pas = input("insert your password: ")
    while user not in usernames:
        user = input("insert your username: ")
        pas = input("insert your password: ")
    if user in usernames:
        while pas not in passwords or usernames.index(user) != passwords.index(pas) :
            print ("password not match.")
            pas = input("insert your password again: ")
        if usernames.index(user) == passwords.index(pas):
            print("Log in successful!")
    question=input("do you want to register again or log in to an existing one?")        
                
while question == 'log in' :
    user = input("insert your username: ")
    pas = input("insert your password: ")
    while user not in usernames:
        user = input("insert your username: ")
        pas = input("insert your password: ")
    if user in usernames:
        while pas not in passwords or usernames.index(user) != passwords.index(pas) :
            print ("password not match.")
            pas = input("insert your password again: ")
        if usernames.index(user) == passwords.index(pas):
            print("Log in successful!")
    question=input("do you want to register again or log in to an existing one?")
    
if question == "quit" :
    print("Bye.")
