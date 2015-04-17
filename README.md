# yagmail -- Yet Another GMAIL client

The simple goal here is to make it as simple and painless as possible to send an email.

In the end, your code will look something like this:

```python
import yagmail
yag = yagmail.Mail('mygmailusername')
yag.send('to@someone.com', 'subject', 'body')
```

### Install

For Python 2.x and Python 3.x respectively:

```python
pip install yagmail
pip3 install yagmail
```

### Start a connection

```python
yag = yagmail.Mail('mygmailusername')
```

Note that this connection is reusable.

### Usability 

Defining some variables:

```python
to = 'santa@someone.com'
to2 = 'easterbunny@someone.com
to3 = 'sky@pip-package.com'
subject = 'This is obviously the subject'
body = 'This is obviously the body'
html = '<a href="https://pypi.python.org/pypi/yagmail/">Click me!</a>'
```

Note that only `To` is required, the rest of the options are optional (`subject`, `body`, `html`)

```python
yag.send(To = to, Subject = subject, Body = body)
yag.send(To = to, Subject = subject, Body = body, Html = html)
yag.send(To = to, Html = html)
```

Furthermore, if you do not want to be explicit, you can do the following:

```python
yag.send(to, subject, body)
yag.send(to, subject, body, html)
```

And lastly, it is also possible to send to a group of people by providing a list of email strings rather than a single string:

```python
yag.send([to, to2, to3], subject, body)
yag.send([to, to2, to3], subject, body)
```

### Errors

- Make sure you have a keyring entry. This is how you can do it for example (only required once):

```python
import keyring
keyring.set_password('yagmail', 'mygmailusername', 'mypassword')
```

- Make sure you have a connection

- I only suppose it will work for gmail