apis.md

This article introduces APIs (Application Programming Interfaces)
that enable computers to talk with each other.

In 2016 it's a rare enterprise which does not provide APIs to vendors
and partners, if not to the public.

* https://developer.visa.com/apicatalog
  
  VISA, the payment card processor opened their APIs to external developers
  for the first time in 2016.
  Their https://github.com/visa has no public repos.

* 

  Paypal has gone through several name changes since they made their API available.

* Alternative payment processor.

* Amazon was one the first to provide their data via APIs. 

* Walmart did not have a website until 2009, but they have a full suite.

* IBM provides APIs to their Watson artificial intelligence systems.

* ATT holds annual hackathons in Las Vegas.

* Netflix was one of the first to provide an API, 
  but in 2015 announced that they will no longer be providing it.

ProgrammableWeb.com provides a registry of APIs.


<a name="ProcessingWorkflow">
## Account Workflow Processing</a>
The basic workflow involved with working with APIs are similar among providers:

1. Click "Register" on a website and provide an email with a name.
2. Confirm email.
3. Complete registration details.
4. Request a Certificate Signing Request.
5. Obtain test keys (a .pem file).
6. Insert test keys in your certificate store.
7. Generate public and private test keys.
8. Run tests using test endpoints.

9. Determine scaling.
10. Obtain production keys.
11. Insert production keys in your certificate store.
12. Generate public and private test keys.
13. Run go-live tests.
14. Run in production.


<a name="Resources">
## Resources</a>

* https://www.mulesoft.com/ty/ebook/restbook
* 
