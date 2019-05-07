#### Bookings & Authorization Model

* Level 2 (for registered users on external TSP):
	- OAuth for Users to get a Token (preferred), or
	- Use User/Pass for auth in endpoints

* Level 3 (for external TSP without registered users):
	- API key auth (preferably filtered by IP), or
	- OAuth can also used for this, but will require a single (corporate) account for which all the bookings are made

A high level description of required booking endpoints (which will be for both Level 2 and 3):

* quote (POST) create (depends on pricing schemes, will probably not be needed)
* quote (GET) get (depends on pricing schemes, will probably not be needed)
* booking/create (POST)(required)
* booking/update (PUT) (nice to have, if possible by the TSP)
* booking/cancel (DELETE) (required, will probably depend on the status of the booking)
* booking/get (GET) (nice to have)
* booking/receipt (required for Level 3)
* booking/ticket (required for Level 3 or similar validation endpoint)
* webhook to get booking updates (nice to have)