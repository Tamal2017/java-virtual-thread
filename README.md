## Simple demo app to test Java virtual thread with Spring
### There are two small app; 
- The first one is _vt-blocker_ a blocking spring web using Thread.sleep();
- The second is _vt-main_ the entering point of our test, calling the _vt-blocker_ blocking app using RestTemplate.

We will use application.properties to configure the main app enabled virtual thread or linite le number of thread within the Tomcat server (refer to line 4 and 7 ). You can comment or uncomment the config you want to test
Use the end point _http://localhost:8080/block/3_ (where 3 is the number of second you want to block a request) of main app to run the test.
You can use Apache Benchmark to run many resquests in parall. For Windows user refer to this website [apachelounge](https://www.apachelounge.com/download/#google_vignette) to download a zip version for Windows.

Example:
>ab -k -c 20 -n 60 http://localhost:8080/block/3
- _ab apache benchmark command_
- _-c concurrency : Number of multiple requests to make at a time_
- _-n requests : Number of requests to perform_
- _-k Use HTTP KeepAlive feature_
