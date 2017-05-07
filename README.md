# WeatherForecast

### Hosting of solution

* The solution is hosted at Microsoft Azure public cloud.
* The server is running via background process.
* I hosted it at Ubuntu Server Virtual Machine.
* URL of site: http://myweatherforecast.southindia.cloudapp.azure.com/
* This solution is accessible at port 80.
* The other open port is 22 for SSH for admin (myself).

### Run tests
* Its very simple to run tests by firing below command.
~~~~
npm test
~~~~
* For testing I have used following
  * Mocha is a test framework running on node.js)
  * Chai is a BDD / TDD assertion library 
  * Nock is an HTTP mocking and expectations library for Node.js.
  * Supertest is a library written to test HTTP calls in node.js.
  

### Run Application
* Below command is running at the Azure Ubuntu Server:
~~~~
sudo npm start
~~~~
  * Internally `npm start` is doing two things. Setting up production environment variable and running the code.
  ~~~~
  NODE_ENV=production node ./bin/www
  ~~~~
  Note: sudo is required because production application is running at port 80 and it needs admin/root privileges.
  
  * By default code sets NODE_ENV variable to `development`. Hence, to run locally change start in package.json as below:
  ~~~~
  node ./bin/www
  ~~~~
  
### Info on application  
* Used Express framework which did scafolding. 
* Using a templating engine called PUG, you can review under Views folder.
* Lodash.js is a utility library for helping in extracting data / mapping data for objects.

### Implement with more time
* I would love to implement 1-click deployment to production server.
* Create a deploy user at the server, give permissions to deploy the code.
* Install PM2 the process manager tool for running process.
