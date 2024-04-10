
To query CESGA:

    # EventAcceptedCount lower than 0.8
    ./check_ams --config ./check_ams_cesga.conf --component FLUME_HANDLER --host "c13-6.node.int.cesga.es" --metric "metrics/flume/flume/SOURCE/syslogsource-1/EventAcceptedCount" --method lt --rate --warning 0.8 --critical 0.4

    # EventDrainSuccessCount lower than 2
    ./check_ams --config ./check_ams_cesga.conf --component FLUME_HANDLER --host c13-8.node.int.cesga.es --metric metrics/flume/flume/SINK/hdfsSink/EventDrainSuccessCount --method lt --rate --warning 2 --critical 1 

    # ChannelFillPercentage below 50%
    ./check_ams --config ./check_ams.conf --component FLUME_HANDLER --host "c13-17.local" \
        --metric "metrics/flume/flume/CHANNEL/ChannelFillPercentage" \
        --method gt -w 50 -c 75

