#### Car Share High Level Model

* System description (*required*): Detailed information on the car share system
  * Name/Company information (*required*): 
  * Operational Area (*required*):
  * System type (*required*):
    * `twoWayHire` - Cars must be picked up in at a specific location (pods) and returned to the same location
    * `oneWayHire` - Cars can be picked up in specific locations (pods) and returned in another of those locations
    * `freeFloating` - Cars can be picked up and dropped off anywhere in specific coverage areas
* Pods (required for `twoWayHire` and `oneWayHire`)
    * Geographical position (*required*)
    * Number of cars per pod (*nice to have*)
    * Available cars per pod (*nice to have*), either as number or as vehicle descriptions (below)
* Free-floating zones (*nice to have* for `freeFloating`):
    * Coverage polygons
* Vehicle description (*nice to have*)
    * Identification (*required*)
    * Location (*required* for `freeFloating`)
    * Vehicle type (*required*)
    * Details (*required*)
    * Fuel (*nice to have*): How full is the car’s tank / battery currently
    * Pricing (*required*)
    * URL for booking (*nice to have*)
