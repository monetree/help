1. connect using `python` using pymongo client:

        import pymongo
        client = pymongo.MongoClient("mongodb://localhost:27017/")
        db = client["mydatabase"]
        col = db["customers"]
        res = mycol.find_one()
        print(res)

 
2. connect using `django` using `djongo` client


        DATABASES = {
            'default': {
                'ENGINE': 'djongo',
                'NAME': 'consumerhub',
                'HOST': 'mongodb://localhost:27017/',  
            }
        }
