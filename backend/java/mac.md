# 설치(Mac)

자바 언어로 프로그램을 개발하기 위해서는 자바 개발 도구(JDK)가 필수적입니다. JDK(Java Development Kit)는 <mark style="color:blue;">**Java 언어로 소프트웨어를 개발하기 위한 도구 모음**</mark>입니다. JDK는 Java 개발자들이 Java 프로그램을 작성하고, 컴파일하고, 디버그하며, 배포할 수 있는 필수 도구를 제공합니다.





&#x20;MacOS에서 자바 프로그램을 개발할 수 있는 환경을 구성해보겠습니다.&#x20;

```sh
# Homebrew 설치
jongseungMac > /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# adoptopenjdk/openjdk 추가
jongseungMac > brew tap adoptopenjdk/openjdk

# 설치 가능한 모든 JDK 찾기
jongseungMac > brew search jdk

# 원하는 버전 설치
jongseungMac > brew install --cask adoptopenjdk8
jongseungMac > brew install --cask adoptopenjdk12

# 자바 설치 경로
jongseungMac > /usr/libexec/java_home -V

# 자바 버전 확인
jongseungMac > java --version
```





JDK를 설치한 후 환경 변수를 설정합니다. 그 이유는 Java 애플리케이션을 실행하기 위해 필요한 경로와 같은 정보를 컴퓨터가 인식할 수 있도록 하기 위함입니다. Java 애플리케이션을 실행하려면, 컴퓨터가 JDK 설치 위치와 같은 정보를 알아야 합니다. 환경 변수를 설정하면 이러한 정보를 저장하고, Java 애플리케이션이 이 정보를 사용할 수 있도록 합니다.



일반적으로, JDK 설치 프로그램은 PATH 환경 변수를 설정하는 선택을 제공합니다. <mark style="color:blue;">**PATH 환경 변수는 컴퓨터가 실행 파일을 찾는 데 사용하는 경로를 저장**</mark>합니다. 따라서 PATH 환경 변수를 설정하면 Java 실행 파일이 저장된 디렉토리를 지정할 수 있습니다. 환경 변수를 설정하지 않으면 Java 애플리케이션을 실행할 때마다 JDK 설치 위치를 수동으로 지정해야 합니다. 이는 귀찮은 작업이며, Java 애플리케이션을 실행할 때마다 같은 작업을 반복해야 합니다. 따라서, 환경 변수를 설정하는 것이 편리하고 효율적입니다.





컴퓨터의 기본 콘솔이 zsh일 경우, 환경 변수를 설정하는 방법은 다음과 같습니다.

```sh
# 현재 사용하고 있는 쉘
jongseungMac > echo $SHELL

# 쉘의 환경 변수가 저장된 파일 수정
jongseungMac > vi ~/.zshrc

--------------------------------------------------------------------
# Java Paths
export JAVA_HOME_8=$(/usr/libexec/java_home -v8)
export JAVA_HOME_12=$(/usr/libexec/java_home -v12)

# Java 8
export JAVA_HOME=$JAVA_HOME_8

# Java 12
# 12버전을 사용하고자 하는 경우 아래 주석(#)을 해제하고 위에 8버전을 주석처리 하면된다.
# export JAVA_HOME=$JAVA_HOME_12

:wq
--------------------------------------------------------------------

# 변경 사항 저장
jongseungMac > source ~/.zshrc
```

