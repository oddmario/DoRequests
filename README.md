# DoRequests
DoRequests is a simple HTTP requests maker written in pure HTML and JavaScript

### How does it work?
DoRequests depends on HTML forms to submit the requests. JavaScript is used to insert the entered data of the DoRequests GUI into the HTML form, they are inserted as ***hidden*** `input` tags. After that, JavaScript submits the HTML form into a new tab of the browser, and there you can see the response of your request.

### More HTTP request methods
Currently DoRequests have only `GET` and `POST` request methods available. But you surely can add more.

To add more methods, open `DoRequests.html` with your favourite code editor. You will find a `select` tag like this:
```
<select id="__form['method']" required>
						<option value="post">POST</option>
						<option value="get">GET</option>
</select>
```
So, to add more methods, just add them as options in this `select` tag, for example:
```
<option value="put">PUT</option>
```
And our final `select` tag should be like that at the end:
```
<select id="__form['method']" required>
						<option value="post">POST</option>
						<option value="get">GET</option>
            <option value="put">PUT</option>
</select>
```

### Change the request parameters' delimiter
The default request parameters delimiter in DoRequests is `=` - this means that you have to put your request parameters like that:
```
key=value
```
But if you want to change this `=` to another thing (`:` for example), then it is really simple.
1. Open `DoRequests.html` with your favourite code editor.
2. Find line `var PostKey = lines[j].split("=")[0];` and replace it with `var PostKey = lines[j].split(":)[0];`
3. Find line `var PostValue = lines[j].split("=")[1];` and replace it with `var PostValue = lines[j].split(":")[1];`
4. Find `placeholder="key=value"` and replace it with `placeholder="key:value"`

### Can we send custom HTTP headers in the requests made by DoRequests?
Simple answer, is, no. That's because DoRequests is really basic and simple and it send the requests in a HTML form. We can't send custom headers in HTML forms (at least until now.. Who knows? It might come in the future).
