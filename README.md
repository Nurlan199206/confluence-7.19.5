```Ubuntu 22.04.2 LTS```

1) ```PostgreSQL 15```
2) ```Java 17```
3) ```Confluence 7.19.5```


```apt update && apt install apt install openjdk-17-jre postgresql-15```

```sudo mkdir /opt/atlassian/atlassian-agent```
```sudo chown -R confluence:confluence /opt/atlassian/atlassian-agent```
```cp atlassian-agent.jar /opt/atlassian/atlassian-agent```
```add on the start the line /opt/atlassian/confluence/bin/setenv.sh```

```export JAVA_OPTS="-javaagent:/opt/atlassian/atlassian-agent/atlassian-agent.jar ${JAVA_OPTS}"```


```su - postgres```
```psql```
```create role confluence_user login superuser password '123';```
```create database confluence_db;```


```/opt/atlasian/confluence/bin/startup.sh```


take key from http://yourserver.com:8090 and put in the script



```java -jar /opt/atlassian/atlassian-agent/atlassian-agent.jar -mail 'my@email.com' -n userName -o CompanyName -p conf -s XXXX-XXXX-XXXX-XXXX```
