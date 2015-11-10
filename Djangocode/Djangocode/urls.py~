from django.conf.urls.defaults import *
from dj import views 
# Uncomment the next two lines to enable the admin:
# from django.contrib import admin
# admin.autodiscover()

urlpatterns = patterns('',
    # Example:
    # (r'^mysite/', include('mysite.foo.urls')),

    # Uncomment the admin/doc line below to enable admin documentation:
    # (r'^admin/doc/', include('django.contrib.admindocs.urls')),

    # Uncomment the next line to enable the admin:
#    (r'^admin/', include(admin.site.urls)),
    (r'^$',views.search),
    (r'^add_author/$',views.add_author),
    (r'^add_book/$',views.add_book),
    (r'^delete/',views.Delete),
    (r'^title/',views.show_inf),
)
