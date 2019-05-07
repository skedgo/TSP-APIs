#### Bike Share High Level Model

* System description (*required*): Detailed information on the bike systems 
	* Name (*required*) 
	* Operational Area (*required*)
	* System type (*required*)
		* `dock` - All bikes must be taken from and returned to a dock.
        * `dockless` - All bikes are only dockless.
        * `dockless_with_hub` - Bikes may be dockless, or taken from or returned to a hub.
	* If the system is `station-based`:
    	* Station/pod geographical position (*required*)
	    * Number of bikes per pod (*nice to have*)
    	* Available bikes per pod (*nice to have*)
	* If the system allows `free floating bikes`:
    	* Bike position (*required*)
	    * `Allowed area` for floating bike (*required*): This could be different from "System Operational Area"
* Pricing schema (`nice to have`): Information about pricing.