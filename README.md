# 프로젝트 소개
[spring-guides](https://spring.io/guides/gs/scheduling-tasks)를 학습한 프로젝트 입니다.


# 배운 내용 

## Enable Scheduling
@EnableScheduling을 이용하면 spring의 scheduled task를 이용할 수 있다.
~~~ java
@SpringBootApplication
@EnableScheduling
public class SchedulingTasksApplication {
~~~


## create Scheduled Task

주기적인 작업을 위해서 fixedRate(), cron(), fixedDelay()가 있습니다. 선택적으로 한번만 실행되는 경우 initialDelay()을 사용해도 됩니다.

~~~ java
@Component
public class ScheduledTasks {

	private static final Logger log = LoggerFactory.getLogger(ScheduledTasks.class);

	private static final SimpleDateFormat dateFormat = new SimpleDateFormat("HH:mm:ss");

	@Scheduled(fixedRate = 5000)
	public void reportCurrentTime() {
		log.info("The time is now {}", dateFormat.format(new Date()));
	}
}
~~~
