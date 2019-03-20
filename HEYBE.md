# steps to run backend

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

1. `git pull origin master` (pull all the upldated code from remote repository)
2. `git add .` (add your changes)
3. `git add .` (commit your changes)
4. `git push origin master` (push your changes to remote repository)
5. `npm install`  (install necessary packages for project)
6. `npm start` (run frontend server)
