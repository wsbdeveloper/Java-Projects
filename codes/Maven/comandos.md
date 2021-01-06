# Comandos utilizados nas aulas

## Configuração

Precisamos atualizar o path de execução do Maven

vi .bash_profile

```bash
export PATH:$PATH:dir_path_to_maven_bin
```

## Init com maven

Temos o Maven descompactado e instalado, e estamos prontos para criar um projeto. Com cd Documents/guilherme/workspace/ solicitaremos que o Maven gere um novo projeto, mas antes precisamos estipular sua estrutura básica ou arquétipo, portanto escreveremos:

Dentro do sistema operacional Windows, é preciso colocar _-DartifactId="produtos"_ em todos os valores.

_mvn archetype:generate_
Precisamos passar o nome ou ID do nosso projeto, que será produtos. Digitaremos -DartifactId=produtos para instaurar essa informação:

_mvn archetype:generate -DartifactId=produtos_
O próximo passo consiste em declararmos o pacote básico da empresa, já que produtos se refere ao projeto em si, isto é, apenas uma parte do pacote. Usaremos -DgroupId=br.com.alura.maven, pois estamos elaborando um curso sobre Maven na Alura.

Desabilitaremos o método interativo usando as informações padrão para configurarmos nosso projeto. Para isso, incluiremos -DinteractiveMode=false:

_mvn archetype:generate -DartifactId=produtos -DgroupId=br.com.alura.maven -DinteractiveMode=false_
No nosso caso, queremos um modelo simples e rápido, portanto buscaremos o ArchetypeArtifactId quickstart:
_mvn archetype:generate -DartifactId=produtos -DgroupId=br.com.alura.maven -DinteractiveMode=false -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4_

-DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart -DarchetypeVersion=1.4

## Relatórios via plugins

Para gerar um relatório em formato .html, utilizamos o plugin Surefire Report. O goal que utilizamos é o report:

_mvn surefire-report:report_

Gerando o jar do nosso projeto

_mvn package_

Para atualizações de Plugins

_mvn versions:use-latest-versions_

[goals](http://www.mojohaus.org/versions-maven-plugin/use-latest-versions-mojo.html)

Para evitar atualizações de dependencias, pode ser perigoso em alguns casos caso os testes não estejam mapeados para isto. Existe um goal para atualizar de fato sem alterar o pom.

_mvn versions:display-dependency-updates_

[documentação](http://www.mojohaus.org/versions-maven-plugin/)
