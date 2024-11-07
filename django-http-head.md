# Django and HTTP HEAD requests

I've been making extensive use of the ```require_get``` decorator in Django. This decorator is used to ensure that a view only responds to GET requests. It's a simple way to ensure that a view doesn't respond to POST requests, which can be a security risk.

However, I've been using the ```require_get``` decorator in a way that's not ideal. I've been using it to ensure that a view only responds to GET requests, but I've been using it in views that should also respond to HEAD requests.

The ```require_get``` decorator is a simple decorator that checks the request method and returns a 405 Method Not Allowed response if the request method is not GET. This means that if a view is decorated with ```require_get```, it will not respond to HEAD requests.

To fix this, I shall use the ```require_safe``` decorator instead of ```require_get```. The ```require_safe``` decorator is a more general decorator that checks if the request method is safe (i.e., GET or HEAD) and returns a 405 Method Not Allowed response if the request method is not safe.

Here's an example of how to use the ```require_safe``` decorator:

```python
from django.views.decorators.http import require_safe

@require_safe
def my_view(request):
    # Your view logic here
```

With this change, my views will now respond to HEAD requests as well as GET requests. This is important because HEAD requests are used by search engines and other web crawlers to gather information about a page without downloading the entire page content. By responding to HEAD requests, my views will be more search engine-friendly and accessible to web crawlers.

## References

* [Django documentation - require_safe decorator](https://docs.djangoproject.com/en/stable/topics/http/decorators/#django.views.decorators.http.require_safe)
