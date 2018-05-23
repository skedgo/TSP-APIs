# TSP-APIs

Recommended APIs that transport service providers implement, for them to be easily included in the SkedGo platform and [accessible through the TripGo API](https://developer.tripgo.com).

Bike-Sharing:

- Static and real-time data in [GBFS](https://github.com/NABSA/gbfs)

Car-Sharing:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/car-share.swagger.yaml).

Car Parks:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/car-park.swagger.yaml)

Taxi-(like) Services:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/taxi.swagger.yaml).

Public Transport:

- Static data in [GTFS](https://developers.google.com/transit/gtfs/reference/) (preferred), [TransXChange](http://naptan.dft.gov.uk/transxchange/) or [VDV-451/VDV-452](http://gdal.org/drv_vdv.html)
- Real-time data in [GTFS-Realtime](https://developers.google.com/transit/gtfs-realtime/reference/) (preferred) or [SIRI](http://user47094.vs.easily.co.uk/siri/)

If you use non-standard formats, we can still integrate your service onto our platform, but please [get in touch](mailto:api@tripgo.com) for that.


## Registry

Existing implementations are tagged on GitHub with [`tsp-apis`](https://github.com/topics/tsp-apis).

- Car Parks:
  - [Nuremberg, Germany](https://github.com/skedgo/de-nuremberg-api)
  

## Where to see my contribution

* TripGo [Android](https://play.google.com/store/apps/details?id=com.buzzhives.android.tripplanner), [iOS](https://itunes.apple.com/app/tripgo/id533630842), [Web](https://tripgo.com/)
* [Edit this file](https://github.com/skedgo/tripgo.connect/edit/master/README.md) and make a pull request to add your end-user product
