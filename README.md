# Pollers
 A simple polls website made with django

## Requirement
 
You need to have [python](https://www.python.org/downloads/) installed 

## Installation 
```
git clone https://github.com/Hichem-Chabou/Pollers.git

cd pollers

pip install pipenv

# install dependencies
pipenv install
```
Then you need to be in the same folder as `manage.py` :
```
cd pollers
```

For the next commands, there is a slight difference between windows and mac/linux

### On Windows
You need to precede each command with `pipenv run`, for example:
```
# Run migration
pipenv run python manage.py migrate
```

### On Mac/Linux
```
# Run migration
python manage.py migrate
```

After running migration you need to create data in the database by using either the interactive shell or the admin dashboard

```
# Using the shell
python manage.py shell

>>>  from polls.models import Question, Choice      # import from models.py
>>>  from django.utils import timezone
>>>  q = Question(question_text="What is your favorite tea?", pub_date=timezone.now())           # Question to ask
>>>  q.save()
>>>  q = Question.objects.get(pk=1)                 # get just the question instead of a list in an array
>>>  q.choice_set.create(choice_text='Peppermint', votes=0)
>>>  q.choice_set.create(choice_text='Sage', votes=0)
>>>  q.choice_set.create(choice_text='Ginger', votes=0)
>>>  q.choice_set.create(choice_text='Moringa', votes=0)  # create choices
```
Using the admin dashboard:

```
# Create admin user
python manage.py createsuperuser
```
You can open the admin dashboard after running the server, here http://127.0.0.1:8000/admin
## Usage

```
# Run server on port 8000
python manage.py runserver

# If the port 8000 is used, you can change to another one like 8071
python manage.py runserver 8071
```