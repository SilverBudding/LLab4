# Create your views here.
from django.shortcuts import render_to_response
from dj.models import Book,Author

    
def search(request):
    errors = []
    if 'q' in request.GET:
        q = request.GET['q']
        if not q:
            errors.append('Enter a search term.')
        elif len(q) > 20:
            errors.append('Please enter at most 20 characters.')
        else:
            author = Author.objects.get(Name=q) 
            books = Book.objects.filter(AuthorID=author)            
            return render_to_response('search_results.html',
                                  {'books': books, 'query': q,'author':author})
    return render_to_response('search_form.html',{'errors': errors }) 
    
def add_author(request):
    if 'Name' in request.GET:
        n = Author(Name = request.GET['Name'],
                   Age = request.GET['Age'],
                   Country = request.GET['Country'])
        n.save()
    return render_to_response('add_author.html')

def add_book(request):
    if 'ISBN' in request.GET:
        n = Book(ISBN = request.GET['ISBN'],
                 Title = request.GET['Title'],
                 AuthorID = Author.objects.filter(Name = request.GET['AuthorName'])[0],
                 Publisher = request.GET['Publisher'],
                 PublishDate = request.GET['PublishDate'],
                 Price = request.GET['Price'])
        n.save() 
    return render_to_response('add_book.html')
    
def Delete(request):
    i = request.path[8:]
    j = Book.objects.get(ISBN=i)
    j.delete()
    k = Book.objects.filter(ISBN=i)
    return render_to_response('delete.html',{'l':k})
    
def show_inf(request):
    i = request.path[7:]
    j = Book.objects.get(ISBN = i)
    return render_to_response('show_inf.html',{'book':j})