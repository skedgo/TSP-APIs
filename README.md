# TSP-APIs

Recommended APIs that transport service providers implement, for them to be easily included in the SkedGo platform and [accessible through the TripGo API](https://developer.tripgo.com).

Bike-Sharing:

- Static and real-time data in [GBFS](https://github.com/NABSA/gbfs)

Car-Sharing:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/car-share.swagger.yaml).

Taxi-(like) Services:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/taxi.swagger.yaml).

Public Transport:

- Static data in [GTFS](https://developers.google.com/transit/gtfs/reference/) (preferred), [TransXChange](http://naptan.dft.gov.uk/transxchange/) or [VDV-451/VDV-452](http://gdal.org/drv_vdv.html)
- Real-time data in [GTFS-Realtime](https://developers.google.com/transit/gtfs-realtime/reference/) (preferred) or [SIRI](http://user47094.vs.easily.co.uk/siri/)

If you use non-standard formats, we can still integrate your service onto our platform, but please [get in touch](mailto:api@tripgo.com) for that.
