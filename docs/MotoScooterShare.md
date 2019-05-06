#### Moto Scooter Share High Level Model

* System description (*required*): Detailed information on the scooter bike system
	* Name (*required*): 
	* Operational Area (*required*):
	* System type (*required*):
		* `dock` - All scooters must be taken from and returned to a dock.
        * `dockless` - All scooters are only dockless.
        * `dockless_with_hub` - Scooters may be dockless, or taken from or returned to a hub.
	* If the system is `station-based`:
    	* Station/pod geographical position (*required*)
	    * Number of scooters per hub (*nice to have*)
    	* Available scooters per hub (*nice to have*)
	* If the system allows free floating scooters:
    	* Scooter position (*required*)
	    * Allowed area for dropping on/off (*required*): This could be different from "System Operational Area"
* Pricing schema (*nice to have*): Information about pricing.
* Battery level (*nice to have*) 