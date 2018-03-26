---
title: Определение многоконтейнерного приложения с помощью docker-compose.yml
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Определение многоконтейнерного приложения с помощью docker-compose.yml
keywords: Docker, микрослужбы, ASP.NET, контейнер
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4fed5c7ba5c2048d103f22bd2b463c143013280
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Определение многоконтейнерного приложения с помощью docker-compose.yml 

В данном руководстве файл [docker-compose.yml](https://docs.docker.com/compose/compose-file/) был представлен в разделе [Шаг 4. Определение служб в файле docker-compose.yml при сборке многоконтейнерного приложения Docker](#step4_define_svcs_in_docker_compose_yml). Тем не менее существуют дополнительные способы использования файлов docker-compose, которые стоит изучить более подробно.

Например, в файле docker-compose.yml вы можете явно описать, как следует развертывать ваше многоконтейнерное приложение. При необходимости также можно описать, как вы планируете собирать свои пользовательские образы Docker. (Пользовательские образы Docker можно также собрать с помощью Docker CLI.)

В сущности, вы определяете каждый из контейнеров, которые планируете развернуть, и конкретные характеристики для каждого развертывания контейнера. Создав файл описания многоконтейнерного развертывания, вы можете развернуть все решение в одном действии, управляемом командой CLI [docker-compose up](https://docs.docker.com/compose/overview/), или развернуть решение прозрачно из Visual Studio. В противном случае придется использовать Docker CLI, чтобы разворачивать контейнер за контейнером в несколько этапов с помощью команды docker run из командной строки. Таким образом, для каждой службы, определенной в файле docker-compose.yml, необходимо указать ровно один образ или сборку. Остальные ключи являются необязательными и соответствуют своим аналогам в командной строке docker run.

В следующем примере кода YAML представлено определение возможно глобального, но единственного файла docker-compose.yml для примера eShopOnContainers. Это ненастоящий файл docker-compose из eShopOnContainers. Это упрощенная и объединенная в один файл версия, представляющая не лучший способ работы с файлами docker-compose, как будет показано ниже.

```yml
version: '2'

services:
  webmvc:
    image: eshop/webmvc
    environment:
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
    ports:
      - "5100:80"
    depends_on:
      - catalog.api
      - ordering.api
      - basket.api

  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=sql.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    environment:
      - ConnectionString=Server=sql.data;Database=Services.OrderingDb;User Id=sa;Password=your@password
    ports:
      - "5102:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data

  basket.api:
    image: eshop/basket.api
    environment:
      - ConnectionString=sql.data
    ports:
      - "5103:80"
    depends_on:
      - sql.data

  sql.data:
    environment:
      - SA_PASSWORD=your@password
      - ACCEPT_EULA=Y
    ports:
      - "5434:1433"

  basket.data:
    image: redis
```

Корневой ключ в этом файле — services. Под этим ключом определяются службы, которые требуется развернуть и запустить при выполнении команды docker-compose или при развертывании из Visual Studio с помощью этого файла docker-compose.yml. В данном случае в файле docker-compose.yml определено несколько служб, как показано в следующем списке.

-   webmvc — контейнер, включающий приложение MVC ASP.NET Core и использующий микрослужбы из C\# на стороне сервера.

-   catalog.api — контейнер, включающий микрослужбу Catalog веб-API ASP.NET Core.

-   ordering.api — контейнер, включающий микрослужбу Ordering веб-API ASP.NET Core.

-   sql.data — контейнер, запускающий SQL Server для Linux, в котором содержатся базы данных микрослужб.

-   basket.api — контейнер с микрослужбой Basket веб-API ASP.NET.

-   basket.data — контейнер, запускающий службу кэша REDIS, с базой данных basket в качестве кэша REDIS.

### <a name="a-simple-web-service-api-container"></a>Простой контейнер API веб-службы

Рассмотрим один контейнер. Контейнер-микрослужба catalog.api имеет простое определение:

```yml
  catalog.api:
    image: eshop/catalog.api
    environment:
      - ConnectionString=Server=catalog.data;Initial Catalog=CatalogData;User Id=sa;Password=your@password
    expose:
      - "80"
    ports:
      - "5101:80"
    #extra hosts can be used for standalone SQL Server or services at the dev PC
    extra_hosts:
      - "CESARDLSURFBOOK:10.0.75.1"
    depends_on:
      - sql.data
```

Эта контейнерная служба имеет следующую базовую конфигурацию.

-   Она основывается на пользовательском образе eshop/catalog.api. Проще говоря, в файле не задан ключ build:. Это означает, что образ должен быть предварительно создан (с помощью команды docker build) или загружен (с помощью команды docker pull) из любого реестра Docker.

-   Она определяет переменную среды с именем ConnectionString со строкой подключения, которая должна использоваться Entity Framework для доступа к экземпляру SQL Server, содержащему модель данных каталога. В данном случае в одном контейнере SQL Server содержатся несколько баз данных. Поэтому на компьютере разработки потребуется меньше памяти для Docker. Однако можно было бы также развернуть по одному контейнеру SQL Server для каждой базы данных микрослужбы.

-   Имя SQL Server — sql.data; это же имя используется для контейнера, в котором выполняется экземпляр SQL Server для Linux. Это удобно; благодаря этой возможности служба разрешения имен (внутренняя для узла Docker) будет разрешать сетевой адрес, так что вам не нужно знать внутренний IP-адрес для контейнеров при доступе к ним из других контейнеров.

Так как строка подключения определяется переменной среды, можно задавать эту переменную посредством другого механизма и в другое время. Например, можно задать другую строку подключения при развертывании в рабочей среде на финальных узлах или сделать это из конвейеров CI/CD в VSTS или в другой предпочитаемой системе DevOps.

-   Она представляет порт 80 для внутреннего доступа к службе catalog.api в узле Docker. В данном случае этот узел является виртуальной машиной Linux, так как он основан на образе Docker для Linux, но можно настроить контейнер для запуска в образе Windows.

-   Она переадресует предоставленный порт 80 в порт 5101 на хост-компьютере Docker (виртуальной машине Linux).

-   Она связывает веб-службу со службой sql.data (экземпляром SQL Server для базы данных Linux, запущенным в контейнере). Если вы указываете эту зависимость, контейнер catalog.api не будет запускаться до запуска контейнера sql.data. Это важно, поскольку для catalog.api требуется уже запущенная база данных SQL Server. Тем не менее во многих случаях недостаточно использовать этот вид зависимости контейнера, так как Docker выполняет проверку только на уровне контейнера. Иногда служба (в данном случае SQL Server) может быть еще не готова, поэтому рекомендуется реализовать в клиентских микрослужбах логику повторов с экспоненциальным отходом. Таким образом, если контейнер зависимостей будет не готов в течение некоторого времени, приложение по-прежнему будет устойчивым.

-   Она настроена для разрешения доступа к внешним серверам: параметр extra\_hosts позволяет получать доступ к внешним серверам или компьютерам за пределами узла Docker (то есть за пределами виртуальной машины Linux по умолчанию, которая является узлом разработки Docker), таким как локальный экземпляр SQL Server на компьютере разработки.

В файле docker-compose.yml также имеются другие, более сложные параметры, которые рассматриваются в следующих разделах.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>Использование файлов docker-compose для нескольких сред

Файлы docker-compose.yml являются файлами определения и могут использоваться несколькими инфраструктурами, которые распознают этот формат. Самый простой инструмент — это команда docker-compose, но с этим файлом могут работать и другие инструменты, такие как оркестраторы (например, Docker Swarm).

Таким образом, используя команду docker-compose, вы можете реализовать следующие основные сценарии.

#### <a name="development-environments"></a>Среды разработки

При разработке приложений важно иметь возможность запускать приложение в изолированной среде разработки. Можно создать такую среду с помощью команды CLI docker-compose или использовать Visual Studio, в котором команда docker-compose применяется внутренним образом.

Файл docker-compose.yml позволяет настраивать и документировать все зависимости служб вашего приложения (другие службы, кэш, базы данных, очереди и т. п.). С помощью команды CLI docker-compose вы можете создавать и запускать один или несколько контейнеров для каждой зависимости одной командой (docker-compose up).

Файлы docker-compose.yml — это файлы конфигурации, интерпретированные подсистемой Docker, но они также служат в качестве удобных файлов документирования сведений о составе вашего многоконтейнерного приложения.

#### <a name="testing-environments"></a>Тестовые среды

Важной частью любого процесса непрерывного развертывания (CD) или непрерывной интеграции (CI) являются модульные тесты и интеграционные тесты. Для этих автоматических тестов требуется изолированная среда, чтобы на них не влияли пользователи или какие-либо изменения данных в приложении.

Используя Docker Compose, можно очень просто создавать и уничтожать такую изолированную среду с помощью нескольких команд, выполненных в командной строке, или скриптов; например, с помощью следующих команд:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>Рабочие развертывания

Команду Compose можно также использовать для развертывания в удаленной подсистеме Docker. Типичный случай — развертывание на один экземпляр узла Docker (такой как рабочая виртуальная машина или сервер с установленной [машиной Docker](https://docs.docker.com/machine/overview/)). Но это также может быть весь кластер [Docker Swarm](https://docs.docker.com/swarm/overview/), поскольку кластеры тоже совместимы с файлами docker-compose.yml.

При использовании любых других оркестраторов (Azure Service Fabric, Mesos DC/OS, Kubernetes и т. п.) может потребоваться добавить параметры настройки и конфигурации метаданных, аналогичные имеющимся в файле docker-compose.yml, но в формате, необходимом для этого другого оркестратора.

В любом случае docker-compose является удобным инструментом и форматом метаданных для рабочих процессов развертывания, тестирования и работы, хотя рабочий процесс работы может отличаться в зависимости от используемого оркестратора.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>Использование нескольких файлов docker-compose для обработки разных сред

Если планируются разные среды, необходимо использовать несколько файлов compose. Это позволяет создать несколько вариантов конфигурации в зависимости от среды.

#### <a name="overriding-the-base-docker-compose-file"></a>Переопределение базового файла docker-compose

Вы можете использовать единственный файл docker-compose.yml, как показано в упрощенных примерах, приведенных в предыдущих разделах. Однако для большинства приложений это не рекомендуется.

По умолчанию Compose читает два файла, docker-compose.yml и дополнительный файл docker-compose.override.yml. Как показано на рисунке 8-11, если вы работаете в Visual Studio и включаете поддержку Docker, Visual Studio при этом создает дополнительный файл docker-compose.ci.build.yml для использования из конвейеров CI/CD, как в VSTS.

![](./media/image12.png)

**Рис. 8-11**. Файлы docker-compose в Visual Studio 2017

Файлы docker-compose можно изменить в любом редакторе, например в Visual Studio Code или Sublime, и запустить приложение с помощью команды docker-compose up.

По определению файл docker-compose.yml содержит базовую конфигурацию и другие статические параметры. Это означает, что конфигурация службы не должна изменяться в зависимости от целевой среды развертывания.

Файл docker-compose.override.yml, как следует из его имени, содержит параметры конфигурации, которые переопределяют базовую конфигурацию, например конфигурацию, зависящую от среды развертывания. У вас может быть несколько файлов переопределения с разными именами. Файлы переопределения обычно содержат дополнительные сведения, необходимые для приложения, но относящиеся к конкретной среде или развертыванию.

#### <a name="targeting-multiple-environments"></a>Планирование нескольких сред

Распространенный вариант использования заключается в том, что определяется несколько файлов compose, чтобы можно было планировать несколько сред, таких как рабочая среда, промежуточная среда, среда CI или среда разработки. Для поддержки этих разных сред можно разделить конфигурацию Compose на несколько файлов, как показано на рисунке 8-12.

![](./media/image13.png)

**Рис. 8-12**. Несколько файлов docker-compose, переопределяющих значения в базовом файле docker-compose.yml

Вы начинаете с базового файла docker-compose.yml. Этот базовый файл должен содержать базовые или статические параметры конфигурации, которые не изменяются в зависимости от среды. Например, eShopOnContainers имеет в качестве базового файла следующий файл docker-compose.yml.

```yml
#docker-compose.yml (Base)
version: '3'
services:
  basket.api:
    image: eshop/basket.api:${TAG:-latest}
    build:
      context: ./src/Services/Basket/Basket.API
      dockerfile: Dockerfile    
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api:${TAG:-latest}
    build:
      context: ./src/Services/Catalog/Catalog.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - rabbitmq

  marketing.api:
    image: eshop/marketing.api:${TAG:-latest}
    build:
      context: ./src/Services/Marketing/Marketing.API
      dockerfile: Dockerfile    
    depends_on:
      - sql.data
      - nosql.data
      - identity.api
      - rabbitmq

  webmvc:
    image: eshop/webmvc:${TAG:-latest}
    build:
      context: ./src/Web/WebMVC
      dockerfile: Dockerfile    
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api
      - marketing.api

  sql.data:
    image: microsoft/mssql-server-linux:2017-latest

  nosql.data:
    image: mongo

  basket.data:
    image: redis
      
  rabbitmq:
    image: rabbitmq:3-management

```

Значения в базовом файле docker-compose.yml не должны изменяться из-за разных целевых сред развертывания.

Если рассмотреть, например, определение службы webmvc, то можно увидеть, что эта информация большей частью одинакова независимо от планируемой среды. В этом определении содержится следующая информация.

-   Имя службы: webmvc.

-   Пользовательский образ контейнера: eshop/webmvc.

-   Команда для создания пользовательского образа Docker, указывающая, какой Dockerfile следует использовать.

-   Зависимости от других служб, чтобы данный контейнер не запускался до запуска других контейнеров зависимостей.

У вас могут быть дополнительные параметры конфигурации, но суть в том, что в базовом файле docker-compose.yml вы просто задаете ту информацию, которая является общей для всех сред. Затем в файле docker-compose.override.yml или в аналогичных файлах для рабочей или промежуточной среды необходимо указать конфигурацию, характерную для каждой среды.

Обычно файл docker-compose.override.yml используется для среды разработки, как в следующем примере из eShopOnContainers.

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '3'

services: 
# Simplified number of services here: 
      
  basket.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_REDIS_BASKET_DB:-basket.data}
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}      
      - AzureServiceBusEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}

    ports:
      - "5103:80"

  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_CATALOG_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.CatalogDb;User Id=sa;Password=Pass@word}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_CATALOG_URL:-http://localhost:5101/api/v1/catalog/items/[0]/pic/}   
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}         
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_CATALOG_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_CATALOG_KEY}
      - UseCustomizationData=True
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
    ports:
      - "5101:80"

  marketing.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - ConnectionString=${ESHOP_AZURE_MARKETING_DB:-Server=sql.data;Database=Microsoft.eShopOnContainers.Services.MarketingDb;User Id=sa;Password=Pass@word}
      - MongoConnectionString=${ESHOP_AZURE_COSMOSDB:-mongodb://nosql.data}
      - MongoDatabase=MarketingDb
      - EventBusConnection=${ESHOP_AZURE_SERVICE_BUS:-rabbitmq}
      - EventBusUserName=${ESHOP_SERVICE_BUS_USERNAME}
      - EventBusPassword=${ESHOP_SERVICE_BUS_PASSWORD}          
      - identityUrl=http://identity.api              
      - IdentityUrlExternal=http://${ESHOP_EXTERNAL_DNS_NAME_OR_IP}:5105
      - CampaignDetailFunctionUri=${ESHOP_AZUREFUNC_CAMPAIGN_DETAILS_URI}
      - PicBaseUrl=${ESHOP_AZURE_STORAGE_MARKETING_URL:-http://localhost:5110/api/v1/campaigns/[0]/pic/}
      - AzureStorageAccountName=${ESHOP_AZURE_STORAGE_MARKETING_NAME}
      - AzureStorageAccountKey=${ESHOP_AZURE_STORAGE_MARKETING_KEY}
      - AzureServiceBusEnabled=False
      - AzureStorageEnabled=False
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5110:80"

  webmvc:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:80
      - CatalogUrl=http://catalog.api
      - OrderingUrl=http://ordering.api
      - BasketUrl=http://basket.api
      - LocationsUrl=http://locations.api
      - IdentityUrl=http://10.0.75.1:5105
      - MarketingUrl=http://marketing.api                                                    
      - CatalogUrlHC=http://catalog.api/hc
      - OrderingUrlHC=http://ordering.api/hc
      - IdentityUrlHC=http://identity.api/hc     
      - BasketUrlHC=http://basket.api/hc
      - MarketingUrlHC=http://marketing.api/hc
      - PaymentUrlHC=http://payment.api/hc
      - UseCustomizationData=True
      - ApplicationInsights__InstrumentationKey=${INSTRUMENTATION_KEY}
      - OrchestratorType=${ORCHESTRATOR_TYPE}
      - UseLoadTest=${USE_LOADTEST:-False}
    ports:
      - "5100:80"
  sql.data:
    environment:
      - MSSQL_SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
      - MSSQL_PID=Developer
    ports:
      - "5433:1433"
  nosql.data:
    ports:
      - "27017:27017"
  basket.data:
    ports:
      - "6379:6379"      
  rabbitmq:
    ports:
      - "15672:15672"
      - "5672:5672"

```

В этом примере конфигурация переопределения для среды разработки представляет некоторые порты для узла, задает переменные среды с URL-адресами перенаправления, а также указывает строки подключения для среды разработки. Все эти параметры предназначены только для среды разработки.

При выполнении команды `docker-compose up` (или запуске ее из Visual Studio) эта команда считывает переопределения автоматически, как если бы оба файла были объединены.

Предположим, что требуется другой файл Compose для рабочей среды, с другими значениями конфигурации, портами или строками подключения. Вы можете создать другой файл переопределения, например с именем `docker-compose.prod.yml`, содержащий другие параметры и переменные среды.  Этот файл может храниться в другом репозитории Git или управляться и защищаться другой группой.

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Развертывание с помощью конкретного файла переопределения

Чтобы использовать несколько файлов переопределения или файл переопределения с другим именем, можно указать эти файлы с помощью параметра -f в команде docker-compose. Команда compose объединяет файлы в том порядке, в котором они указаны в командной строке. В следующем примере показано, как выполняется развертывание с файлами переопределения.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Использование переменных среды в файлах docker-compose

Удобно, особенно в рабочих средах, иметь возможность получать сведения о конфигурации из переменных среды, как показано в предыдущих примерах. Ссылки на переменные среды в файлах docker-compose делаются с помощью синтаксиса \${MY\_VAR}. Следующая строка из файла docker-compose.prod.yml показывает, как ссылаться на значение переменной среды.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Переменные среды создаются и инициализируются разными способами в зависимости от среды узла (Linux, Windows, кластер Cloud и т. п.). Однако рекомендуется использовать ENV-файл. Файлы docker-compose поддерживает объявление переменных среды по умолчанию в ENV-файле. Эти значения для переменных среды являются значениями по умолчанию. Однако они могут быть переопределены значениями, которые, возможно, заданы в каждой из сред (ОС узла или переменные среды из кластера). Этот ENV-файл следует поместить в ту папку, из которой выполняется команда docker-compose.

В следующем примере показан ENV-файл, аналогичный [ENV](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env)-файлу для приложения eShopOnContainers.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Для команды docker-compose необходимо, чтобы каждая строка в ENV-файле была в формате &lt;переменная&gt;=&lt;значение&gt;.

Обратите внимание, что значения, установленные в среде выполнения, всегда переопределяют значения, определенные в ENV-файле. Аналогичным образом значения, переданные с помощью аргументов командной строки, тоже переопределяют значения по умолчанию, заданные в ENV-файле.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Общие сведения о Docker составления**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Несколько файлов составление**
    [*https://docs.docker.com/compose/extends/\#составить файлы несколько*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Создание оптимизированных образов Docker ASP.NET Core

Если вы изучаете Docker и .NET Core по источникам в Интернете, вы обнаружите файлы Dockerfile, демонстрирующие простоту создания образа Docker путем копирования источника в контейнер. Эти примеры показывают, что, используя простую конфигурацию, можно получить образ Docker со средой, упакованной с приложением. В следующем примере показан такой простой Dockerfile.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Такой Dockerfile будет работать. Тем не менее вы можете существенно оптимизировать ваши образы, особенно образы рабочей среды.

В модели контейнера и микрослужб вы постоянно запускаете контейнеры. Обычно контейнеры используются таким образом, чтобы не перезапускать спящий контейнер, так как контейнер является одноразовым. Оркестраторы (такие как Docker Swarm, Kubernetes, DCOS и Azure Service Fabric) просто создают новые экземпляры образов. Это означает, что вам нужно будет выполнить оптимизацию путем предварительной компиляции приложения во время его сборки, чтобы ускорить процесс создания экземпляра. Когда контейнер запускается, он должен быть готов к выполнению. Не следует выполнять восстановление и компиляцию во время выполнения с помощью команд dotnet restore и dotnet build из dotnet CLI, как показано в нескольких записях блога о .NET Core и Docker.

Команда .NET выполняет важнейшую работу, чтобы сделать .NET Core и ASP.NET Core платформой, оптимизированной для работы с контейнерами. .NET Core является не только облегченной платформой с небольшим объемом памяти; команда .NET работала над производительностью при запуске и создала несколько оптимизированных образов Docker, таких как образ [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), доступный в [Центре Docker](https://hub.docker.com/r/microsoft/aspnetcore/), в сравнении с обычными образами [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) или [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile). Образ [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) обеспечивает автоматическую настройку aspnetcore\_urls в порт 80 и кэш pre-ngend сборок; оба эти параметра приводят к ускорению запуска.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Создание оптимизированных образов Docker с ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Сборка приложения из контейнера сборки (CI)

Другим преимуществом Docker является возможность сборки приложения из предварительно настроенного контейнера, как показано на рисунке 8-13, так что не требуется создавать компьютер сборки или виртуальную машину для сборки приложения. Вы можете воспользоваться этим контейнером сборки или протестировать его, запустив его на компьютере разработки. Но еще интереснее то, что можно использовать один и тот же контейнер сборки из конвейера CI (непрерывной интеграции).

![](./media/image14.png)

**Рис. 8-13**. Контейнер сборки Docker, компилирующий двоичные файлы .NET 

Для этого сценария мы предоставляем образ [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/), который можно использовать для компиляции и сборки приложений ASP.NET Core. Результат помещается в образ на основе образа [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), который представляет собой оптимизированный образ среды выполнения, как указано выше.

Образ aspnetcore-build содержит все необходимое для компиляции приложения ASP.NET Core, включая .NET Core, пакет SDK ASP.NET, npm, Bower, Gulp и т. д.

Эти зависимости необходимы во время сборки. Но мы не хотим переносить их с приложением в среду выполнения, так как это сделает образ излишне большим. В приложении eShopOnContainers можно собрать приложение из контейнера, просто выполнив следующую команду docker-compose.

```
  docker-compose -f docker-compose.ci.build.yml up
```

На рисунке 8-14 показана эта команда, которая выполняется из командной строки.

![](./media/image15.png)

**Рис. 8-14**. Сборка приложения .NET из контейнера

Как можно видеть, выполняется контейнер ci-build\_1. Это основывается на образе aspnetcore-build, чтобы можно было выполнять компиляцию и сборку всего приложения из этого контейнера, а не с ПК. Вот почему на самом деле сборка и компиляция проектов .NET Core выполняется в Linux — потому что этот контейнер выполняется на узле Docker Linux по умолчанию.

Файл [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) для этого образа (часть eShopOnContainers) содержит следующий код. Вы видите, что он запускает контейнер сборки с помощью образа [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/).

```yml
version: '3'

services:

  ci-build:

    image: microsoft/aspnetcore-build:2.0

    volumes:
      - .:/src

    working_dir: /src

    command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && popd && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"

```

* Начиная с **.NET Core 2.0**, команда `dotnet restore` выполняется автоматически при выполнении команды `dotnet publish`.

Когда контейнер сборки запустился и начал работать, он выполняет команды dotnet restore и dotnet publish пакета SDK .NET для всех проектов в решении, чтобы скомпилировать биты .NET. В данном случае, поскольку приложение eShopOnContainers также имеет SPA на основе TypeScript и Angular для клиентского кода, ему, в свою очередь, необходимо проверить зависимости JavaScript с помощью команды npm, но это действие не связано с битами .NET.

Команда dotnet publish выполняет сборку и публикует скомпилированные выходные данные в каждой папке проекта в папку ../obj/Docker/publish, как показано на рисунке 8-15.

![](./media/image16.png)

**Рис. 8-15**. Двоичные файлы, созданные командой dotnet publish

#### <a name="creating-the-docker-images-from-the-cli"></a>Создание образов Docker из CLI

После публикации выходных данных приложения в связанных папках (в каждом проекте) следующий шаг заключается в фактическом создании образов Docker. Для этого используются команды docker-compose build и docker-compose up, как показано на рисунке 8-16.

![](./media/image17.png)

**Рис. 8-16**. Создание образов Docker и запуск контейнеров

На рисунке 8-17 показано, как выполняется команда docker-compose build.

![](./media/image18.png)

**Рис. 8-17**. Создание образов Docker с помощью команды docker-compose build

Различие между командами docker-compose build и docker-compose up состоит в том, что команда docker-compose up и создает, и запускает образы.

При использовании Visual Studio все эти действия выполняются внутренним образом. Visual Studio компилирует приложение .NET, создает образы Docker и развертывает контейнеры в узле Docker. Visual Studio предлагает дополнительные функциональные возможности, такие как возможность отладки контейнеров, работающих в Docker, непосредственно из Visual Studio.

Общий вывод заключается в том, что вы можете выполнять сборку приложения таким же образом, каким должен выполнять его сборку ваш конвейер CI/CD — из контейнера, а не с локального компьютера. После создания образов остается только запустить эти образы Docker с помощью команды docker-compose up.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Построение биты в другой контейнер: Настройка eShopOnContainers решение в среде Windows CLI (dotnet CLI, Docker CLI и VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI, - Docker - CLI- и -VS-код)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Назад] (data-driven-crud-microservice.md) [Далее] (database-server-container.md)
