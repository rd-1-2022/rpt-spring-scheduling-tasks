# Overview

This project demonstrates Spring's scheduling functionality by scheduling a method to be executed every 5 seconds.

## Code

To enable scheduling support in Spring, the annotation `@EnableScheduling` should be placed on the main applicaiton class.

```java
@SpringBootApplication
@EnableScheduling
public class SchedulingTasksApplication {

    public static void main(String[] args) {
        SpringApplication.run(SchedulingTasksApplication.class);
    }
	
}
```

The method that is to be scheduled has the annotation `@Scheduled` with a time value for a fixed rate of executing the method 


```java
@Scheduled(fixedRate = 5000)
public void reportCurrentTime() {
    log.info("The time is now {}", dateFormat.format(new Date()));
}
```