<div align="center">

![project logo](https://user-images.githubusercontent.com/76540311/217404630-863299b2-1b21-4ae7-8330-28f980be614f.png)


# Fire and Smoke Digital Twin: API
See the [Frontend](https://github.com/UrbanInfoLab/FireIncidentFrontend) or the [Backend](https://github.com/UrbanInfoLab/FireIncidentBackend).

[![latest release badge]][latest release link] [![github stars badge]][github stars link] [![github forks badge]][github forks link]

[![CI checks on main badge]][CI checks on main link] [![latest commit to main badge]][latest commit to main link]

[![github open issues badge]][github open issues link] [![github open prs badge]][github open prs link]

[CI checks on main badge]: https://flat.badgen.net/github/checks/urbaninfolab/FireIncidentBackend/main?label=CI%20status%20on%20main&cache=900&icon=github
[CI checks on main link]: https://github.com/urbaninfolab/FireIncidentBackend/actions/workflows/test-invoke-conda.yml
[github forks badge]: https://flat.badgen.net/github/forks/urbaninfolab/FireIncidentBackend?icon=github
[github forks link]: https://useful-forks.github.io/?repo=urbaninfolab%2FFireIncidentBackend
[github open issues badge]: https://flat.badgen.net/github/open-issues/urbaninfolab/FireIncidentBackend?icon=github
[github open issues link]: https://github.com/urbaninfolab/FireIncidentBackend/issues?q=is%3Aissue+is%3Aopen
[github open prs badge]: https://flat.badgen.net/github/open-prs/urbaninfolab/FireIncidentBackend?icon=github
[github open prs link]: https://github.com/urbaninfolab/FireIncidentBackend/pulls?q=is%3Apr+is%3Aopen
[github stars badge]: https://flat.badgen.net/github/stars/urbaninfolab/FireIncidentBackend?icon=github
[github stars link]: https://github.com/urbaninfolab/FireIncidentBackend/stargazers
[latest commit to main badge]: https://flat.badgen.net/github/last-commit/urbaninfolab/FireIncidentBackend/main?icon=github&color=yellow&label=last%20dev%20commit&cache=900
[latest commit to main link]: https://github.com/urbaninfolab/FireIncidentBackend/commits/main
[latest release badge]: https://flat.badgen.net/github/release/urbaninfolab/FireIncidentBackend/development?icon=github
[latest release link]: https://github.com/urbaninfolab/FireIncidentBackend/releases

</div>

The Fire and Smoke Digital Twin is a cutting-edge solution that predicts smoke paths in 2D and 3D and provides real-time analysis of air quality drops due to fires. The digital twin collects and archives fire incident data from cities all over the US, and uploads nightly to this repository.

_Note: This repository serves as an API endpoint for collected data and provides documentation to access the real-time API. To see the code behind querying each city for fire data and generating predicted impact, see the [Backend](https://github.com/UrbanInfoLab/FireIncidentBackend), and for the code behind displaying this data in real-time, see the [Frontend](https://github.com/UrbanInfoLab/FireIncidentFrontend)._

<div align="center">

</div>

# Getting Started with Fire & Smoke Digital Twin API

This repository serves fire data in the following format:

```
/api/v1/ {CITY} / {YEAR} / {MONTH} / {DAY} / FireMap.json
```

An example to get the data from August 9th, 2022, of Los Angeles fires would be:
```
/api/v1/LosAngeles/2022/08/09/FireMap.json
```

Notice that spaces are removed from city names, and that all numbers below 10 are zero padded.
To visually see the data structure of our API, just look through the repository files above.

You can query this directly from our live server, at 

https://smartcity.tacc.utexas.edu/fire/api/v1/LosAngeles/2022/08/09/FireMap.json


Or, for better uptime and performance, from this repo at 

https://raw.githubusercontent.com/urbaninfolab/FireIncidentData/master/api/v1/LosAngeles/2022/08/09/FireMap.json

## Recommended API Usage

For historical data, which we consider anything from yesterday to the start of our data collection, please use
```
https://raw.githubusercontent.com/urbaninfolab/FireIncidentData/master/api/v1/
```
as an endpoint. This relieves strain from our live server, and has GitHub deliver much faster results.

For real-time data, which is anything from the current day, please use our live server at
```
https://smartcity.tacc.utexas.edu/fire/api/v1/
```
to get the latest results.

## Data Example

All data is in a JSON dictionary with a RSS-like syntax. To access the fire data, it's under ["rss"]["channel"]["item"].
Watch out for singular fire cases, in which the ["rss"]["channel"]["item"] will return a single dict object {} and not a list of dict [{},{}].

### Notice

All data from our API is cloned on a nightly basis to this repository. There are no differences between our API and the files this repository lists.

## Coverage

We are currently collecting and publishing active fire data from the following cities:             

| City Name | Collection Start Date |      
| --------------- | --------------- |
| Austin, Texas | February 1, 2022 |
| Dallas, Texas | July 6, 2022 |
| El Paso, Texas | July 17, 2022 |
| Houston, Texas | July 6, 2022 |
| Los Angeles, California | July 18, 2022 |
| Miami, Florida | January 23, 2023 |
| Milwaukee, Wisconsin | January 23, 2023 |
| Orlando, Florida | January 23, 2023 |
| Portland, Oregon | January 23, 2023 |
| Riverside, California | July 17, 2022 |
| San Antonio, Texas | July 7, 2022 |
| San Antonio, Texas | July 7, 2022 |
| San Diego, California | September 8, 2022 |
| Seattle, Washington | July 19, 2022 |

This table is sorted alphabetically by city.

Please note that due to some outages, we are missing data for a few days out of the year of 2022. Please keep this in mind when using the data.

### Contributing

If you know a city we have not listed here that provides an open real-time fire data page, please open an [Issue](https://github.com/urbaninfolab/FireIncidentData/issues) and let us know!
Alternatively, open a [pull request](https://github.com/urbaninfolab/FireIncidentBackend/pulls) to our [Backend](https://github.com/urbaninfolab/FireIncidentBackend) with the city added.

On the off-case someone has fire data in a different format and would like to convert it to our format,
and upload past fire data to our API, please review our conversions in our Backend, or reach out via an Issue.

### Contributors

This project is a combined effort of the [Urban Information Lab](https://sites.utexas.edu/uil) and others.
[Check out the list of all these amazing people](https://github.com/urbaninfolab/FireIncidentBackend/collaborators). We thank them for
their time, hard work and effort.






