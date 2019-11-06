class Users(models.Model):
    first_name = models.CharField(max_length=255)
    last_name = models.CharField(max_length=255)
    email_address = models.CharField(max_length=255)
    age = models.IntegerField()
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

Query: Create 3 new users
Users.objects.create(first_name='Michelle', last_name='Tanzil', email_address='xoxo@test.com', age=25)
Users.objects.create(first_name='Mark', last_name='Ramos', email_address='xxx@test.com', age=23)
Users.objects.create(first_name='Kevin', last_name='Song', email_address='ooo@test.com', age=21)

Query: Retrieve all the users
Users.objects.all()

Query: Retrieve the last user
Users.objects.last()

Query: Retrieve the first user
Users.objects.first()

Query: Change the user with id=3 so their last name is Pancakes.
k = Users.objects.get(id=3)
k.last_name = 'pancakes'
k.save()

Query: Delete the user with id=2 from the database
m = Users.objects.get(id=2)
m.delete()

Query: Get all the users, sorted by their first name
Users.objects.all().order_by("first_name")

BONUS Query: Get all the users, sorted by their first name in descending order
Users.objects.all().order_by("-first_name")

