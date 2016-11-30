# Neo4j CSV export-import examples

## Exporting

```
rm -rf trainbenchmark
mkdir trainbenchmark
```

```
cat export-csvs.txt | bin/neo4j-shell
```

## Importing

```
bin/neo4j stop
rm -rf data/databases/graph.db
```

```
time bin/neo4j-import --into data/databases/graph.db \
  --nodes:Region trainbenchmark/regions.csv \
  --nodes:Route trainbenchmark/routes.csv \
  --nodes:Segment:TrackElement trainbenchmark/segments.csv \
  --nodes:Semaphore trainbenchmark/semaphores.csv \
  --nodes:Sensor trainbenchmark/sensors.csv \
  --nodes:Switch:TrackElement trainbenchmark/switches.csv \
  --nodes:SwitchPosition trainbenchmark/switchPositions.csv \
  --relationships:connectsTo trainbenchmark/connectsTo.csv \
  --relationships:entry trainbenchmark/entry.csv \
  --relationships:exit trainbenchmark/exit.csv \
  --relationships:follows trainbenchmark/follows.csv \
  --relationships:monitoredBy trainbenchmark/monitoredBy.csv \
  --relationships:requires trainbenchmark/requires.csv \
  --relationships:target trainbenchmark/target.csv
```
