# Setup Java Environment

## Install Java

We need to first install the java jdk.

```bash
$ sudo apt install default-jdk
```

If you want to install some other version:

```bash
$ sudo apt install openjdk-8-jdk
```

You can choose which will be your current version.

```bash
$ java -version
openjdk version "11.0.22" 2024-01-16

$ sudo update-alternatives --config java
There are 2 choices for the alternative java (providing /usr/bin/java).

  Selection    Path                                            Priority   Status
------------------------------------------------------------
* 0            /usr/lib/jvm/java-11-openjdk-arm64/bin/java      1111      auto mode
  1            /usr/lib/jvm/java-11-openjdk-arm64/bin/java      1111      manual mode
  2            /usr/lib/jvm/java-8-openjdk-arm64/jre/bin/java   1081      manual mode

Press <enter> to keep the current choice[*], or type selection number: 2
update-alternatives: using /usr/lib/jvm/java-8-openjdk-arm64/jre/bin/java to provide /usr/bin/java (java) in manual mode

$ java -version
openjdk version "1.8.0_392"
```

## Install gradle

I do it with sdkman. So, first install sdkman.

```bash
$ sudo apt install zip unzip # A dependency of sdkman
$ curl -s "https://get.sdkman.io" | bash
```

Then, install gradle:
```bash
$ sdk install gradle 8.6
```

Reference: https://gradle.org/install/#with-a-package-manager

## Note
Add these lines to the ~/.extended file.

```bash
$ tail -2 ~/.extended
# For gradle
source "/home/ubuntu/.sdkman/bin/sdkman-init.sh"
```

## Install make

Also, please install `make` because, I still use Makefile as a slightly more manageable version of shell script.

```bash
$ sudo apt install make
```

## Install httpie

I also use httpie as a cleaner replacement of curl.

```bash
$ curl -SsL https://packages.httpie.io/deb/KEY.gpg | sudo gpg --dearmor -o /usr/share/keyrings/httpie.gpg
$ echo "deb [arch=amd64 signed-by=/usr/share/keyrings/httpie.gpg] https://packages.httpie.io/deb ./" | sudo tee /etc/apt/sources.list.d/httpie.list > /dev/null
$ sudo apt update
$ sudo apt install httpie
```

Reference: https://httpie.io/docs/cli/debian-and-ubuntu