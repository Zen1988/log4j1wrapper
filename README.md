# log4j1wrapper
Log4j 1.x announced end of life at August 5, 2015, yet, a lot of enterprise application such as blue1, blue2, still make use of log4j 1 as their logging mechanism. While some of them allow to easy migration by replacing log4j bridge api and log4j2 jar files, some of them actually are programmatically called the log4j class. It's being become problem when there is requirement to upgrade to 2.x