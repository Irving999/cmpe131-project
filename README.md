## Setup Instructions

### Prerequisites
- Python 3.6 or higher
- pip 
- Git 

### 1. Clone the Repository to local machine
- git clone https://github.com/Irving999/hw3.git
- cd cmpe131-project
  
### 2. Create a Virtual Environment
python3 -m venv .venv

### 3. Activate the Virtual Environment
source .venv/bin/activate

### 4. Install Dependencies
pip install -r requirements.txt

### 5. Set Up DataBase and filter tags
- flask shell
- from app import db
- db.create_all()
- from app.models import Tag
tags = ['vegan', 'dessert', 'gluten-free', 'breakfast', 'dinner', 'lunch', 'low-carb', 'Italian', 'quick', 'healthy'] # use any tags
for tag_name in tags:
    if not Tag.query.filter_by(name=tag_name).first():
        tag = Tag(name=tag_name)
        db.session.add(tag)
db.session.commit()
  

### 6. Run the application 
- python3 run.py
- visit http://127.0.0.1:5000
