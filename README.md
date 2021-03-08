# TSP-APIs

Recommended APIs that transport service providers implement, for them to be easily included in the SkedGo platform and [accessible through the TripGo API](https://developer.tripgo.com).

## TSP connectors

### Bike-Sharing and Scooter-Sharing:

- Static and real-time data in [GBFS](https://github.com/NABSA/gbfs) 
- For GBFS TSP connector, also [provider](shared/#operation/provider) and [coverage](shared/#operation/coverage) endpoints are required.

- [Bike Share High level model](model/BikeShare.md) 
- [Moto Scooter Share High level model](model/MotoScooterShare.md)

### Taxi-(like) Services:

- [View in ReDocs UI](taxi).

### Info:

- [View in ReDocs UI](info).

## Future TSP connectors

These are the current specs, but may change once they are added as TSP connectors

### Car-Sharing:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/car-share.swagger.yaml).
- [Car Share High level model](model/CarShare.md)

### Car Parks:

- [View in Swagger UI](http://petstore.swagger.io/?url=https://raw.githubusercontent.com/skedgo/TSP-APIs/master/car-park.swagger.yaml)

## Other

### Public Transport:

- Static data in [GTFS](https://developers.google.com/transit/gtfs/reference/) (preferred), [TransXChange](http://naptan.dft.gov.uk/transxchange/) or [VDV-451/VDV-452](http://gdal.org/drv_vdv.html)
- Real-time data in [GTFS-Realtime](https://developers.google.com/transit/gtfs-realtime/reference/) (preferred) or [SIRI](http://user47094.vs.easily.co.uk/siri/)


If you use non-standard formats, we can still integrate your service onto our platform, but please [get in touch](mailto:api@tripgo.com) for that.


## Registry

Existing implementations are tagged on GitHub with [`tsp-apis`](https://github.com/topics/tsp-apis).

- Car Parks:
  - [Nuremberg, Germany](https://github.com/skedgo/de-nuremberg-api)
  

## Where to see my contribution

* TripGo [Android](https://play.google.com/store/apps/details?id=com.buzzhives.android.tripplanner), [iOS](https://itunes.apple.com/app/tripgo/id533630842), [Web](https://tripgo.com/)
* Other [apps using the TripGo API](https://skedgo.com/tripgo-api/)
* [Edit this file](https://github.com/skedgo/tripgo.connect/edit/master/README.md) and make a pull request to add your end-user product
