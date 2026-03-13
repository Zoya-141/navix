READ THIS FIRST AND USE IT AS PERMANENT CONTEXT.

PROJECT NAME: NaviX

NaviX is a safety-aware route recommendation system designed to suggest safer travel routes using environmental and infrastructural indicators derived from open geospatial data.

Traditional navigation systems prioritize shortest or fastest routes. NaviX introduces a safety dimension by evaluating road segments using safety indicators and integrating those scores into the routing algorithm.

The project is currently UNDER DEVELOPMENT as an academic prototype.

--------------------------------------------------

PROJECT OBJECTIVE

The objective of NaviX is to build a system that computes safer routes through cities by analyzing road segments and assigning safety risk scores to them.

Key principles of the project:

- privacy-first design
- no crime datasets
- no real-time surveillance
- explainable safety metrics
- open geospatial data (OpenStreetMap)

--------------------------------------------------

SYSTEM ARCHITECTURE

The system has three major layers:

1. Frontend (my responsibility)
2. Backend (FastAPI services)
3. Database (PostgreSQL + PostGIS)

--------------------------------------------------

BACKEND OVERVIEW

The backend performs:

- geospatial data processing
- safety feature extraction
- risk score computation
- route computation using a modified A* algorithm

Technologies used by backend:

- Python
- FastAPI
- NetworkX
- OSMnx
- GeoPandas
- Shapely

The backend exposes REST APIs which the frontend consumes.

--------------------------------------------------

DATA SOURCE

Geospatial data comes from OpenStreetMap.

The backend extracts:

- road networks
- intersections
- POIs
- lighting data
- infrastructure indicators

The road network is represented as a graph where:

nodes = intersections  
edges = road segments

--------------------------------------------------

ROUTING ENGINE

The routing system uses a modified A* algorithm.

Traditional A*:

f(n) = g(n) + h(n)

Where:

g(n) = cost from start to node  
h(n) = heuristic distance to destination

In NaviX the edge cost incorporates safety risk:

edge_cost = α * distance + β * risk_score

This allows the system to compute routes that balance safety and distance.

The backend can return multiple route types:

- shortest route
- safest route
- balanced route

--------------------------------------------------

EXPECTED FRONTEND OUTPUT

The frontend must visualize:

- road network
- route geometry
- safety levels
- multiple route options

The UI should allow the user to:

- input start location
- input destination
- display route on map
- show safety level indicators
- compare routes

--------------------------------------------------

MY ROLE IN THE TEAM

I am responsible for FRONTEND DEVELOPMENT and UI/UX DESIGN.

My responsibilities include:

MAP VISUALIZATION

- displaying routes on a map interface
- visualizing safety levels using color-coded routes
- rendering geospatial data returned from backend APIs

USER INTERFACE

- designing clean and intuitive UI
- allowing users to enter start and destination locations
- displaying route details and safety scores

API INTEGRATION

- consuming FastAPI backend endpoints
- sending requests for route computation
- rendering the returned route data

DATA VISUALIZATION

- displaying different route types
- showing safety indicators
- optionally displaying heatmaps of risk levels

USER EXPERIENCE

- making the interface responsive
- ensuring smooth interaction with map and route controls

--------------------------------------------------

WHAT I DO NOT WORK ON

Do not focus on:

- backend safety scoring logic
- dataset extraction
- routing algorithm implementation
- Docker infrastructure

Only explain how these systems affect frontend integration.

--------------------------------------------------

TECH STACK

Frontend technologies:

ReactJS  
JavaScript  
TailwindCSS  

Map visualization tools may include:

Leaflet
Mapbox
or other JavaScript mapping libraries.

Backend communication:

REST APIs from FastAPI.

--------------------------------------------------

HOW YOU SHOULD ASSIST ME

When helping with this project:

- focus on frontend architecture
- help design React components
- help build map visualization features
- assist with API integration
- help improve UI/UX

Prefer:

- modular React components
- clean and readable code
- simple user workflows

Assume this is an academic prototype rather than a large production application.

--------------------------------------------------

ACKNOWLEDGE THIS CONTEXT AND USE IT FOR ALL FUTURE RESPONSES IN THIS CHAT.
