## Introduction
{:#introduction}

Transport data is being currently published by transport authorities and operators in many different formats, some of which are well-known de-facto standards, such as the General Transit Feed Specification or GTFS, and some others are ad-hoc data formats whose structure is decided by the data publisher (e.g., current datasets and APIs published by [Empresa Municipal de Transportes de Madrid in its open data portal](https://opendata.emtmadrid.es/), [tram information in Zaragoza](https://www.zaragoza.es/sede/servicio/catalogo/327), etc.). 

All of these datasets have similarities, associated to the fact that they are describing overlapping sets of information (schedules, stops, vehicles, lines, etc.). They are also made available, commonly, using tabular data formats. For example, GTFS feeds are essentially zip-compressed files containing sets of CSV files following the GTFS specification. And other data sources such as those mentioned above as examples provide the data either in CSV or JSON. 

Having all this data available in a homogeneous manner would actually reduce the total cost of reusing data sources, especially across operators/authorities and cities/regions. That is, developers may be able to develop one application that would be deployable in any city in the world with minor adaptations. This is already happening with GTFS, which is not only being used by Google Maps to provide data about transport infrastructure, but also for route planning, but also by other route planners, such as Navita.io and OpenTripPlanner.

To achieve this homogeneity, there are several options that may be followed:

- Transport authorities and operators may agree on using the same data format and hence publish according to such data format. They know well the type of data that they handle, the quality properties on such data, etc., so they should be able to provide this data easily. To some extent, this is what is happening currently with GTFS, and what should happen in the near future in the European Union with NeTex, according to directive 2010/40/EU and regulation 2017/1926 (MMTIS).
- 3rd parties (as well as operators and authorities themselves) may be able to create transformation rules that allow transforming the original data sources into other generally-agreed formats, republishing such transformed data either in the original data portals, if allowed to do so, or in other servers. Transformations may be done programmatically (that is, with ad-hoc code) or declaratively (using mappings in existing languages like R2RML or RML).

In this paper, we present our work on ensuring that declarative mappings can be used for the purpose of transforming transport data published by transport authorities and operators into a homogeneous representation based on Transmodel (the reference data model for public transport at European level, which will be further described in section 2). This data can then be further transformed into NeTEx so as to comply with the EU regulations for the publication of transport-related data in National Access Points.


