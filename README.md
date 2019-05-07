# ![LOGO](logo.png) Stationsdatenbereitstellung **flow**ground Connector

## Description

A generated **flow**ground connector for the Stationsdatenbereitstellung API (version 2.2.01).

Generated from: https://api.apis.guru/v2/specs/deutschebahn.com/stada/2.2.01/swagger.json<br/>
Generated at: 2019-05-07T17:40:14+03:00

## API Description

An API providing master data for german railway stations by DB Station&Service AG.

## Authorization

This API does not require authorization.

## Actions

### This operation provides the master data for german railway stations.

> Get a QueryResult object containing station objects from the database applying to the parameters described below. <br/>
> <br/>
> QueryResult is a container providing the following information about the query result.<br/>
>   1. the total number of hits<br/>
>   2. the maximum number of hits to be returned in that QueryResult object<br/>
>   3. the offset of the first hit returned in that QueryResult object with respect to all hits returned by the query<br/>
>   4. the result objects<br/>
>   <br/>
> The parameters described below work as filters to reduce the number of hits returned. Some of these parameters must be used only once, others are allowed to be used multiple times. Valid parameters that are allowed to be used only once are _offset_, _limit_ and _logicaloperator_. <br/>
> <br/>
> All other parameters described below may be used multiple times.<br/>
> <br/>
> If a parameter is given more than once, the result will contain all hits that match all given parameter values.<br/>
> <br/>
> E.g. _federalstate=berlin&federalstate=saarland_ returns all stations in Berlin and Saarland.<br/>
> <br/>
> If more than one filter criterion is used at the same time, the different filter criteria are interpreted as if they are combined by a logical AND operator, unless the parameter _logicaloperator_ is set to _or_.<br/>
> <br/>
> E.g. _category=1-2&federalstate=hamburg_ returns all stations in Hamburg having category 1 or 2.<br/>
> <br/>
> _category=1-2&federalstate=hamburg&federalsate=hessen_ returns all stations in Hamburg and Hessen having category 1 or 2, while<br/>
> <br/>
> _searchstring=berlin*&federalstate=hamburg&federalsate=hessen&logicaloperator=or_ will return all stations with a name starting with 'berlin' as well as all stations in Hamburg and Hessen.<br/>
> <br/>
> If no 'limit' parameter is given, the number of hits (stations) is set to its maximum value of 10000.<br/>
> <br/>
> To specify parameter values containing German umlauts, the following encoding has to be used<br/>
>   * a  => %C3%A4<br/>
>   * o  => %C3%B6<br/>
>   * u  => %C3%BC<br/>
>   * A  => %C3%84<br/>
>   * O  => %C3%96<br/>
>   * U  => %C3%9C<br/>
>   * ss  => %C3%9F

#### Input Parameters
* `offset` - _optional_ - Offset of the first hit returned in the QueryResult object with respect to all hits returned by the query. If this parameter is omitted, it will be set to 0 internally.
* `limit` - _optional_ - The maximum number of hits to be returned by that query. If 'limit' is set greater than 10000, it will be reset to 10000 internally and only 10000 hits will be returned.
* `searchstring` - _optional_ - String to search for a station name. The wildcards * (indicating an arbitrary number of characters) and ? (indicating one single character) can be used in the search pattern. A comma separated list of station names is also supported (e.g. searchstring=hamburg*,berlin*).
* `category` - _optional_ - Filter by station category. Category ranges are supported as well as lists of categories (e.g. category=2-4 or category=1,3-5). The category must be between 1 and 7 otherwise a parameter exception is returned.
* `federalstate` - _optional_ - Filter by German federal state. Lists of federal states are also supported (e.g. federalstate=bayern,hamburg). Wildcards are not allowed here.
* `eva` - _optional_ - Filter by EVA number. Wildcards are not allowed here.
* `ril` - _optional_ - Filter by Ril100-identifier. Wildcards are not allowed here.
* `logicaloperator` - _optional_ - Logical operator to combine query parameters (default=AND). See above for further details.  Allowed values: or, and

### This operation provides the master data for a german railway station selected by its station-id.

> Get a QueryResult object containing one station object specified by its id.

#### Input Parameters
* `id` - _required_ - Station ID (Bahnhofsnummer)

### This operation provides the master data for 3-S-Zentralen.

> Get a QueryResult object containing SZentralen objects from the database applying to the parameters described below. <br/>
> QueryResult is a container providing the following information about the query result.<br/>
>   1. the total number of hits<br/>
>   2. the maximum number of hits to be returned in that QueryResult object<br/>
>   3. the offset of the first hit returned in that QueryResult object with respect to all hits returned by the query<br/>
>   4. the result objects

#### Input Parameters
* `offset` - _optional_ - Offset of the first hit returned in the QueryResult object with respect to all hits returned by the query. If this parameter is omitted, it will be set to 0 internally.
* `limit` - _optional_ - The maximum number of hits to be returned by that query. If 'limit' is set greater than 10000, it will be reset to 10000 internally and only 100 hits will be returned.

### This operation provides the master data for 3-S-Zentralen select by its id.

> Get a QueryResult object containing one SZentralen object specified by its id.

#### Input Parameters
* `id` - _required_ - id of the 3-S-Zentrale.

## License

**flow**ground :- Telekom iPaaS / deutschebahn-com-stada-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
