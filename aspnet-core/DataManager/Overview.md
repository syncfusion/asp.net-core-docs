---
layout: post
title: Overview | DataManager  | ASP.NET Core | Syncfusion
description: overview 
platform: aspnet-core
control: DataManager
documentation: ug
---

# DataManager

DataManager helps in managing relational data in the ASP.NET Core. Its rich features make querying data sources easier. The ODataClient supports OData queries that are enabled in the Web API & WCF data services.

## DataManager supports different types of data binding such as:

1. JSON
2. Web Services
3. OData

Basically, all services that have JSON acts as a transport.

## Key Features

Some important features of the DataManager for ASP.NET Core are:

1. DataManager - Communicates with data source and returns the desired result based on the Query provided.
2. Query – DataManager has APIs to generate data query with ease.
3. CRUD in individual requests and Batch – CRUD operations are fully supported. The options are enabled to commit the data as a single or multiple requests.
4. Adaptors – Adaptors are specific dataSource type aware interfaces that are used by DataManager to communicate with DataSource. Three adaptors are created. They are, ODataAdaptor, JsonAdaptor and UrlAdaptor
5. Model binding – Simple model binding is made by using the DataManager. You can directly bind Query result to HTML element.
6. Calculate and maintain aggregates, sorting order and paging

In other words, the DataManager fully supports CRUD (Create, Read, Update, Destroy) data operations, and provides both client-side and server-side support for sorting, paging, filtering, grouping, and aggregates.
