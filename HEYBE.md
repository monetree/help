### Note: I have shared two ways to run project (both frontend and backend). If you wants to setup from scratch please follow way1 and if you have already all setup and you need updated code you should follow way2. As the codes are already setup on your system better you go for way2 to get updated code as per the changes.



# steps to run backend

## Way 1 (If you wants to setup project in a system from scratch where you never setup beforeor if you wants to setup everything from scratch)

1. `git clone https://monetimes@bitbucket.org/monetimes/backend.git` (to get complete backend project from remote repository)
2. `cd backend` (get inside root directory where codes is)
3. `virtualenv env` (create a fresh environment)
4. `cd env` (to get inside environment of python)
5. `Scripts/activate` (activate the environment)
6. `cd ..` (get back to the root directory)
7. `pip install -r requirements.txt` (install necessary packages for project)
8. `python manage.py migrate` (update the database)
9. `python manage.py runserver` (run backend server)

## Way 2 (If you have already the setup and working project but, you need updated code as per my changes)

1. `cd env` (to get inside environment of python)
2. `Scripts/activate` (activate the environment)
3. `cd ..` (get back to the root directory)
4. `git pull origin master` (pull all the upldated code from remote repository)
5. `git add .` (add your changes)
6. `git add .` (commit your changes)
7. `git push origin master` (push your changes to remote repository)
8. `pip install -r requirements.txt` (install necessary packages for project)
9. `python manage.py migrate` (update the database)
10. `python manage.py runserver` (run backend server)


# steps to run frontend

## Way 1 (If you wants to setup project in a system from scratch where you never setup beforeor if you wants to setup everything from scratch)

1. `git clone https://monetimes@bitbucket.org/monetimes/frontend.git` (to get complete frontend project from remote repository)
2. `cd frontend` (get inside root directory where codes is)
7. `npm install` (install necessary packages for project)
9. `npm start` (run backend server)

## Way 2 (If you have already the setup and working project but, you need updated code as per my changes)


1. `git pull origin master` (pull all the upldated code from remote repository)
2. `git add .` (add your changes)
3. `git add .` (commit your changes)
4. `git push origin master` (push your changes to remote repository)
5. `npm install`  (install necessary packages for project)
6. `npm start` (run frontend server)
