## Automategit

Automategit is a python library to create, delete and clone GitHub repositories through command line. 
Seperate py files for specific task (as mentioned below) work under the hood to perform appropriate actions. Note that user authentication must be done as shown below to link the user's GitHub account. 

#### This python library ```automategit``` contains the following features:
- Check the user's login credentials.
- Download/clone repository to create a local copy on your computer.
- Creates a new repository and delete an existing repository.


### Implementation

  To implement all this functionality and for better understanding, there are some ```code snippets``` below which would be very helpful for you to code.
  
  

### Install

   Use the package manager [pip](https://pip.pypa.io/en/stable/) to install automategit.

```bash
pip install automategit
```




### Create file: cloneRepo.py 

This python file ```cloneRepo.py``` takes input from user through command line arguments, and the usage of this file is to clone or download public repository.



```python
from automategit import clone_repo
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('--url',help="Enter the url")
parser.add_argument('--path',help="Enter path where you want to download or clone repository.")
args=parser.parse_args()
url = args.url
path = args.path
password = args.password
clone_repo.cloneRepo(url,path)
```




##### Run the following in terminal:

```
> python cloneRepo.py --url https://github.com/xyz/Demo.git --path g://demo
```



### Create file: authenticateuser.py 
This python file ```authenticateuser.py``` takes input from user through command line arguments, and the usage of this file is to authenticate user.


```python
from automategit import checkcredentials
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('--user',help="Enter your username")
parser.add_argument('--password',help="Enter your password")
args = parser.parse_args()
user = args.user
password = args.password
checkcredentials.checkCredentials(user,password)
```



##### Run the following in terminal:
```
> python authenticateuser.py --user abc --password abc
```


### Create file: createRepo.py 
This python file ```createRepo.py``` takes input from user through command line arguments, and the usage of this file is to create a new repository.


```python
from automategit import create_repo
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('--reponame',help="Enter the name of repository you want to create")
args=parser.parse_args()
reponame = args.reponame
create_repo.createRepo(reponame)
```


#### Run the following in terminal:

```
> python createRepo.py --reponame Test
```


### Create file:  deleteRepo.py
This python file ```deleteRepo.py``` takes input from user through command line arguments, and the usage of this file is to delete a repository.


```python
from automategit import delete_Repo
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('--owner',help="Enter your username")
parser.add_argument('--repo',help="Enter the name of repository you want to delete")
args = parser.parse_args()
owner = args.owner
repo = args.repo
delete_repo.deleteRepo(owner,repo)
```


##### Run the following in termianl:

```
> python deleteRepo.py --owner xyz --repo demo
```

### Create file: fetch_clear_create_repo.py
This python file ```fetch_clear_create_repo.py``` takes input from user through command line arguments, and the usage of this file is to delete the existing repository and create a new repository.


```python
from automategit import fetch_clean_create_repo
import argparse

parser = argparse.ArgumentParser()
parser.add_argument('--owner',help="Enter your username")
parser.add_argument('--repo',help="Enter the name of repository you want to delete")
parser.add_argument('--reponame',help="Enter the name of repository you want to create at the place of deleted repository")
args = parser.parse_args()
owner = args.owner
repo = args.repo
reponame = args.reponame
fetch_clean_create_repo.clearCreateRepo(owner,repo,reponame)
```

##### Run the following in terminal:

```
> python fetch_clear_create_repo.py --owner xyz --repo Test --reponame Test1
```
