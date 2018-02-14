Jitsi Videobridge Rest Dealer
=============================

This is a build for jitsi videobridge that contain rest dealer.
In additional to jitsi videobridge it will provide possibility to load ChannelStatsDealer
OSGi bundle.

ChannelStatsDealer subscribes to CHANNEL_CREATED_TOPIC, CHANNEL_EXPIRED_TOPIC messages and update
selected by `org.jitsi.videobridge.ChannelStatsDealer.ORIGIN` rest service.
Rest service must provide POST method handler, that receives Json with ConferenceID / ChannelID fields.

For turning ChannelStatsDelaer on next settings are required:
1) `org.jitsi.videobridge.ChannelStatsDealer.ON=true`
2) `org.jitsi.videobridge.ChannelStatsDealer.ORIGIN=http://valid.rest.receiver:port/path`
3) `org.jitsi.videobridge.ChannelStatsDealer.ACCEPT_SELF_SIGNED=true` in case of self-signed https

Also add bundles.txt file (example you can find at config/bundles.txt) to `<HOME>/.jitsi-videobridge/` folder 
(this could be changed by `net.java.sip.communicator.SC_HOME_DIR_LOCATION`, 
`net.java.sip.communicator.SC_HOME_DIR_NAME` parameters).
