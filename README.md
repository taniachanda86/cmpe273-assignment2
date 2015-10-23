# cmpe273-assignment2
Location and trip planner service in Go.
The location service has the following REST endpoints to store and retrieve locations. All the data is persisted into MongoLab.

1) Create New Location - POST /locations

Request:
{
   "name" : "John Smith",
   "address" : "123 Main St",
   "city" : "San Francisco",
   "state" : "CA",
   "zip" : "94113"
}

Response:
HTTP Response Code: 201
{
   "id" : 56292ac819e8994008a9976d,
   "name" : "John Smith",
   "address" : "123 Main St",
   "city" : "San Francisco",
   "state" : "CA",
   "zip" : "94113",
   "coordinate" : { 
      "lat" : 38.4220352,
     "lng" : -222.0841244
   }
}

2) Get a Location - GET /locations/{location_id}

Request:
GET /locations/56292ac819e8994008a9976d

Response:
HTTP Response Code: 200
{
   "id" : 12345,
   "name" : "John Smith",
   "address" : "123 Main St",
   "city" : "San Francisco",
   "state" : "CA",
   "zip" : "94113",
   "coordinate" : { 
      "lat" : 38.4220352,
     "lng" : -222.0841244
   }
}


3) Update a Location - PUT /locations/{location_id}

Request:
PUT /locations/56292ac819e8994008a9976d
{
   "address" : "1600 Amphitheatre Parkway",
   "city" : "Mountain View",
   "state" : "CA",
   "zip" : "94043"
}

Response:
HTTP Response Code: 201
{
   "id" : 12345,
   "name" : "John Smith",
   "address" : "1600 Amphitheatre Parkway",
   "city" : "Mountain View",
   "state" : "CA",
   "zip" : "94043"
   "coordinate" : { 
      "lat" : 37.4220352,
     "lng" : -122.0841244
   }
}

4) Delete a Location - DELETE /locations/{location_id}

Request:
DELETE  /locations/12345

Response:
HTTP Response Code: 200
