# Django mongodb api documentation

settings:

    # databse connection in settings.py which can be used globally by just importing database.
    uri = 'mongodb://10.4.9.230:80,10.4.9.227:80,10.4.9.228:80,10.4.9.229:80/'
    myclient = pymongo.MongoClient(uri)
    db = myclient["eugenie"]

models:

    from settings import db
    
    def channels(request):
        category  = request.GET.get('category')
        country   = request.GET.get('country')
		# here you can pass collection name inside the list for this database.
		# surface care is the collection name(table name)
        mycol  = db['surface_care']     
		# query to fetch results 
        res= json.loads(dumps(mycol.find({})
        return res

view:

	from .models import channels
	from django.http import JsonResponse

	def channels(request):
		# call channels function from models and get the result 
		res = channels(request)
		return JsonResponse(res, safe=False)

urls:

	from .views import channels
	# assign the url end point for the same view to access the api
	path('api/channels/', channels),
