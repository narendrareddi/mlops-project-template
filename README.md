1. Create ennvironment for project
```bash
conda create -n wineq python=3.7 -y
```
2. Activate ennvironment
```bash
activate env
```
3. Create requirements.txt manually or by using touch command and write libraries that we might use in our project
4. Install requirements.txt
```bash
pip install -r requirements.txt
```
5. create template.py file to create project template and run it using 
```bash
python template.py
```
6. Move your dataset to data_given folder
7. Initialise git
```bash
git init
```
8. Initialise dvc
```bash
dvc init 
```
9. Add dataset to dvc
```bash
dvc add data_given/winequality.csv
git add .
```
10. Commit changes to git repository
```bash
git commit -m "first commit"
```
If any error encountered here as Identify yourself, execute below commands
```bash
git config --global user.name "yourname"
git config --global user.email "mail@domain.com"
```
Note:- String should be enclosed between double quotes not single quotes

11. If any file is updated use below command to commit code changes in git
```bash
git add . && git commit -m "update comment"
```
12. Now Go to web your github account and create a new repository button, you can import project files by executing commands under "push an existing repository from the command line"
```bash
git remote add origin https://github.com/narendrareddi/mlops-project-template.git
git branch -M main
it push -u origin main
```
13. Update params.yaml file
14. Create get_data.py & load_data in src folder and write code for file creation in data\raw folder
15. Update corresponding stage information in dvc.yaml and run below command to see changes
```bash
dvc repro
```
dvc.lock file is created

16. commit changes in git and push code changes to repository 
```bash
git add . && git commit -m "first stage complete"
```
```bash
git push origin main
```
17. Create split_data.py in src folder and write code for file creations in data\processed folder
18. Update corresponding stage information in dvc.yaml and run below command to see changes
```bash
dvc repro
```
dvc.lock file is updated

19. commit changes in git and push code changes to repository 
```bash
git add . && git commit -m "second stage complete"
```
```bash
git push origin main
```
20. Create a directory called report to save parameters and files json inside it
```bash
mkdir report
touch report/paramas.json
touch report/scores.json
```
21. Create train_and_evaluate.py in src folder and write code for model file creation
22. Update corresponding stage information in dvc.yaml and run below command to see changes
```bash
dvc repro
```
dvc.lock file is updated

23. commit changes in git and push code changes to repository 
```bash
git add . && git commit -m "final stage complete"
```
```bash
git push origin main
```
24. Commands to see differences that model predicted for various parameters
```bash
dvc metrics show
dvc metrics diff
dvc params show
dvc params diff
```
25. Add pytest and tox in requirements.txt and install them in current environment with below command
```bash
pip install -r requirements.txt
```
Push the same to git repository
```bash
git add . && git commit -m "final stage complete" && git push origin main
```
