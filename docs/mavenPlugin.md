## Jube Maven Plugin

This maven plugin makes it easy to create [Image Zips](imageZips.html) as part of your maven project. 

Jube tries to [reuse as much of the metadata](goals.html) for building docker images as possible to have minimal impact on your pom.xml files.

### Adding the plugin to your project

To enable this maven plugin and to automatically generate an [Image Zip](imageZips.html) as part of your build

      <plugin>
        <groupId>org.jboss.jube</groupId>
        <artifactId>jube-maven-plugin</artifactId>
        <version>${jube.version}</version>
        <executions>
          <execution>
            <goals>
              <goal>build</goal>
            </goals>
            <phase>package</phase>
          </execution>
        </executions>
      </plugin>

### Building your image zip

To generate an [Image Zip](imageZips.html) just type:

    mvn install jube:build

The image zip will be installed into the local maven repository.

#### Properties for configuring the generation

You can use maven properties to customize the generation of the JSON:

<table class="table table-striped">
<tr>
<th>Parameter</th>
<th>Description</th>
</tr>
<tr>
<td>docker.baseImage</td>
<td>The name of the base docker image used to generate the new image zip.</td>
</tr>
<tr>
<td>docker.dataImage</td>
<td>The name of the image to generate.</td>
</tr>
</table>
