#### Car Share High Level Model

* System description (*required*): Detailed information on the car share system
	* Name/Company information (*required*): 
	* Operational Area (*required*):
	* System type (*required*):
		* `twoWayHire` - Cars must be picked up in a location and returned to the same location.
		* `oneWayHire`-  Cars could be picked up in a location and returned in another location.
* Pods:
    * Geographical position (*required*)
    * Number of cars per pod (*nice to have*)
    * Available cars per pod (*nice to have*)
* Vehicle description (*required*)
    * Identification (*required*)
    * Location (*required*)
    * Vehicle type (*required*)
    * Details (*required*)
    * Fuel (*nice to have*): How full the car’s tank / battery currently is
    * Pricing (*required*)
    * URL for booking (*nice to have*)