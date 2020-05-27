How to run QARK exploit feature in docker container - https://hub.docker.com/r/ilyaglow/qark

Create in exploit build directory (/qark/exploit_apk/qark/):
```
nano local.properties
sdk.dir=/qark/android-sdk-linux/
```

install
```
apt install openjdk-7-jdk-headless
apt install lib32stdc++6 lib32z1
```

create
nano /root/.bashrc
JAVA_HOME="/usr/lib/jvm/java-7-openjdk-amd64/bin"
```
source /root/.bashrc
```

./gradlew assembleDebug

Choose required sdk and download it:
curl -s https://dl.google.com/android/android-sdk_r24.3.4-linux.tgz

```
./android update sdk -u -a -t 34,59,60
```

qark --exploit-apk --apk /apk/Application.apk


Along with other provided solutions, make sure to have the following within project/build.gradle
```
allprojects {
repositories {
jcenter()
maven {
url "https://maven.google.com"
}
}
}
```
