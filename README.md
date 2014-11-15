One MDM Client
==============

One MDM Client is the android application to run on the client device to communicate with the [One MDM](https://github.com/multunus/one-mdm/) Server.

## How to set up One MDM Client?

### Prerequisites

* Java Development Kit
* Android SDK Tools
* Android 4.3 APIs (API Level 18)

Clone the One MDM Client repo:

``` bash
git clone https://github.com/multunus/one-mdm-client.git
```

Go to the one-mdm-client directory and copy the file `Config.java.template` to `Config.java` in the package:

``` bash
cd one-mdm-client
cp src/main/java/com/multunus/one_mdm_client/Config.java.template src/main/java/com/multunus/one_mdm_client/Config.java
```

Set the constant `SERVER` to point to the hosted One MDM Server. Also configure the `BUGSNAG_API_KEY` for error reporting:

``` java
public static final String SERVER = <Server URL>;
public static final String BUGSNAG_API_KEY = <Bugsnag API Key>;
```

Build the project from the command line:

``` bash
./gradlew clean build
```

### Configurations

Currently, you can configure the following options in `Config.java`:

* `SERVER` - Root URL to the One MDM Server (For example: `http://onemdm.herokuapp.com`)
* `HEARTBEAT_INTERVAL` - Interval at which the device sends heartbeat to the server to say that 'I am alive!'. Heartbeat interval value is given in seconds.
* `BUGSNAG_API_KEY` - Bugsnag API key for sending error reports when it happens. To know more about Bugsnag, [see here](https://bugsnag.com/).
* `SCRIPT_POLLING_INTERVAL` - Interval at which the client polls to the server to check if any new scripts are available for execution.

### Installation and Running

You can install the application in an android device after building it. Once it is installed and started, the device gets registered in the server automatically. It also starts sending heartbeats at the given interval. It shows a notification on the device indicating that the One MDM service is running in the background. 

If the device is not connected to the internet at the time of starting, the registration will not happen. The device will show a message to the user and will exit.

## How to contribute to One MDM?

One MDM is still under construction! It is purely an open source project. If you find any bugs, you can help us by raising issues in Github. You can also contribute to the project by sending pull requests.