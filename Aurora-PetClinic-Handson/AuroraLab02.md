# Session Manager를 이용해서 EC2 인스턴스에 접속

1. 다음의 주소를 복사해서 Browser의 새 창에 Copy and Paste합니다.

`https://ap-northeast-2.console.aws.amazon.com/systems-manager/session-manager?region=ap-northeast-2`

2. "Start Session"을 Click

<kbd> ![GitHub Logo](images/6.png) </kbd>

3. `auroralab-mysql-workstation`을 선택한 후 "Start Session"을 Click

<kbd> ![GitHub Logo](images/7.png) </kbd>

4. Terminal 이 뜨면 `sudo su -l ubuntu`를 통해 ssm-user에서 ubuntu User로 Switching.(항상 ubuntu User로 작업을 해야 합니다.)

<kbd> ![GitHub Logo](images/8.png) </kbd>

5. `tail -n1 /debug.log`를 확인하여 다음의 Log가 있는지 확인

`* bootstrap complete, rebooting`

6. mysql client를 사용해서 aurora instance로 접속을 확인합니다. [clusterEndpoint]는 Lab01에서 복사해둔 CloudFormation Output에서 확인 할 수 있습니다.

`mysql -h[clusterEndpoint] -u$DBUSER -p"$DBPASS" -e"SELECT @@aurora_version;"`

**COMMAND & Output Example**

<kbd> ![GitHub Logo](images/9.png) </kbd>

7. Install JDK 11

```
ubuntu@ip-172-31-0-217:~$ sudo apt-get install openjdk-11-jdk -y
```

8. petclinic git repository를 clone 합니다.

```
ubuntu@ip-172-31-0-217:~$ git clone https://github.com/kiwonyoon0701/spring-petclinic.git
ubuntu@ip-172-31-0-217:~$ wget https://shared-kiwony.s3.ap-northeast-2.amazonaws.com/m2.tar.Z
ubuntu@ip-172-31-0-217:~$ tar xvfz m2.tar.Z
ubuntu@ip-172-31-0-217:~$ cd spring-petclinic/
ubuntu@ip-172-31-0-217:~/spring-petclinic$ ./mvnw package -Dmaven.test.skip=true
```

9. EC2의 Public IP 를 확인하고, PetClinic application을 실행 후 접속 테스트를 진행합니다.

```
ubuntu@ip-172-31-0-145:~/spring-petclinic$ curl -s ifconfig.me | awk ' { print $1 "\n" }'
52.79.61.11
ubuntu@ip-172-31-0-145:~/spring-petclinic$ java -jar target/*.jar

```

10. Browser에서 http://EC2-PublicIP:8080 으로 접속합니다.
    <kbd> ![GitHub Logo](images/10.png) </kbd>

**앞으로 있을 Terminal 작업은 모두 위의 Session Manager 접속을 통해서 이뤄집니다.**
**Session Manager가 Timeout되서 Close될 경우 위의 순서로 다시 여시면 됩니다.**

9. 수고하셨습니다. 다음 챕터로 이동하세요. [AuroraLab03.md](AuroraLab03.md)
