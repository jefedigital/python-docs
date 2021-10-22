# Python - requests

[https://requests.readthedocs.io/en/master/](https://requests.readthedocs.io/en/master/)

Making Requests

Begin by importing the Requests module:

import requests

Now, let’s try to get a webpage. For this example, let’s get GitHub’s public timeline:

r = requests.get('[https://api.github.com/events](https://api.github.com/events)')

Now, we have a Response object called r. We can get all the information we need from this object.

Requests’ simple API means that all forms of HTTP request are as obvious. For example, this is how you make an HTTP POST request:

r = requests.post('[https://httpbin.org/post](https://httpbin.org/post)', data = {'key':'value'})

Nice, right? What about the other HTTP request types: PUT, DELETE, HEAD and OPTIONS? These are all just as simple:

r = requests.put('[https://httpbin.org/put](https://httpbin.org/put)', data = {'key':'value'})

r = requests.delete('[https://httpbin.org/delete](https://httpbin.org/delete)')

r = requests.head('[https://httpbin.org/get](https://httpbin.org/get)')

r = requests.options('[https://httpbin.org/get](https://httpbin.org/get)')

Note: if any of the values being sent in a PUT are a dict, try json instead:

r = requests.put('[https://httpbin.org/put](https://httpbin.org/put)', **json** = {'key':'value'})

Custom Headers: If you’d like to add HTTP headers to a request, simply pass in a dict to the headers parameter.

For example, we didn’t specify our user-agent in the previous example:

url = '[https://api.github.com/some/endpoint](https://api.github.com/some/endpoint)'

headers = {'user-agent': 'my-app/0.0.1'}

r = requests.get(url, headers=headers)

Response Content

r.text

r.encoding

r.content

r.json

In the rare case that you’d like to get the raw socket response from the server, you can access r.raw. If you want to do this, make sure you set stream=True in your initial request. Once you do, you can do this:

r = requests.get('[https://api.github.com/events](https://api.github.com/events)', stream=True)

r.raw

\\

r.raw.read(10)

'\x1f\x8b\x08\x00\x00\x00\x00\x00\x00\x03'

In general, however, you should use a pattern like this to save what is being streamed to a file:

with open(filename, 'wb') as fd:

for chunk in r.iter\_content(chunk\_size=128):

fd.write(chunk)

Using Response.iter\_content will handle a lot of what you would otherwise have to handle when using Response.raw directly. When streaming a download, the above is the preferred and recommended way to retrieve the content. Note that chunk\_size can be freely adjusted to a number that may better fit your use cases.
