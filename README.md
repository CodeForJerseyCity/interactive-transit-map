## About
This project aims to create an interactive transit map of Jersey City public transportation from GTFS data.
Markers denoting transit vehicles are animated along route lines according to their GTFS schedules.

The project was started during the [#hackforchange](http://hackforchange.org/) hackathon 2014.

The code is essentially a clone of https://github.com/vasile/transit-map, plus GTFS data.

## Status
Currently, the map shows [MTA Metro North data](http://as0.mta.info/mnr/schedules/sched_form.cfm). 
Yes, NYC instead of JC. This is because we had the following problems with JC GTFS data.

#### [NJT Rail GTFS](www.njtransit.com/developer)

1. a required GTFS file, `calendar.txt`, is missing
     * this file tells us what days of week and during which date window each service is active

2. some timestamps in `stop_times.txt` don't make sense, e.g., `27:26:00`

3. `route_short_name`s in `routes.txt` are all empty strings; they should contain the same info [as displayed on train terminals](http://dv.njtransit.com/mobile/tid-mobile.aspx?sid=NY), or some other short identifier

4. we could also filter the data to display only trains that stop in JC

#### [NJT Bus GTFS](www.njtransit.com/developer)

1. we could not get started with this during the hackathon due to the sheer size of the GTFS export (224 MB), but we should try again after filtering out buses that don't stop in JC

#### [NY Waterway](https://github.com/BetaNYC/NY-Waterways-GTFS-data)

1. we used a stale GTFS export (from January 2014) since we could not find anything made available directly by NY Waterway 
    * the link http://www.gtfs-data-exchange.com/agency/ny-waterway/latest.zip sounded promising, but it got us metro north data instead!

2. some timestamp data in `stop_times.txt` contains spaces, e.g., `09:20:00 ,09:20:00`

#### [Jersey Jetneys](http://www.jerseyjitneys.info/?page_id=7)

1. no GTFS data available

## Getting started

To run the current visualization locally:

1. run a web server (e.g., Apache)

2. configure it to serve the `index.html` page from the repo

To import new GTFS data:

1. follow the readme at [https://github.com/vasile/GTFS-viz](https://github.com/vasile/GTFS-viz) (allow yourself 2-3 hours for this...)

## Other Links
* [http://openjerseycity.org/Jitney/](http://openjerseycity.org/Jitney/)
* [http://www.dougandadrienne.info/njbus/indexnnj.html](http://www.dougandadrienne.info/njbus/indexnnj.html)
