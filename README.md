# MoPub Android SDK for MFP Android App

Here's how to update and integrate this SDK into the MFP Android App.

- Set up your github fork with an upstream if necessary

  **[Set up your fork with an upstream](https://help.github.com/articles/syncing-a-fork)**

- Fetch and merge upstream every time it changes

```
	% git fetch upstream
	% git merge upstream/master
```

- Change pom.xml to reflect the new version number

```xml
	<properties>
		<mopub.sdk.version>1.17.2.0</mopub.sdk.version>
	</properties>
```

- Build and install into maven repo

```
	% mvn clean install
```

- Install into android app local repo

```
	% cd ../android-app/maven_repo_3rd_party
	% install.sh -f /your/.m2/repo/com/mopub/mobileads/mopub-sdk/<version>/mopub-sdk-<version>.jar -g com.mopub.mobileads -a mopub-sdk -v <version> -p jar
	% git add com/mopub/mobileads
	% git commit -a -m "update to version <version> of mopub"
	% git push origin <branchname>
```

- Change the version in app/pom.xml

```xml
    <dependency>
        <groupId>com.mopub.mobileads</groupId>
        <artifactId>mopub-sdk</artifactId>
        <version>VERSION</version>
        <exclusions>
            <exclusion>
                <groupId>com.google.android</groupId>
                <artifactId>support-v4</artifactId>
            </exclusion>
        </exclusions>
    </dependency>
```


# MoPub Android SDK

Thanks for taking a look at MoPub! We take pride in having an easy-to-use, flexible monetization solution that works across multiple platforms.

Sign up for an account at [http://app.mopub.com/](http://app.mopub.com/).

Help is available on the [wiki](https://github.com/mopub/mopub-android-sdk/wiki/Getting-Started).

## Download

The MoPub SDK is distributed as source code that you can include in your application.  MoPub provides two prepackaged archives of source code:

- **[MoPub Android Full SDK.zip](http://bit.ly/YUdU9v)**

  Includes everything you need to serve HTML and MRAID MoPub advertisiments *and* built-in support for Millennial Media third party ad network - [Millennial Media](http://www.millennialmedia.com/) - including the required third party binaries.

- **[MoPub Android Base SDK.zip](http://bit.ly/YUdWhH)**

  Includes everything you need to serve HTML and MRAID MoPub advertisements.  No third party ad networks are included.

## Integrate

Integration instructions are available on the [wiki](https://github.com/mopub/mopub-android-sdk/wiki/Getting-Started).


## New in this Version

Please view the [changelog](https://github.com/mopub/mopub-android-sdk/blob/master/CHANGELOG.md) for details.

  - **Bug Fixes**

## Requirements

Android 2.3.1 (API Version 9) and up

## License

We have launched a new license as of version 3.2.0. To view the full license, visit [http://www.mopub.com/legal/sdk-license-agreement/](http://www.mopub.com/legal/sdk-license-agreement/).
