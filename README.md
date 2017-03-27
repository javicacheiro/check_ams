# check_ams
## Description
Nagios check script for the Ambari Metrics System (AMS).

It is similar in purpose and usage to the `check_tsdb` from OpenTSDB.

## Usage
Check that the average rate (`--rate`) of the metric `metrics/flume/flume/SINK/hdfsSink/EventDrainSuccessCount`
from host `c13-17.local` is not lower than (`--method lt`) 2.5 (warning level) or 1.5 (critical level):

    check_ams --config ./check_ams.conf --component FLUME_HANDLER --host "c13-17.local" \
        --metric "metrics/flume/flume/SINK/hdfsSink/EventDrainSuccessCount" \
        --method lt --rate -w 2.5 -c 1.5

Check that the metric `metrics/flume/flume/CHANNEL/ChannelFillPercentage` is not greater than 50% (warning)
or 75% (critical):

    check_ams --config ./check_ams.conf --component FLUME_HANDLER --host "c13-17.local" \
        --metric "metrics/flume/flume/CHANNEL/ChannelFillPercentage" \
        --method gt -w 50 -c 75

