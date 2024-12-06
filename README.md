
# FoxCast API Documentation 🌟

Welcome to the **FoxCast API Documentation**! 🎉  
This API provides access to events, results, odds, and much more from different sports leagues and tournaments. Whether you're building a sports app or integrating live data into your platform, the FoxCast API is here to help. It's the **official API of FoxCast** ([www.playfoxcast.com](https://www.playfoxcast.com)).

---

## 🎯 Quick Example

Here’s an example of what you can achieve with the FoxCast API:

### Request
```bash
GET https://www.playfoxcast.com/server/endpoint/events/323232
```

### Response (Example)
```json
{
  "events": [
    {
      "team_1": "Fulham",
      "team_2": "Brighton",
      "date": "2024-12-05 20:30:00",
      "odd_team_1": 2.38,
      "odd_team_2": 2.92,
      "odd_draw": 3.82
    }
  ]
}
```

With just a single call, you get access to teams, match date, and odds, making integration seamless and efficient! ⚡

---

## 🚀 Features

- 📅 **Retrieve Events**: Access detailed information about sports events.  
- 🏆 **Get Results**: Fetch results of completed events or leagues.  
- 🔢 **Odds Integration**: Get odds and other interesting data points for events.  
- 🌍 **Global Coverage**: Supports multiple sports and regions.  

Be free to comment or recommend features—new ones are added frequently! 💡

---

## Table of Contents

1. [Overview](#overview)
2. [Base URL](#base-url)
3. [Authentication](#authentication)
4. [Endpoints](#endpoints)
    - [Retrieve Events](#1-retrieve-events)
    - [Retrieve Results by League](#2-retrieve-results-by-league)
    - [Retrieve Results by Event ID](#3-retrieve-results-by-event-id)
    - [Retrieve Available League IDs (BBIDs)](#4-retrieve-available-league-ids-bbids)
5. [Supported Championships](#supported-championships)
6. [Examples](#examples)
7. [Error Handling](#error-handling)
8. [Changelog](#changelog)

---

## Overview

The FoxCast API provides access to event and result data from various sports leagues and events. This API is designed to support high-performance applications with real-time updates and comprehensive filters.

---

## Base URL

All API requests should be made to the following base URL:

```
https://www.playfoxcast.com/server/endpoint
```

---

## Authentication

> **Note:** Currently, the API does not require authentication. Future versions may include an API key for enhanced security.

---

## Endpoints

### 1. Retrieve Events
Retrieve details of specific events for a league.

- **Method**: `GET`
- **URL**: `/events/{bbid}`

#### **Path Parameters**
| Parameter | Type   | Required | Description               | Example  |
|-----------|--------|----------|---------------------------|----------|
| `bbid`    | Int    | Yes      | Unique league identifier  | `323232` |

#### **Example Request**
```bash
curl -X GET "https://www.playfoxcast.com/server/endpoint/events/323232"
```

---

### 2. Retrieve Results by League
Retrieve all results for a specific league.

- **Method**: `GET`
- **URL**: `/results/{league_id}`

#### **Path Parameters**
| Parameter   | Type   | Required | Description               | Example  |
|-------------|--------|----------|---------------------------|----------|
| `league_id` | Int    | Yes      | Unique league identifier  | `323232` |

#### **Example Request**
```bash
curl -X GET "https://www.playfoxcast.com/server/endpoint/results/323232"
```

---

### 3. Retrieve Results by Event ID
Retrieve the result for a specific event.

- **Method**: `GET`
- **URL**: `/results/{event_id}`

#### **Path Parameters**
| Parameter   | Type   | Required | Description               | Example   |
|-------------|--------|----------|---------------------------|-----------|
| `event_id`  | Int    | Yes      | Unique event identifier   | `1358253` |

#### **Example Request**
```bash
curl -X GET "https://www.playfoxcast.com/server/endpoint/results/1358253"
```
---

### 4. Retrieve Available League IDs (BBIDs)
Retrieve all active and supported league identifiers (`bbid`) that can be used with `/events` and `/results` endpoints.

- **Method**: `GET`
- **URL**: `/league_ids/`

#### **Response**
A list of leagues with their corresponding identifiers (`bbid`), including essential metadata like region, sport, and championship.

#### **Example Request**
```bash
curl -X GET "https://www.playfoxcast.com/server/endpoint/league_ids/"
```

---

## Supported Championships

Here is a table of supported championships and their corresponding `bbid` values:

| **bbid**   | **Region**       | **Sport**     | **Championship**                          |
|------------|------------------|---------------|-------------------------------------------|
| 323232     | ENGLAND          | football      | Premier League                            |
| 121212     | SPAIN            | football      | LaLiga                                    |
| 2277880    | NETHERLANDS      | football      | Eredivisie                                |
| 2277931    | USA              | hockey        | NHL                                       |
| 2278619    | USA              | basketball    | NBA                                       |
| 2277633    | ITALY            | football      | Coppa Italia                              |
| 2277655    | SPAIN            | football      | Copa del Rey                              |
| 4579334    | SWITZERLAND      | hockey        | National League                           |
| 4579368    | EUROPE           | football      | Champions League - League phase           |
| 4579369    | EUROPE           | football      | Europa League - League phase              |
| 313131     | ITALY            | football      | Serie A                                   |
| 158        | WORLD            | football      | Friendly International                    |
| 101010     | GERMANY          | football      | Bundesliga                                |
| 434343     | FRANCE           | football      | Ligue 1                                   |
| 2278609    | SWITZERLAND      | football      | Super League                              |
| 4579336    | JAPAN            | football      | J1 League                                 |
| 4579367    | THAILAND         | football      | Thai League 1                             |
| 4579337    | SAUDI ARABIA     | football      | Saudi Professional League                 |
| 2277610    | ENGLAND          | football      | FA Cup                                    |
| 2276249    | SOUTH AMERICA    | football      | Copa Libertadores - Play Offs            |
| 2276253    | SOUTH AMERICA    | football      | Copa Sudamericana - Play Offs            |
| 4579338    | SOUTH AMERICA    | football      | World Championship - Qualification        |
| 4579363    | EUROPE           | football      | UEFA Nations League - League A           |
| 4579364    | EUROPE           | football      | UEFA Nations League - League B           |
| 4579365    | EUROPE           | football      | UEFA Nations League - League C           |
| 4579366    | EUROPE           | football      | UEFA Nations League - League D           |

---

## Examples

#### Retrieve Events for a League
- **Example URL**:  
  [https://www.playfoxcast.com/server/endpoint/events/323232](https://www.playfoxcast.com/server/endpoint/events/323232)  

- **cURL Command**:  
  ```bash
  curl -X GET "https://www.playfoxcast.com/server/endpoint/events/323232"
  ```

#### Retrieve Results for a League
- **Example URL**:  
  [https://www.playfoxcast.com/server/endpoint/results/323232](https://www.playfoxcast.com/server/endpoint/results/323232)  

- **cURL Command**:  
  ```bash
  curl -X GET "https://www.playfoxcast.com/server/endpoint/results/323232"
  ```

#### Retrieve Results for a Specific Event
- **Example URL**:  
  [https://www.playfoxcast.com/server/endpoint/results/1358253](https://www.playfoxcast.com/server/endpoint/results/1358253)  

- **cURL Command**:  
  ```bash
  curl -X GET "https://www.playfoxcast.com/server/endpoint/results/1358253"
  ```

---

## Error Handling

The API uses standard HTTP status codes to indicate the success or failure of a request.

| Status Code | Meaning                 | Description                                         |
|-------------|-------------------------|-----------------------------------------------------|
| `200`       | OK                      | The request was successful.                        |
| `400`       | Bad Request             | The request could not be understood or was missing parameters. |
| `404`       | Not Found               | The requested resource could not be found.         |
| `500`       | Internal Server Error   | The server encountered an error while processing the request. |

### Example Error Response
```json
{
  "error": "Not found"
}
```

---

## Changelog

### v1.0.0 - Initial Release
- Added `/events/{bbid}` endpoint to retrieve event data for a league.
- Added `/results/{league_id}` endpoint to retrieve results for a league.
- Added `/results/{event_id}` endpoint to retrieve results for a specific event.

---

## Contact

For questions or support, please contact the FoxCast team at [support@playfoxcast.com](mailto:support@playfoxcast.com).
