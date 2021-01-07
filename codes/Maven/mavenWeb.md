# Trabalhando com Maven na Web

Para trabalhar com maven na web é preciso criar o projeto com o plugin do maven
dentro do eclipse é muito fácil a criação do projeto com padrão de web.

## Configurações

As configurações dentro do pom.xml são de muita importância primeiro vamos atualizar os plugins para configurar nosso servidor web.

```xml
 <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/maven-v4_0_0.xsd">
    <!-- informações sobre o projeto  -->
    <dependencies>
        <!-- junit -->
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>javax.servlet-api</artifactId>
            <version>3.1.0</version>
        </dependency>
    </dependencies>
    <!-- build -->
    <build>
        <finalName>lojaweb</finalName>
        <plugins>
            <plugin>
                <groupId>org.eclipse.jetty</groupId>
                <artifactId>jetty-maven-plugin</artifactId>
                <version>9.3.7.v20160115</version>
                <!-- Para excluir uma dependencia -->
                <exclusions>
                    <exclusion>
                        <groupId>com.thoughtworks.xstream</groupId>
                        <artifactId>xstream</artifactId>
                    </exclusion>
                </exclusions>
                <configuration>
                    <scanIntervalSeconds>10</scanIntervalSeconds>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
```

Após configurar o plugin, temos que atualizar o web.xml no path src/main/webapp/WEB-INF/. Não podemos deixar na versão 2.x que já está muito antiga e fica gerando erros. Vamos a configuração para a 3.0 em diante. As apis do servelet

```xml
<web-app xmlns="http://xmlns.jcp.org/xml/ns/javaee"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="http://xmlns.jcp.org/xml/ns/javaee
    http://xmlns.jcp.org/xml/ns/javaee/web-app_3_1.xsd"
    version="3.1">
</web-app>
```

Após as configurações execute

```bash
mvn jetty:run
```
