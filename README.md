# StatsD Auto-Configuration

Easy to use Statsd with Spring, no configuration necessary.
Out of the box metrics, by enabling statsd you also got every metric generated by Spring actuator `/metrics` endpoint [[docs]](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-metrics.html)

# Usage

## Maven

```
<dependency>
    <groupId>com.github.cristianoperez</groupId>
    <artifactId>statsd-autoconfiguration</artifactId>
    <version>1.0.1</version>
</dependency>
```

## Gradle
`compile 'com.github.cristianoperez:statsd-autoconfiguration:1.0.1'`

## Sample
```
@Autowired
private StatsDClient statsdClient;
	
public void login() {
	//some logic
	statsdClient.increment("login.success");
	//more logic
}
```
Will generate `metrics.login.success:1|c`


# Properties

application.properties
```
spring.statsd.enable=true/false (Enable/Disable statsd configuration, if disabled will log every call as debug. Default: true)
spring.statsd.metrics=true/false (Enable/Disable metrics generation. Default: true)
spring.statsd.prefix="" (Metric prefix. Default: metrics)
spring.statsd.host="" (StatsD host. Default: localhost)
spring.statsd.port="" (Statsd port. Default: 8125)
``` 

# Metrics

Out of the box every metric generated by Spring actuator `/metrics` endpoint [[docs]](https://docs.spring.io/spring-boot/docs/current/reference/html/production-ready-metrics.html#production-ready-metrics)

Some metrics exposed by Actuator
```

metrics.instance.uptime:5327|g
metrics.uptime:6624|g
metrics.systemload.average:0|g
metrics.systemload.average:-1|g
metrics.heap.committed:251392|g
metrics.heap.init:262144|g
metrics.heap.used:44270|g
metrics.heap:3712000|g
metrics.nonheap.committed:28352|g
metrics.nonheap.init:2496|g
metrics.nonheap.used:27501|g
metrics.nonheap:0|g
metrics.threads.peak:24|g
metrics.threads.daemon:18|g
metrics.threads.totalStarted:34|g
metrics.threads:20|g
metrics.classes:3996|g
metrics.classes.loaded:3996|g
metrics.classes.unloaded:0|g
metrics.gc.ps_scavenge.count:2|g
metrics.gc.ps_scavenge.time:17|g
metrics.gc.ps_marksweep.count:0|g
metrics.gc.ps_marksweep.time:0|g
metrics.mem:279030|g
metrics.mem.free:201464|g
metrics.processors:8|g
metrics.instance.uptime:10344|g
metrics.uptime:11642|g
metrics.systemload.average:0|g
metrics.systemload.average:-1|g
metrics.heap.committed:251392|g
metrics.heap.init:262144|g
metrics.heap.used:49927|g
metrics.heap:3712000|g
metrics.nonheap.committed:28672|g
metrics.nonheap.init:2496|g
metrics.nonheap.used:27638|g
metrics.nonheap:0|g
metrics.threads.peak:24|g
metrics.threads.daemon:19|g
metrics.threads.totalStarted:42|g
metrics.threads:21|g
metrics.classes:4006|g
metrics.classes.loaded:4006|g
metrics.classes.unloaded:0|g
metrics.gc.ps_scavenge.count:2|g
metrics.gc.ps_scavenge.time:17|g
metrics.gc.ps_marksweep.count:0|g
metrics.gc.ps_marksweep.time:0|g
metrics.mem:279101|g
metrics.mem.free:196278|g
metrics.processors:8|g
```
