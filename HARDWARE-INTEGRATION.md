# Future API integration notes

The current interface uses sample arrays in `app.js`. Keep the browser UI independent from sensors and route sensor data through a backend.

Example reading:
```json
{
  "sensorId": "TEMP-001",
  "building": "Academic Block",
  "metric": "temperature",
  "value": 28,
  "unit": "C",
  "status": "normal",
  "recordedAt": "2026-10-22T10:24:00+05:30"
}
```

Do not expose MQTT broker passwords, API tokens, or database credentials in frontend code.
