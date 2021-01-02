# Backend developer in the Data Architecture Team (DA or backend)

## Context

### Current Team structure

The team is composed of 1 Manager(dev), a Tech lead, 4 Developers and 1 Apprentice.

The work is then split between feature team:

* 2 standard feature team (Lead dev + 1 dev + external front devs) (Lead dev + 1 dev + 1
  apprentice + external front devs)
* 1 Technical feature team (Manager + Tech Lead + 1 dev)

Currently, the lead dev changes every 11 weeks for the standard feature team.

Some projects are done outside the feature teams' workflow and sometimes with the support
of other teams such as devops (infrastructure), ML.

## Current work:

### Technical Feature Team - Backend developer

* Solving performance issues on different applications(slow api calls, high memory usage,
  OOM).
* Optimization of reactive applications.
* Data migration (cassandra/elasticsearch) to another azure location:
    * Dsbulk/CQLSH
    * Bash
    * Rust

## Additional work

* Provided advices and support material for functional programming and clean lambda in
  Java
* Provide trick and tips on IntelliJ for the team :D
* Customize the intellij Nyan Cat plugin so instead of the cat we had our manager face
  encouraging us :D !
* Write Architecture Decision Records
* Write our Developer Guidelines
* Write technical/feature documentation
* Review the code of the new version of the Android App
* Introduce the use of the 'code with me' plugin for Pair review/Pair programming.
* Report/fix security/performance issues in production.


* Creation of visualization and dashboards to monitor platform usage and loads from logs
    * calls/service/period
    * average response time/endpoint
    * SLI
    * Endpoint response time degradation

* Organized the 'Lunch and learn' meeting (during lunch time :D)
  The objective is to deepen our knowledge on various technical subjects. Each week the
  team would propose different technical topics Theory, framework, Paradigm, Language each
  week then vote for the next topic. And the next week I would prepare a workshop on the
  selected topic (30 min to 1h30)

## Previous work (Reverse chronological order):

### *APIM project* - Azure Api Management automatic deployment

Goal was to automate the deployment/configuration of our backend Apis (20+ microservices)
on the Azure APIM. And make the whole process painless for the backend developers.

#### Implementation

-> Build Docker Image for the ci to run:

* Ansible
* Azure ansible collection
* azure-api-management-devops-resource-kit tools + runtime

-> Build a project for configuring the different resources of the Azure APIM and generate
the corresponding ARM templates:

* Api (generated from open api specification)
* Product
* User Group
* Policies

-> Build the ci pipeline which retrieve the latest available Open APi Specification on the
target env, generate the adequate ARM template, verify the coherence and invariant
configuration. If there are modifications, push the changes to a deployment branch with
automatic merge on success pipeline.

Ex :

```
INT pipeline -> (
pull latest spec from int instances &&
 generate arm template &&
  validate/check &&
   optional Push to Deploy-INT
)

Deploy-INT pipeline -> (
deploy the generated configuration via Ansible Playbook to the Azure apim int &&
 automtic merge the diff to INT
)
```

-> Create playbook & role for the deployment of the APIM ARM template with support for
multi env/location.

Stack:

* Azure API Management DevOps Resource Kit
* Ansible(playbook,inventories)
* Gitlab (ci+bash)
* Springdoc-openapi
* Azure Api Management

### *Technical feature team* - Backend developer

-> Design the Authorization/Authentication flow/module and implement it and benchmark it.

-> Implement partial periods aggregation to our existing sensor analysis projects (
realtime/pre-calculated bucket)

Stack:

* Java 14
* Spring Boot
* Reactor
* Cassandra
* Elasticsearch
* JWT
* Hazelcast
* Caffeine
* Gatling
* Docker Swarm

### *Bmad Project* - Lead Dev

Building a project to provide a quick way to build energy-related Datasets for AI Team,
Data scientist and Project Manager

Stack:

* Scala
* Sangria (Graphql)
* Elasticsearch
* Cassandra
* Gatling
* Docker
* AKS

### *APIM Project* - POC Api Management

Goal was to benchmark each solution and verify it checks the company requirements (
Backend, Devops, Data-Acquisition & CTO)

* Kong
* Azure Api Management
* Gravitee.io

### Java Migration 11 - 13:

* MicroService upgrade
* Switch to AdoptOpenJdk (Ci,Docker)

### *Technical Feature Team* - Backend developer

-> In charge of building a reactive application which handles sensor time-series
aggregation.

Time constraint was 2 weeks This was my first application fully reactive.

Stack:

* Spring Boot
* Reactor
* ElasticSearch
* Cassandra
* Gatling

### *Energy modeling feature Team* - Lead dev  (1 year)

This feature team started as an experiment since we previously did not have feature teams
in the company. Main Topics: Sensor Data And aggregation, Meter Statement, Influencing
Factor, Energy Model, Weather Station.

* Common Tasks
    * During Workshop with PO and Project Manager, provide Estimations(sizing), technical
      conception, and slicing features into smaller sets
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
* Wrote migration scripts for mono type index and index using multiple doc type (
  bash+groovy)
* Modified and optimized template
* Add aliases to reduce reindex time

### *Java Migration 8 - 11:*

* Created a presentation from scratch for the Backend team to prepare ourself for the
  migration when Java 11 will be released (New features,JVM improvements, upgrade path,
  Jdk vendors)
* Upgrade to Spring boot 2.2.1
* Upgrade backend microservices

### Work Before Feature Teams (5 months)

* Wrote the Developer installation guide for linux
* Integration of PITD (point d'interface transport distribution) data
* Data Historization:
    * System where each property of an object has a different value in time.
    * Values are defined for a period and data is mutable, users can insert, remove,
      replace values on periods smaller or larger than the previous, the system must
      correct inconsistency and rearrange/merge periods.
    * Users can filter on different properties on different periods and retrieve the value
      of the object at a specific moment in time.
* Implemented Historization for Meter Domain
* Create project to handle Action planning on the platform
