# Open Protocol

## Endpoints

### Coverage

- system?full=[boolean]
- system/?search=[location]&full=[boolean]
- system/{system_id}?full=[boolean]
- system/{system_id}/calendar/
- system/{system_id}/hours
- station
- station/?search=[location]
- station/{station_id}

### Real-time Availability

- system/alerts
- system/{system_id}/alerts
- station/status
- station/status/?search=[location]
- station/{station_id}/status
- vehicle
- vehicle/?search=[location]
- vehicle/{vehicle_id}

### Users

- user/auth    (varies)
- user/profile (GET) get
- user/profile (PUT) update
- user/profile (PATCH) promotion code or similar
- user/history 

### Memberships / Products

- system/{system_id}/plans
- system/{system_id}/products
- system/{system_id}/products/{product_id}
- system/{system_id}/products?search=[location]

### Booking and Ticketing

- quote (POST) create
- quote (GET)  get
- booking/create (POST)
- booking/update (PUT)
- booking/cancel (DELETE)
- booking/get    (GET)
- booking/receipt
- booking/ticket
- webhook to get booking updates


## Explanation

### Coverage

- system?full=[boolean]
- system/?search=[location]&full=[boolean]
- system/{system_id}?full=[boolean]

A system represents a service provided by a particular TSP in a given region or area.
May return all systems supported by the TSP, or be accessed by ID or searched by location. 

- system/{system_id}/calendar/

Describes the calendar of the system, if applies. Useful for seasonal services, that are closed/open for long periods.
Can be accessed individually (by system id), or returned as part of the system endpoint (full=true).

- system/{system_id}/hours

Describes the system hours of operation, if applies at this level. Useful, for example, for bike sharing services that 
may be opened/closed at specific hours/week days. 
Can be accessed individually (by system id), or returned as part of the system endpoint (full=true).

- station
- station/?search=[location]
- station/{station_id}

A station is a public place where the user can park/pickup vehicles (shared bikes, shared cars, owned cars, etc). 
May return all stations supported by the TSP in a given system, or be accessed by ID or searched by location. 
This often refers to the static information of those stations, which does not change too often.

### Real-time Availability

- system/alerts
- system/{system_id}/alerts

This endpoint is intended to inform users about changes to the system.
Can be accessed globally, individually (by system id), or returned as part of the system endpoint.

- station/status
- station/status/?search=[location]
- station/{station_id}/status

Station status returns information about real-time availability of the given station. For example, available places to 
park (any vehicle), or available vehicles to pickup (for shared cars/bikes).
May return all stations (dumps) supported by the TSP in a given system, or be accessed by ID or searched by location.
For dumps, incremental updates should be used, to reduce the amount of transferred information. 
This information can also be part of the station endpoint.

- vehicle
- vehicle/?search=[location]
- vehicle/{vehicle_id}

This endpoint returns available vehicles for a given system. Useful for free floating services, where vehicles are not
parked at fixed stations.
May return all vehicles (dumps) supported by the TSP in a given system, or be accessed by ID or searched by location.
For dumps, incremental updates should be used, to reduce the amount of transferred information. 

### Users

- user/auth    (varies)

For TSPs supporting user accounts, there will be a set of authentication endpoints depending on the mechanism used.

- user/profile (GET) get
- user/profile (PUT) update
- user/profile (PATCH) promotion code or similar
- user/history 

Endpoints to get user account information, possibly update some values, and apply promotional codes (if applicable). 
Also get booking history.


### Memberships / Products

- system/{system_id}/plans

Describes possible plans/memberships available for users, with their corresponding pricing scheme and supported/included 
products/services.
Can be accessed individually (by system id), or returned as part of the system endpoint (full=true).

- system/{system_id}/products
- system/{system_id}/products/{product_id}
- system/{system_id}/products?search=[location]

Describes the available products for a particular system, with their corresponding pricing scheme and any extra information
required/available. 
Can be accessed individually (by system id), or returned as part of the system endpoint (full=true).

### Booking and Ticketing

- quote (POST) create
- quote (GET)  get

These endpoints are used to create quotes for services that depend on specific from, to locations and
depart times, or get extra or updated information about them. Examples can be taxis, shuttle buses, car rentals. 

- booking/create (POST)

This endpoint is used to create a booking, either on behalf of a user or the MaaS provider.

- booking/cancel (DELETE)

Whenever available, this endpoint will allow to cancel an existing booking. Will depend on the status of the booking and the TSP.

- booking/update (PUT)

Whenever available, this endpoint will allow to update an existing booking. Will depend on the status of the booking and the TSP.

- booking/get    (GET)

Get updated information of a given booking

- booking/receipt

Obtain a receipt of the booking, with pricing information.

- booking/ticket

Obtain a ticket, useful for validation/verification.

- webhook to get booking updates

A webhook to allow the TSP to proactively inform MaaS provider about updates or changes in a booking.


## Private APIs

| Endpoint                                       | Uber             | car2go          | Jayride         | Donkey Republic | Swiftfleet | 
|------------------------------------------------|------------------|-----------------|-----------------|-----------------|------------| 
| system?full=[boolean]                          |                  | yes (+op-areas) | yes (countries) | cities          |            | 
| system/?search=[location]&full=[boolean]       |                  |                 |                 | city_details    |            | 
| system/{system_id}?full=[boolean]              |                  |                 |                 |                 |            | 
| system/{system_id}/calendar/                   |                  |                 |                 |                 |            | 
| system/{system_id}/hours                       |                  |                 |                 |                 |            | 
| system/alerts                                  |                  |                 |                 |                 |            | 
| system/{system_id}/alerts                      |                  |                 |                 |                 |            | 
| system/{system_id}/plans                       |                  |                 |                 |                 |            | 
| system/{system_id}/products                    |                  |                 |                 |                 |            | 
| system/{system_id}/products/{product_id}       | yes              |                 |                 |                 |            | 
| system/{system_id}/products?search=[location]  | yes              |                 |                 |                 |            | 
| station                                        |                  | yes             |                 |                 | yes        | 
| station/?search=[location]                     |                  |                 |                 | hubs            |            | 
| station/{station_id}                           |                  |                 |                 | hubs            | yes        | 
| station/status                                 |                  |                 |                 | yes             |            | 
| station/status/?search=[location]              |                  |                 |                 | yes             |            | 
| station/{station_id}/status                    |                  |                 |                 |                 |            | 
| vehicle                                        |                  | yes             |                 |                 |            | 
| vehicle/?search=[location]                     |                  |                 |                 |                 |            | 
| vehicle/{vehicle_id}                           |                  |                 |                 |                 |            | 
| user/auth    (varies)                          | oauth            | oauth1 (r)      | in booking      |                 | in booking | 
| user/profile (GET) get                         | yes              |                 |                 |                 |            | 
| user/profile (PUT) update                      |                  |                 |                 |                 |            | 
| user/profile (PATCH) promotion code or similar | yes              |                 |                 |                 |            | 
| user/history                                   | yes              |                 |                 |                 |            | 
| quote (POST) create                            | yes (+estimates) |                 | yes             |                 | yes        | 
| quote (GET)  get                               |                  |                 | yes             |                 | yes        | 
| booking/create (POST)                          | yes              | removed         | yes             |                 | yes        | 
| booking/update (PUT)                           | yes              |                 |                 |                 |            | 
| booking/cancel (DELETE)                        | yes              | removed         | yes             |                 | yes        | 
| booking/get    (GET)                           | yes              | removed         | yes             |                 | yes        | 
| booking/receipt                                | yes              |                 |                 |                 |            | 
| booking/ticket                                 |                  |                 |                 |                 |            | 
| webhook to get booking updates                 | yes              |                 |                 |                 |            | 


## Open APIs

| Endpoint                                       | GBFS | MaaS Global     | SUTI             | goConga & SkedGo | 
|------------------------------------------------|------|-----------------|------------------|------------------| 
| system?full=[boolean]                          | x    |                 |                  |                  | 
| system/?search=[location]&full=[boolean]       | x    |                 |                  |                  | 
| system/{system_id}?full=[boolean]              |      |                 |                  |                  | 
| system/{system_id}/calendar/                   | x    |                 |                  |                  | 
| system/{system_id}/hours                       | x    |                 |                  |                  | 
| system/alerts                                  | x    |                 |                  |                  | 
| system/{system_id}/alerts                      | x    |                 |                  |                  | 
| system/{system_id}/plans                       | x    |                 |                  |                  | 
| system/{system_id}/products                    |      |                 |                  |                  | 
| system/{system_id}/products/{product_id}       |      |                 |                  |                  | 
| system/{system_id}/products?search=[location]  |      |                 |                  |                  | 
| station                                        | x    | x               |                  |                  | 
| station/?search=[location]                     | x    | x               |                  |                  | 
| station/{station_id}                           |      |                 |                  |                  | 
| station/status                                 | x    |                 |                  |                  | 
| station/status/?search=[location]              | x    |                 |                  |                  | 
| station/{station_id}/status                    |      |                 |                  |                  | 
| vehicle                                        |      |                 |                  |                  | 
| vehicle/?search=[location]                     |      |                 |                  |                  | 
| vehicle/{vehicle_id}                           |      |                 |                  |                  | 
| user/auth    (varies)                          |      |                 |                  |                  | 
| user/profile (GET) get                         |      |                 |                  |                  | 
| user/profile (PUT) update                      |      |                 |                  |                  | 
| user/profile (PATCH) promotion code or similar |      |                 |                  |                  | 
| user/history                                   |      |                 |                  |                  | 
| quote (POST) create                            |      | route           | x (1501)         | x                | 
| quote (GET)  get                               |      |                 |                  | x                | 
| booking/create (POST)                          |      | booking_create  | x (2000)         | x                | 
| booking/update (PUT)                           |      | booking_update  |                  | x                | 
| booking/cancel (DELETE)                        |      | booking_cancel  | x (2010)         | x                | 
| booking/get    (GET)                           |      | booking_get     | x (5020)         | x                | 
| booking/receipt                                |      | booking_receipt |                  | x                | 
| booking/ticket                                 |      | booking_ticket  |                  |                  | 
| webhook to get booking updates                 |      |                 | "x (3003, 4010)" |                  | 
