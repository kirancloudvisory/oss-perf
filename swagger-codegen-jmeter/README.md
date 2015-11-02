This section describes how to generate everything JMeter needs to 
emulate a lot of clients calling a REST API service defined in Swagger, 
beginning with the example at 
<a target="_blank" href="http://petstore.swagger.io/"> http://petstore.swagger.io</a>

The major steps:

 <a href="#UsualJMeter"> 1). Create JMeter resources for the sample API using conventional approaches (Badboy, etc.).</a>
 
 <a href="#SampleSwagger"> 2). Setup swagger-codegen to create code for a Java client program.</a>
 
 <a href="#SwaggerJMeter"> 3). Edit the template to produce basic JMeter code.</a>

 <a href="#JMeterTricks"> 4). Edit the template to do more edits.</a>

<hr />

<a id="UsualJMeter">
### 1). Create JMeter resources for the sample API using conventional approaches (Badboy, etc.).</a>

<a id="SampleSwagger"> 
2). Setup swagger-codegen to create code for a Java client program.</a>
 
As described in <a href="swagger-codegen.md">
swagger-codegen</a>,
client code is generated by running Java 7 called from within a node.js 
server created within Docker, 

swagger-codegen references a custom template defined in this repo.

maven is used to build the project run-time.


<a id="SwaggerJMeter"> 
### 3). Edit the template to produce basic JMeter code.</a>


The run-time for JMeter is run like other languages generated:

 ```
 ./bin/android-petstore.sh
 ./bin/java-petstore.sh
 ./bin/objc-petstore.sh
 ./bin/jmeter-petstore.sh
 ```

<a id="JMeterTricks"> 
### 4). Edit the template to do more edits.</a>

1). <a href="#BadResponseCodes">Valid atomic calls with bad response codes</a>.

2). <a href="#HappyPath">Happy paths: Valid atomic calls with valid response codes</a>.

3). <a href="#AtomicRunTypes">Atomic run types</a>.

4). <a href="#InvalidFieldValues">Invalid field values</a>.

5). <a href="#CrossFieldEdits">Cross-field edits</a>.

<a href="#Resources">Videos</a>

<hr />

<a id="BadResponseCodes"></a>
1). Recognize and handle problem HTTP response codes

 0. 400 (not found)
 0. 500 (server issues)
 0. etc.


<a id="CleanHappyPath">
## 2). Clean Happy paths</a>
Valid atomic calls with valid response codes

 2.1). POST new (user registration)

 2.2). GET new (lists)
 
 2.3). PUT change
 
 2.4). DELETE newly created, which keeps database empty.

<a id="AtomicRunTypes">
### 3). Atomic run types (perftest)</a>
3). "run-type" parameter defines repeating processing strategies.

 3.1) Repeat POST new to populate the database and identify how many can register all at once.

 3.2) Repeat GETs to identify cache hits and impact of caching.
 
 3.3) Repeat PUTs 
 
 3.4) Impact of database replication (log shipping).

<a id="InvalidFieldValues">
## 4). Invalid field values</a>
There are different invalid values for each data type.

  * Currency number has negative
  * Phone number has too few numbers
  * Phone number has wrong area code
  * Zip code has text characters (as UK Postal code)
  * Credit card number has invalid checksum

<a id="CrossFieldEdits">
## 5) Cross-field edits</a>
There are different invalid values for each data type.

  * Zip code out of state specified
  * Content-Type header doesn’t match the body

## Resources:
Sources:

https://www.youtube.com/watch?v=UuxKpmIrK4w
API Testing and Debugging @ APIStrat SF

https://www.youtube.com/watch?v=heh4OeB9A-c
How to Design a good API and Why It Matters
(Google TechTalk Jan. 24, 2007 Joshua Bloch)

 "APIs live forever. Bad APIs create an un-ending stream of support calls."
 
 "inter-modular boundaries are APIs".

https://www.youtube.com/watch?v=BtAYZ3pHg4c
Developer Friendly API Designs
Nov 16, 2011 by Ferenc Milhaly 

https://www.youtube.com/watch?v=QlQm786MClE
Secrets of Awesome API Design

https://www.youtube.com/watch?v=mZ8_QgJ5mbs
Beautiful REST & JSON APIs

https://www.youtube.com/watch?v=hdSrT4yjS1g
REST+JSON API Design - Best Practices for Developers
by Stormpath

https://www.youtube.com/watch?v=qCdpTji8nxo
How to create great APIs
(at Facebook Developer Day 2013)