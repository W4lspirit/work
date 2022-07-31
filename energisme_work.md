# Backend developer in the Data Architecture Team (DA or backend)

## Context

### Current Team structure

1 Manager 1 Tech lead 1 Dev 1 Devops

## Current work:

### Product Team "Datalake" Datastore - Backend developer S1 2022-XXX

* State of the art
* Review of different architecture and implementations
* Review of storage engine/database
* Architecture design/review with team & Architect
* Implementation of different prototype/mvp using already deployed technologies & new ones

### Rust self-training 2 Days/month

#### Context

I discovered rust, in 2017, third semester of my master degree in Computer Science,
french Engineer came to do a small presentation about the use of rust for in Servo
Since then I was pretty much amazed by it, and kept reading news about it and starting

Already started learning rust on personal time early 2018 but failed to grasp/change habit on relying on IDE
Started with zero to prod

#### December 2021

* Finished Rust book

#### January 2022

* Finished Rustlings Exercise
* Started Rust in Action Book Stop at chapter 6.3

#### February 2022

* Finished Rust In Action:
    * For Chapter 11&12 (Kernel&Signal) only read (no code written)
* Continued Zero to prod

#### March/April 2022

* Finished last chapters of Zero to prod

#### June/July/August 2022

## Additional work

* Provided advices and support material for functional programming and clean lambda in Java
* Provide trick and tips on IntelliJ for the team :D
* Customize the intellij Nyan Cat plugin so instead of the cat we had our manager face encouraging us :D !
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
  The objective is to deepen our knowledge on various technical subjects. Each week the team would propose different
  technical topics Theory, framework, Paradigm, Language each week then vote for the next topic. And the next week I
  would prepare a workshop on the selected topic (30 min to 1h30)

## Previous work (Reverse chronological order):

### Previously Technical Feature Team - Backend developer (2018-2021)

The team is composed of 1 Manager(dev), a Tech lead, 5 Developers.

The work is then split between feature team:

* 2 standard feature team (Lead dev + 2 dev + external front devs) (Lead dev + 1 dev + 1 apprentice + external front
  devs)
* 1 Technical feature team (Manager + Tech Lead + 1 dev)

Currently, the lead dev changes every 11 weeks for the standard feature team.

Some projects are done outside the feature teams' workflow and sometimes with the support of other teams such as
devops (infrastructure), ML.

#### Main topic:

* Application security
* Authorization/authentication flow and upgrade
* Access-control
* Automation of tedious tasks
* Pair Programming
* Code Review
* Review feature Architecture/Design
* k8s migration (helm+argocd)
* APIM improvement
* Writing Documentation
* Solving performance issues on different applications(slow api calls, high memory usage, OOM).
* Optimization of reactive applications.
* Observability(opentelemetry + jaeger + sleuth)
* Data migration (cassandra/elasticsearch) to another azure location:
    * Dsbulk/CQLSH
    * Bash
    * Rust

## Q4 2021

### PaaS Migration

* Upgrade kubernetes add-ons (traefik, prometheus-stack, filebeat) so it can be deployed via our PaaS offer

### Kubernetes migration

Migrate monitoring tooling to kubernetes using dedicated CRD

* Prometheus-stack (helm chart)
    * Configure metrics scraping for the middlewares  (cassandra elasticsearch kafka)
* Prometheus-adapter (helm chart)
    * Configure custom autoscaling rules

### Observability

* Prepare core library for spring-cloud-sleuth-otel (opentelemetry)
* Add tracing support to Elasticsearch client and Spring Reactive Elastic client
* Instrument maven build (via maven otel plugin)

### Azure Managed Cassandra

* Evaluate cost & perf migration to AMC
* Poc & restitution

### Performance Improvement

* profiling & jvm tuning

## Q3 2021

### Tutor Intern for 3 months

* Pair Programming/Review

### Platform & Application security

* Design & Implementation of major security/authorization improvement
    * Application security
    * Authorization/authentication flow and upgrade
    * Organization based Access-control
* Coordinate the changes with other dev teams

## Q2 2021

### Astra Datastax Migration

* Prepare migration to Astra (data migration, perf analysis, non regression testing)

### Kubernetes migration

* Prepare migration from docker swarm to k8s for 20+ microservice (springboot) :
    * remove use of config server + discovery to leverage the native option of k8s
    * Prepare helm starter chart for backend services (app configuration, ingress + tls, autoscaling)
    * Argocd for gitops

Stack:

* AKS
* Argocd
* Helm
* Spring boot
* Java 16
* Traefik

## Q1 2021

### Training Kubernetes (self training & linux foundation training)

https://www.credly.com/badges/f15d292b-ceca-4724-9965-9b82f7c541e1?source=linked_in_profile

### *APIM project* - Azure Api Management automatic deployment

Provide a simple configuration project with ci/cd pipelines for all dev teams wanting to expose & secure their Api

## Q4 2020

### *APIM project* - Azure Api Management automatic deployment

Goal was to automate the deployment/configuration of our backend Apis (20+ microservices)
on the Azure APIM. And make the whole process painless for the backend developers.

#### Implementation

-> Build Docker Image for the ci to run:

* Ansible
* Azure ansible collection
* azure-api-management-devops-resource-kit tools + runtime

-> Build a project for configuring the different resources of the Azure APIM and generate the corresponding ARM
templates:

* Api (generated from open api specification)
* Product
* User Group
* Policies

-> Build the ci pipeline which retrieve the latest available Open APi Specification on the target env, generate the
adequate ARM template, verify the coherence and invariant configuration. If there are modifications, push the changes to
a deployment branch with automatic merge on success pipeline.

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
 automatic merge the diff to INT
)
```

-> Create playbook & role for the deployment of the APIM ARM template with support for multi env/location.

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

Building a project to provide a quick way to build energy-related Datasets for AI Team, Data scientist and Project
Manager

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

-> In charge of building a reactive application which handles sensor time-series aggregation.

Time constraint was 2 weeks This was my first application fully reactive.

Stack:

* Spring Boot
* Reactor
* ElasticSearch
* Cassandra
* Gatling

### *Energy modeling feature Team* - Lead dev  (1 year)

This feature team started as an experiment since we previously did not have feature teams in the company. Main Topics:
Sensor Data And aggregation, Meter Statement, Influencing Factor, Energy Model, Weather Station.

* Common Tasks
    * During Workshop with PO and Project Manager, provide Estimations(sizing), technical conception, and slicing
      features into smaller sets
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

* Created a presentation from scratch for the Backend team to prepare ourself for the migration when Java 11 will be
  released (New features,JVM improvements, upgrade path, Jdk vendors)
* Upgrade to Spring boot 2.2.1
* Upgrade backend microservices

### Work Before Feature Teams (5 months)

* Wrote the Developer installation guide for linux
* Integration of PITD (point d'interface transport distribution) data
* Data Historization:
    * System where each property of an object has a different value in time.
    * Values are defined for a period and data is mutable, users can insert, remove, replace values on periods smaller
      or larger than the previous, the system must correct inconsistency and rearrange/merge periods.
    * Users can filter on different properties on different periods and retrieve the value of the object at a specific
      moment in time.
* Implemented Historization for Meter Domain
* Create project to handle Action planning on the platform
