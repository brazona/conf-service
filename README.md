# Config Server Service

Esse aplicativo tem a função de centralizar o fornecimento de informações de configuração das aplicações, possibilitando classificar os arquivos em perfils, assim entregando as configurações especifica de cada ambiente.

## Versões

__[relação das versões de aplicativos externos: ]__ A aplicação utiliza as seguintes versões:

| Software | Versão |
| --- | --- |
| JDK | 21.0.2 |
| Maven | 3.9.3 |
| Docker | 27.5.1|
| Docker Compose | 2.32.4|

## Estrutura do projeto

``` text

├── .github
│   └── workflows
│       └── script
│               └── manifest.sh
│           └── conf-service.yml
│           └── ng-update.yml
│           └── rules.yml
│       └── dependabot.yml
├── app
│   └── src
├── docs
│   └── CONTRIBUTING.md
│   └── CODE_OF_CONDUCT.md
│   └── PULL_REQUEST_TEMPLATE.md
└── README.md
```

## Fluxo de Trabalho - Deploy Ambientes

O fluxo de trabalho são processos definidos para dar direção a etapa de desenvolvimento , homologação e lançamento.

As alterações são aplicadas em determinado ambiente através das **branchs**, ao publicar uma alteração numa das branchs ***principais*** o pipeline executa a atualização, a tabela abaixo descreve a relação entre branch e o respectivo ambiente:

### Tabela Branch x Ambiente

| Branch | Ambiente |
| --- | --- |
| develop | Aplica no ambiente __DSV__ |
| release/** | Aplica no ambiente __HMG__ |
| pre-release/** | Aplica no ambiente __STG__ |
| main | Aplica no ambiente __PRD__ |

## Sobre a Aplicação

Esta aplicação foi desenvolvida utilizando a linguaguem [java](https://www.java.com/pt-BR/) e o framework [spring Boot](https://docs.spring.io/spring-boot/index.html)

## Build com docker compose

Para atender a necessidade de executar a os servidore em ambiente local, foi criado um manifesto compose que inicia as configurações iniciais dos servidores, proporcionando os recursos da arquitetura em ambiente **localhost.**

Para executar essa instrução basta abrir o terminal shell, e executar com exemplo abaixo:

``` sh
cd app &&
mvn clean install &&
docker compose --env-file .env up -d --build --force-recreate
```

## Licença

> [!IMPORTANT]
> *O código fonte neste projeto não possui licença de uso.*

É terminantemente proibido reproduzir, distribuir, alterar, utilizar engenharia reversa ou valer-se de qualquer tentativa de reverter ao seu código-fonte qualquer dos componentes que compõem o SOFTWARE, bem como utilizar subterfúgios para burlar a quantidade de usuários licenciados.
