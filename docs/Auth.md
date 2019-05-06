#### Auth High Level Model

* Level 2 (for registered users on external TSP):
	- OAuth for Users to get a Token (preferred), or
	- Use User/Pass for auth in endpoints

* Level 3 (for external TSP without registered users):
	- API key auth (preferably filtered by IP), or
	- OAuth can also used for this, but will require a single (corporate) account for which all the bookings are made