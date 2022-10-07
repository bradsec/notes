## api security mini course we hack purple notes

Course:  We Hack Purple Api Security Mini Course
Topics: [[api security]] [[hacking apis]] [[api basics]]  [[we hack purple]] [[cybersecurity]]

---
# What is an API?

Reference: https://medium.com/@perrysetgo/what-exactly-is-an-api-69f36968a41f

- An API is not the database or even the server, it is the code that governs the access point(s) for the server.  
- Web based APIs return data in response to a request made by a client
- An API brokers access to a different application to provide functionality or access to data, so data can be included in different applications
- Requests to retrieve or write data are generally done without a frontend, by sending an HTTP request to a server.


Reference: https://community.wehackpurple.com/posts/api-security-mini-course-what-are-apis

- APIs are one of the first things pentesters look for.
- Will attempt to talk to the API when they shouldn't be allowed to.
- API access should be restricted to your API or particular service accounts
- Many APIs are not doing authentication and authorisation
- Many APIs are not doing rate limiting, throttling or making sure they are not being called over and over.

### Testing APIs

- PostMan, BurpSuite
- https://owasp.org/www-project-apicheck/


### Best Practices

- Inventory or your API's (internal and public facing)
- API gateways will do authentication, throttling and quotas
- Logging, monitoring and alerting as you would for any web app 
  - https://newsletter.wehackpurple.com/errors-and-logging
- Block/disable HTTP methods not in use by the API.
  - Common in use GET PUT
- Use a Service Mesh
- Have API Standards
- Strict Linting - Linter is a tool that analyses code for errors and compliance
- Authenticate API's
- Avoid verbose error messages (Don't give away to much error information which could further compromise your API)
- Decommission old and unused versions of the API.


How to test an API with CURL
https://www.youtube.com/watch?v=8f9DfgRGOBo

Walkthru APIs with Postman and the cURL Command
https://www.youtube.com/watch?v=0LFKxiATLNQ
