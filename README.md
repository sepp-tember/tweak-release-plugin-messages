# tweak-release-plugin-messages

## Info

The Maven release plugin starts by default all commit messages with lower case letters. Using this artifact as dependency for the release
plugin overwrites the default messages with ones starting with upper case letters.

The release plugin uses plexus container configuration to load its release phases and commit messages. This project contains an 
alternative configuration to replace the commit messages with new ones that start with upper case letters.

## Retrieval

Artifacts of this project can be retrieved from a maven repository located at
[http://maven.sepp-tember.net/releases/](http://maven.sepp-tember.net/releases/). So to use it in a maven project, the repository has to 
be configured in the pom file (see [example below](#usage)).

## Usage

To replace the commit messages this artifact has to be configured as dependency for the Maven release plugin in the projects pom file 
like this:

```xml
	<project xmlns="http://maven.apache.org/POM/4.0.0"
			xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
			xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
		<modelVersion>4.0.0</modelVersion>
		...
		<build>
			<plugins>
				<plugin>
					<groupId>org.apache.maven.plugins</groupId>
					<artifactId>maven-release-plugin</artifactId>
					<version>2.5.3</version>
					<dependencies>
						<dependency>
							<groupId>net.sepp-tember.maven</groupId>
							<artifactId>tweak-release-plugin-messages</artifactId>
							<version>1.0.0</version>
						</dependency>
					</dependencies>
				</plugin>
			</plugins>
		</build>
		...
		<pluginRepositories>
			<pluginRepository>
				<releases>
					<enabled>true</enabled>
				</releases>
				<id>sepp-tember-snapshots</id>
				<url>http://maven.sepp-tember.net/releases/</url>
			</pluginRepository>
		</pluginRepositories>
		...
	</project>
```

## Project Website

The project website is located at http://dev.sepp-tember.net/tweak-release-plugin-messages/
