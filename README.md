# First-Plugin
Our first plugin made together!

### File Hierarchy

This is common file hierarchy for Maven projects.

* src/
  * main/
    * java/ - Contains all classes and packages (ie org.bukkit.plugin.java.JavaPlugin.class).
    * resources/ - Contains plugin resources (ie plugin.yml, config.yml).
* LICENSE - The legal statement of the repository.
* pom.xml - Maven information file formatted in XML.
* README.md - Repository information file formatted in Markdown.

### Maven Configuration

These are the primary tags we will be using in our projects' pom.xml files

```
    <groupId>BinaryBanana</groupId>

    <dependencies>
        <dependency>
            <groupId>org.bukkit</groupId>
            <artifactId>craftbukkit</artifactId>
            <version>1.8.7</version>
            <scope>system</scope>
            <systemPath>${project.basedir}/../API/craftbukkit-1.8.7.jar</systemPath>
            <!-- This is only the location of MY craftbukkit.jar. Change it to match the location of your craftbukkit.jar library of the specified version. -->
        </dependency>
    </dependencies>

    <build>
        <defaultGoal>package install</defaultGoal>
        <directory>${project.basedir}/../BUILDS/${project.artifactId}</directory>
        <!-- This is only the location of MY build directory. Change it to match the location you would like to export the compiled JAR. -->

        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>
                <version>2.6</version>

                <configuration>
                    <archive>
                        <addMavenDescriptor>false</addMavenDescriptor>

                        <manifestEntries>
                            <Built-By>Binary Banana's Java Class</Built-By>
                        </manifestEntries>
                    </archive>
                </configuration>
            </plugin>
        </plugins>
    </build>
```
