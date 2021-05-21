# GTFS-actual

GTFS-actual extends GTFS static specifications maintained by [Google](https://developers.google.com/transit/gtfs/reference) to enable real transit data reporting.

GTFS-actual rely on GTFS static's field definitions, data types and file format.

## agency.txt

Definition is available [here](https://developers.google.com/transit/gtfs/reference?#agencytxt).

## trips_capacities.txt

| Field Name | Type                            | Required               | Description |
| ---------- |:-------------------------------:|:----------------------:| ----------- |
| agency_id  | ID referencing agency.agency_id | Conditionally required | Agency for the specified trip. This field is required when the dataset provides data for trips from more than one agency in agency.txt, otherwise it is optional. |
| trip_id    | ID referencing trips.trip_id    | Required               | Identifies a trip. |
| start_date | Date                            | Required               | Start day for the trip. |
| start_time | Time                            | Required               | Start time for the trip. |
| capacity   | Non-negative Integer            | Required               | Maximum vehicle capacity. |

## trips_tags.txt

| Field Name | Type                            | Required               | Description |
| ---------- |:-------------------------------:|:----------------------:| ----------- |
| agency_id  | ID referencing agency.agency_id | Conditionally required | Agency for the specified trip. This field is required when the dataset provides data for trips from more than one agency in agency.txt, otherwise it is optional. |
| trip_id    | ID referencing trips.trip_id    | Required               | Identifies a trip. |
| start_date | Date                            | Required               | Start day for the trip. |
| start_time | Time                            | Required               | Start time for the trip. |
| tags       | Text                            | Required               | Coma separated list of tags applied to all stops of the given ride. |

## stop_times_validations.txt

| Field Name    | Type                                    | Required               | Description |
| ------------- |:---------------------------------------:|:----------------------:| ----------- |
| agency_id     | ID referencing agency.agency_id         | Conditionally required | Agency for the specified stop. This field is required when the dataset provides data for trips from more than one agency in agency.txt, otherwise it is optional. |
| trip_id       | ID referencing trips.trip_id            | Required               | Identifies a trip. |
| start_date    | Date                                    | Required               | Start day for the trip. |
| start_time    | Time                                    | Required               | Start time for the trip. |
| stop_id       | ID referencing stops.stop_id            | Required               | Identifies a stop. |
| validations   | Non-negative Integer                    | Required               | Number of ticket validations observed for the stop. |


## stop_times_delays.txt

| Field Name    | Type                                    | Required               | Description |
| ------------- |:---------------------------------------:|:----------------------:| ----------- |
| agency_id     | ID referencing agency.agency_id         | Conditionally required | Agency for the specified stop. This field is required when the dataset provides data for trips from more than one agency in agency.txt, otherwise it is optional. |
| trip_id       | ID referencing trips.trip_id            | Required               | Identifies a trip. |
| start_date    | Date                                    | Required               | Start day for the trip. |
| start_time    | Time                                    | Required               | Start time for the trip. |
| stop_id       | ID referencing stops.stop_id            | Required               | Identifies a stop. |
| delay         | Integer                                 | Required               | Delay (in seconds) can be positive (meaning that the vehicle is late) or negative (meaning that the vehicle is ahead of schedule). Delay of 0 means that the vehicle is exactly on time. |
