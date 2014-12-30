# Nodejs
### Modules:

# Frameworks
### StrongLoop [Connect to Backend] (StrongLoop.md)
## ExpressJS
* [Route](Route.md)
* Third-party Node modules: 
  * [Connect to Backend] (StrongLoop.md) 
* [Template Engine](Consolidate.md): need more research on each template engine to understand pro and corn
* Allow define new template engin http://expressjs.com/advanced/developing-template-engines.html
* Serve static files from several directories
 * With the following middleware setup, and a request for GET /javascripts/jquery.js, the first check would be ./public/javascripts/jquery.js; if it does not exist, then the subsequent middleware will check ./files/javascripts/jquery.js.
```
app.use(express.static('public'));
app.use(express.static('files'));
 ```
 * Prefix a pathname for serving static files
```
app.use('/public', express.static('public'));
```
* Handle 404s
```
app.use(function(req, res, next){
  res.send(404, 'Sorry cant find that!');
});
```
* Render plain HTML
 * If you have a specific file, use res.sendFile(). If you are serving many assets from a directory use the express.static() middleware.
* 
