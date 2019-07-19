## Transmodel Ontology and GTFS
{:#onett}

In its drive to foster interoperability across Europe, the EU is requiring each Member State to allow access to transportation data via a National Access Point (NAP). According to the EU Regulation 2017/1926, all transportation authorities, transport operators and infrastructure managers must provide static and dynamic data in specific data formats (e.g., NeTEx, SIRI).
- the EU Regulation applies to different transportation modes, including air, train, road vehicle, bus, ferry, metro, tram, shuttlebus, car-sharing, car-pooling and bike-sharing.

Transmodel is the European Reference Data Model for Public Transport. It provides a conceptual model of common public transport concepts and data structures that can be used to build many different kinds of public transport information system such as timetabling, fares, operational management, real-time data, journey planning. It is divided into eight different sections or  Parts: Common Concepts (CC), Public Transport Network Topology (NT), Network Description (ND), Operations Monitoring & Control (OM), Fare Management (FM), Passenger Information (PI), Driver Management (DM), Management Information & Statistics (MI). 

These parts or sections are usually developed by different standards or specific data formats. One of the most relevant implementations is NeTEx, which covers partially some features of the parts CC, NT, ND, FM and PI. NeTEx releases the 2017/1926 EU Regulation (May 2017) where the European Commission recognized NeTEx as a strategic standard for the cross-border exchange of data. The first step must be taken before December 2019 when every European country must provide data available in NeTEx format at National Access Points to allow  EU-wide multi-modal travel information services.

The General Transit Feed Specification (GTFS) is a de-facto standard for representing public transport data, a collection of at least five required, two optional required and up to fifteen CSV files (with extension .txt and preferably encoded as UTF-8) contained within a .zip file to describe a transit scheduled operations system. The aim of GTFS is providing at least trip-planning functionality.  It defines the headers and a set of rules that must be taken into account when the dataset is created. Each file, as well as its headers, can be mandatory or optional and they have relations among them. The specification supports the representation of several public transport features such as trips, routes, stops, times, fares or calendar.

In order to provide a better GTFS to NeTEx conversion and further full data interoperability, we have started to build up a Transmodel Ontology. The development is released in a [github repository](https://github.com/oeg-upm/transmodel-ontology) where every material generated in the different activities carried out during the development of the vocabulary, as for instance use cases, user stories, glossary of terms, etc., will be available in the Vocabulary Wiki Project maintenance. Eventually, some queries will be performed in a SPARQL endpoint to test and exemplify its operability. Furthermore, in the context of work in a CEN Transmodel working group has published a base [URI](https://w3id.org/transmodel/terms#) that is used by ONETT to perform the transformations. Before performing the transformation from GTFS to the ontology based format of Transmodel, we analyse the relationship between the two standards. For example, in [](#comparison) we show the relation between the properties of the calendar.txt in the GTFS model with the corresponding property in Transmodel using the NeTEx implementation. The full relation between the two standards is available [online](https://github.com/osoc-es/onett-paper/tree/master/Gtfs2Transmodel).

<figure id="comparison" class="table" markdown="1">

| GTFS-Calendar      | Transmodel (NeTEx) |
| :-------------: |:-------------:|
| service_id      | \<DayType>@id + \<ServiceCalendarFrame> @id |
| moday      | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>monday |
| tuesday | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>tuesday      |
| wednesday | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>wednesday    |
| thursday | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>thursday     |
| friday | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>friday      |
| saturday | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>saturday     |
| sunday | \<DayType>\<properties>\<PropertyOfDay>\<DaysOfWeek>sunday      |
| start_date | \<ServiceCalendar>\<FromDate>      |
| end_date | \<ServiceCalendar>\<ToDate>      |
	
<figcaption markdown="block">
Relation among GTFS-Calendar properties and Transmodel in NeTEx implementation
</figcaption>
</figure>

