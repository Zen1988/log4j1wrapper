# log4j1wrapper
Log4j 1.x announced end of life at August 5, 2015, yet, a lot of enterprise application such as blue1, blue2, still make use of log4j 1 as their logging mechanism. While some of them allow to easy migration by replacing with log4j bridge api (log4j-1.2-api-2.xx.xx.jar) and log4j2 jar files, some of them actually are programmatically called the log4j class, which then impossible unless they willing to release new version.

The idea of wrapper jar is to create a Java class, using the same package name, and class name, e.g. org.apache.log4j.RollingFileAppender, while method interfaces either being invalidate (return null/set nothing), or being redirect to create a new org.apache.logging.log4j.core.appender.RollingFileAppender. 

Implementation Step:
1) Put wrapper-log4j-1.2-api-2.x-1.0.jar together with log4j-1.2-api-2.xx.xx.jar, log4j-api-2.xx.xx.jar, log4j-core-2.xx.xx.jar under classpath.
2) Besure wrapper-log4j-1.2-api-2.x-1.0.jar is configured to be called first before other jar file. 
3) Make sure any hardcoded classpath to call old log4j jar is being reconfigured to recognize all jar. 
4) Restart java application. 

Current Scope:
1) Cover only RollingFileAppender
