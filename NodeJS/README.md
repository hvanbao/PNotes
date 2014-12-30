# Nodejs
### Modules:

# Frameworks
### StrongLoop [Connect to Backend] (StrongLoop.md)
## ExpressJS
1. [Route](Route.md)
2. Third-party Node modules: 
  * [Connect to Backend] (StrongLoop.md) 
3. [Template Engine](Consolidate.md): *need more research on each template engine to understand pro and corn*
4. Allow define new template engin http://expressjs.com/advanced/developing-template-engines.html
5. Serve static files from several directories
 * With the following middleware setup, and a request for GET /javascripts/jquery.js, the first check would be ./public/javascripts/jquery.js; if it does not exist, then the subsequent middleware will check ./files/javascripts/jquery.js.
 ```
 app.use(express.static('public'));
 app.use(express.static('files'));
  ```
 6. Prefix a pathname for serving static files
 ```
 app.use('/public', express.static('public'));
 ```
7. [Error handling](http://expressjs.com/guide/error-handling.html)
 * Handle 404s
 ```
 app.use(function(req, res, next){
   res.send(404, 'Sorry cant find that!');
 });
 ```
 * Define error handle: Define error-handling middleware like other middleware, except with four arguments instead of three, specifically with the signature (err, req, res, next)):
  ```
  app.use(function(err, req, res, next){
   console.error(err.stack);
   res.status(500).send('Something broke!');
 });
 
 app.use(logErrors);
 app.use(clientErrorHandler);
 app.use(errorHandler);
 
 function logErrors(err, req, res, next) {
   console.error(err.stack);
   next(err);
 }
 
 function clientErrorHandler(err, req, res, next) {
   if (req.xhr) {
     res.status(500).send({ error: 'Something blew up!' });
   } else {
     next(err);
   }
 }
 
 function errorHandler(err, req, res, next) {
   res.status(500);
   res.render('error', { error: err });
 }
  ```
8. Render plain HTML
 * If you have a specific file, use res.sendFile(). If you are serving many assets from a directory use the express.static() middleware.
9. [Moving (migration) Express 3 to Express 4] (http://expressjs.com/guide/migrating-4.html): *need more research how to implement, what changes in Express 4*
* 
