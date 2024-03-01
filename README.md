# API Documentation

## Feed API

### ticks

`GET /v1/feed/ticks/`

Returns ticks data.

#### Example Usage:

`GET /v1/feed/ticks/EURUSD`

#### Response:

- **Type**: JSON
- **Description**: Contains tick data for the specified currency pair.

Example response:

```
{
  "timestamp": "2024-03-01T12:00:00Z",
  "symbol": "EURUSD",
  "bid": 1.1205,
  "ask": 1.1207
}
```

---

### ticks_history

`GET /v1/feed/ticks_history/`

Returns historical ticks data.

#### Parameters:

- **symbol**: String (required) - The currency pair symbol.
- **start_time**: String (optional) - The start time of the historical data (format: "YYYY-MM-DDTHH:MM:SSZ").
- **end_time**: String (optional) - The end time of the historical data (format: "YYYY-MM-DDTHH:MM:SSZ").
- **limit**: Integer (optional) - The maximum number of ticks to return.

#### Example Usage:

`GET /v1/feed/ticks_history/EURUSD?start_time=2024-02-01T00:00:00Z&end_time=2024-02-01T23:59:59Z&limit=100`

#### Response:

- **Type**: JSON
- **Description**: Contains historical tick data for the specified currency pair within the specified time range.

Example response:

```
[
  {
    "timestamp": "2024-02-01T00:00:00Z",
    "symbol": "EURUSD",
    "bid": 1.1200,
    "ask": 1.1202
  },
  {
    "timestamp": "2024-02-01T00:00:01Z",
    "symbol": "EURUSD",
    "bid": 1.1201,
    "ask": 1.1203
  },
  ...
]
```

---

### underlying

`GET /v1/feed/underlying/EURUSD`

Returns information about an underlying

#### Response:

- **Type**: JSON
- **Description**: -

Example response:

```
  {
    "market": "forex",
    "submarket" : "major_pair",
    "pip_size": 0.001
  }
```

---

### trading_calendar

`GET /v1/feed/trading_calendar/`

Returns trading calendar information.

#### Response:

- **Type**: JSON
- **Description**: Contains information about trading hours, holidays, and other relevant calendar data.

Example response:

```
{
  "exchange": "Forex",
  "timezone": "UTC",
  "trading_hours": {
    "Monday": "00:00 - 23:59",
    "Tuesday": "00:00 - 23:59",
    "Wednesday": "00:00 - 23:59",
    "Thursday": "00:00 - 23:59",
    "Friday": "00:00 - 20:00"
  },
  "holidays": [
    "2024-05-01",
    "2024-07-04",
    ...
  ]
}
```

### Team members
- @afshin
- @qinfeng
- @masud

### Roadmap
- Raw feed support
