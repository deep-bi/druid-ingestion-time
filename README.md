# druid-ingestion-time

Standalone Apache Druid extension that adds a `currentTimestamp` ingestion transform.

Put the built jar into a extensions/druid-ingestion-time directory and add it to `druid.extensions.loadList`.

Once loaded, the transform can be used in `transformSpec`:

```json
{
  "transformSpec": {
    "transforms": [
      {
        "type": "currentTimestamp",
        "name": "ingestedAt"
      }
    ]
  }
}
```

The resulting value is the current wall-clock timestamp in epoch milliseconds, stored as a `LONG`.
