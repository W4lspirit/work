# Backend developer in the Data Architecture Team (DA or backend) 

## Current work:
### *Lead Dev*
Building a project to provide a rapid means to build energy-related Datasets for AI Team, Data scientist and Project Manager 
Stack: 
* Scala
* Sangria (Graphql)
* Elasticsearch 
* Cassandra
* Gatling
* Docker
* AKS



## Additional work 
* Provided advices and support material for functional programming and clean lambda in Java
* Provide trick and tips on IntelliJ for the team :D
* Customize the intellij Nyan Cat plugin so instead of the cat we had our manager face encouraging us :D ! 
* Write Architecture Decision Records 
* Write our Developer Guidelines 
* Review the code of the new version of the Android App


* Creation of visualization and dashboards to monitor platform usage and loads from logs
  * calls/service/period 
  * average response time/endpoint
  * SLI 
  * Endpoint response time degradation

* Organized the 'Lunch and learn' meeting (during lunch time :D)
The objective is to deepen our knowledge on various technical subjects
Each week the team would propose different technical topics Theory, framework, Paradigm, Langage each week then vote for the next topic.
And the next week I would prepare a workshop on the selected topic (30 min to 1h30)


## Previous work:
### *POC Api Management*
Goal was to benchmark each solutions and verify it checks the company requirements (Backend, Devops, Data-Acquisition & CTO)
* Kong 
* Azure Api Management
* Gravitee.io

- Java Migration 11 - 13:
* MicroService upgrade 
* Switch to AdoptOpenJdk (Ci,Docker)


### *In charge of building a reactive application which handles sensor time-series aggregation*
Time constraint was 2 weeks
This was my first application fully reactive.
Stack:
* Spring Boot 
* Reactor
* ElasticSearch 
* Cassandra
* Gatling

### *Lead dev on Energy modeling Team (1 year)*

This feature team started as an experiment since we previously did not have feature teams in the company.
Main Topics: Sensor Data And aggregation, Meter Statement, Influencing Factor, Energy Model, Weather Station.
* Common Tasks
	* During Workshop with PO and Project Manager, provide Estimations(sizing), technical conception, and slicing features into smaller sets
	* Challenge PO on implicit performance issues , UI/UX bottleneck
	* Review stories and acceptance rules
	* Design technical implementations and write technical tickets for each story
	* Write load test
	* Provide Documentation and Support for the front end team working from Vietnam 
	* Implement stories 

Stack:
* Spring Boot
* ElasticSearch
* Cassandra (+Reactive)
* Kafka (+Reactive)

### *In charge of Elastic Migration 5 - 7:*
* Rewrote part of the connection layer and ES repository library
* Wrote migration scripts for mono type index and index using multiple doc type (bash+groovy)
* Modified and optimized template
* Add aliases to reduce reindex time

### *Java Migration 8 - 11:*
* Created a presentation from scratch for the Backend team to prepare ourself for the migration when Java 11 will be released (New features,JVM improvements, upgrade path, Jdk vendors)
* Upgrade to Spring boot 2.2.1
* Upgrade backend microservices

Work Before Feature Teams (5 months)
* Wrote the Developer installation guide for linux 
* Integration of PITD (point d'interface transport distribution) data   
* Data Historization:
	* System where each property of an object has a different value in time.
	* Values are defined for a period and data is mutable, users can insert, remove, replace values on periods smaller or larger than the previous, the system must correct inconsistency and rearrange/merge periods.
	* Users can filter on different properties on different periods and retrieve the value of the object at a specific moment in time.
* Implemented Historization for Meter Domain
* Create project to handle Action planning on the platform
