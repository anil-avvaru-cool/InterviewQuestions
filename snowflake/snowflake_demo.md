## Pipes

## Tables

## Streams

## Zones similar to medallion architecture
- Landing zone -> Bronze
- Curated zone -> Silver
- Consumption zone -> Gold

## Schema creation

```sql
create or replace schema landing_zone;
create or replace schema curated_zone;
create or replace schema consumption_zone;

show schemas;
```

https://toppertips.com/snowflake-etl-example-ch19-part01

- pipe is to load csv data from storage like s3 to pre processing like stage env.