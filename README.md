## Introduction to TDD
- Test Driven Development
- its a way Development would automate their Unit and Integration Testing
- TDD Frameworks for C# ( NUnit, xUnit, MS Test, etc., )
- Dependency isolation will be done with the help Mocking Frameworks like Moq(C#)
- Test First Development approach
- SOLID
  - Single Responsibility Principle (SRP)
  - Open Closed Principle (OCP)
  - Liskov Substitution Principle (LSP)
  - Interface Seggration
  - Dependency Injection or Dependency Inversion of Inversion of Control (IOC)
- The test cases could be understood only by Development or Technical folks
  
# Introduction to BDD
- Behavior Driven Development - C# Framework ( Specflow - native BDD Framework )
- Specflow is Cucumber for C#
- It is an extension of TDD
- Test First Development approach just like TDD
- The scope of BDD
  - You could this to automate
    - Component Test
    - API Test
    - End to End Functionality Test
    - Stress and Load Test
    - Regression and Smoke Test
    - REST/SOAP API test
    - Backend Services
    - Desktop application
    - Web application
    - Web Services
    - Microservices
   
- Uses a special Gherkin langauage, which looks like plain English
- Gherkin
-  supports about 70+ spoken languages
- BDD Test cases can be used as a live document
- 


## Testing REST API using Specflow with RESTSharp
```
var client = new RestClient("https://realtor.p.rapidapi.com/properties/v3/list");

            var request = new RestRequest();

            request.AddHeader("content-type", "application/json");

            request.AddHeader("X-RapidAPI-Key", "SIGN-UP-FOR-KEY");

            request.AddHeader("X-RapidAPI-Host", "realtor.p.rapidapi.com");

            request.AddParameter("application/json", "{\r\n\t\"limit\": 200,\r\n\t\"offset\": 0,\r\n\t\"postal_code\": \"90004\",\r\n\t\"status\": [\"for_sale\", \"ready_to_build\"],\r\n\t\"sort\": {\r\n\t\t\"direction\": \"desc\",\r\n\t\t\"field\": \"list_date\"\r\n\t}\r\n}", ParameterType.RequestBody);

            request.Method = Method.Post;

            var response = client.Execute(request);

            Assert.That(response.StatusCode, Is.EqualTo(HttpStatusCode.OK));
```
