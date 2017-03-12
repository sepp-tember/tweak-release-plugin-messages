## About

The Maven release plugin starts by default all commit messages with lower case letters. Using this artifact as dependency for the release
plugin overwrites the default messages with ones starting with upper case letters.

The release plugin uses plexus container configuration to load its release phases and commit messages. This project contains an 
alternative configuration to replace the commit messages with new ones that start with upper case letters. Following the list of 
messages, where `{0}` will be replaced with release tag name:

<dl>
	<dt>Release phase</dt>
		<dd>Prepare release {0}</dd>
	<dt>Commit development phase</dt>
		<dd>Prepare for next development iteration</dd>
		<dd>Rollback changes from release preparation of {0}</dd>
	<dt>Commit branch phase</dt>
		<dd>Prepare branch {0}</dd>
	<dt>Commit rollback phase</dt>
		<dd>Rollback the release of {0}</dd>
</dl>

### Usage

To replace the commit messages this artifact has to be configured as dependency for the Maven release plugin in the projects pom file 
like this:

	<?xml version="1.0" encoding="UTF-8"?>
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
	</project>
