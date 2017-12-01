---
title: "Определение приложения несколькими контейнера с docker compose.yml"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Определение приложения несколькими контейнера с docker compose.yml"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c5d4d2c9fb9fbb595f6f6ea195247474f353a32f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a>Определение приложения несколькими контейнера с docker compose.yml 

В этом руководстве [docker compose.yml](https://docs.docker.com/compose/compose-file/) файла была представлена в разделе [шаг 4. Определение службы в docker compose.yml при построении приложения несколькими контейнера Docker](#step4_define_svcs_in_docker_compose_yml). Тем не менее существуют дополнительные способы использования docker-compose файлы, которые являются более подробно исследовать.

Например можно явно описать способ развертывания приложения в файле docker compose.yml несколькими контейнера. При необходимости также можно описать, как необходимо для построения пользовательских образов Docker. (Пользовательские образы Docker можно также создавать с помощью Docker CLI.)

По сути определение каждого из контейнеров, которые требуется развернуть, а также определенные характеристики для каждого развертывания контейнера. Как только файл описания развертывание нескольких контейнера, можно развернуть все решение в рамках одной операции, под управлением [docker создания копии](https://docs.docker.com/compose/overview/) команду CLI, или его можно развернуть прозрачно с Visual Studio. В противном случае необходимо использовать Docker CLI для развертывания контейнера в несколько этапов с помощью docker, выполните команду из командной строки. Таким образом каждой службы, определенной в docker compose.yml необходимо указать ровно одно изображение или сборки. Остальные ключи являются необязательными и аналогичны их docker, запустите аналогами из командной строки.

В следующем примере кода YAML является определением файла невозможно, но один глобальный docker-compose.yml eShopOnContainers образца. Это не фактический docker-compose файл из eShopOnContainers. Вместо этого это версия упрощенной и объединенные в один файл, который не является наиболее подходящий способ работы с docker составить файлы, как будет описано ниже.

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

Корневой ключ в этом файле — служб. В данном разделе определения службы, нужно развернуть и запустить при выполнении docker составлять команды или при развертывании из Visual Studio с помощью этого файла docker compose.yml. В этом случае файл docker compose.yml имеет несколько служб, которые определены, как описано в следующем списке.

-   webmvc контейнера, включая приложения ASP.NET Core MVC, использование микрослужбами из C на стороне сервера\#

-   Catalog.API контейнера, включая микрослужбу каталога ASP.NET Core веб-API

-   Ordering.API контейнера, включая микрослужбу упорядочение веб-API ASP.NET Core

-   SQL.Data контейнер с SQL Server для Linux, удерживая микрослужбами баз данных

-   Basket.API контейнер с микрослужбу корзины ASP.NET Core веб-API

-   Basket.Data контейнера, запущенного служба кэша REDIS корзины базы данных в качестве кэша REDIS

### <a name="a-simple-web-service-api-container"></a>Простой контейнер API веб-службы

Сосредоточившись на один контейнер catalog.api контейнера микрослужбу имеет простой определение:

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

Контейнерного сервисе следующей базовой конфигурацией:

-   Он основан на eshop/catalog.api пользовательского образа. Чтобы упростить понимание является построение: параметр в файле ключа. Это означает, что образ должен был ранее создавали (с сборка docker), или были загружены (командой docker pull) из любой реестра Docker.

-   Он определяет переменную среды с именем "ConnectionString" в строке подключения для использования платформы Entity Framework для доступа к экземпляру SQL Server, содержащий модель данных каталога. В этом случае один и тот же контейнер SQL Server содержится несколько баз данных. Таким образом требуется меньше памяти в компьютере разработки для Docker. Однако можно также развернуть один контейнер SQL Server для каждой базы данных микрослужбы.

-   Имя SQL Server — sql.data, это же имя, используемое для контейнера, на котором выполняется экземпляр SQL Server для Linux. Это удобно; сетевой адрес разрешается в возможность использования этого разрешения имен (внутренний узел Docker), вам требуется знать внутренний IP-адрес для контейнеров, запрашиваемых от других контейнеров.

Так как строка подключения определяется переменной среды, можно задать эту переменную посредством другого механизма и в другое время. Например можно задать другую строку соединения при развертывании в рабочей среде, в окончательной узлов или выполнив из конвейеры CI/CD в VSTS или предпочтительный DevOps системы.

-   Он предоставляет порт 80 для внутреннего доступа к службе catalog.api узел Docker. Этот узел является виртуальной Машины Linux, так как оно зависит от образа Docker для Linux, но можно настроить контейнер для запуска в образ Windows, вместо этого.

-   Она передает предоставленный порт 80 для контейнера с портом 5101 на хост-компьютере Docker (виртуальной Машине Linux).

-   Ссылки на службу sql.data (экземпляр SQL Server для Linux базы данных, запущенные в контейнере) веб-службы. При указании этой зависимости catalog.api контейнера не будет начата до начала sql.data контейнера; Это важно, поскольку catalog.api должен иметь базы данных SQL Server и запущена сначала. Тем не менее этого вида зависимостей контейнера недостаточно во многих случаях потому, что Docker проверяет только на уровне контейнера. Иногда (в этом вариантов SQL Server) по-прежнему не возможно, служба готова, поэтому рекомендуется реализовать логику повторных попыток с экспоненциально растущим в микрослужбами вашего клиента. Таким образом, если контейнер зависимостей не готов в течение некоторого времени, приложение по-прежнему будет устойчивыми.

-   Он настроен для разрешения доступа к внешним серверам: дополнительного\_параметр узлов позволяет получить доступ к внешним серверам или машины за пределами узла Docker (то есть за пределами виртуальных Машин Linux, который Docker разработки по умолчанию размещения), например локального SQL Экземпляр сервера на Компьютере разработки.

Также существуют другие, дополнительные параметры docker compose.yml, которые обсуждаются в следующих разделах.

### <a name="using-docker-compose-files-to-target-multiple-environments"></a>С помощью docker составить файлы для нескольких сред

Файлы docker compose.yml файлы определения и могут использоваться несколько инфраструктур, которые распознает этот формат. Средство самый простой — docker-создание команды, но другие средства, как orchestrators (например, помощью Docker Swarm) также знание этого файла.

Таким образом, с помощью docker создание команды ориентировании следующих основных сценариев.

#### <a name="development-environments"></a>Для сред разработки

При разработке приложений важно иметь возможность запускать приложения в изолированной среде разработки. Можно использовать команду CLI для создания этой среды или использовать Visual Studio, которая использует docker составления на самом деле составления docker.

В файле docker compose.yml можно настроить и задокументировать все зависимости приложения от службы (других служб, кэша, базы данных, очереди, и т. д.). С помощью docker составить команду CLI, можно создать и запустить один или несколько контейнеров для каждой зависимости, с помощью одной команды (docker составления вверх).

Это файлы конфигурации, интерпретируемые подсистемой Docker docker compose.yml, но также выступать в качестве файлов удобный документации о структуре приложения несколькими контейнера.

#### <a name="testing-environments"></a>В средах тестирования

Модульные тесты и тесты интеграции, являются важной частью процесса непрерывного развертывания (CD) ни один процесс непрерывной интеграции (CI). Эти автоматические тесты требуются изолированной среде, поэтому они не затрагивает пользователей или любое другое изменение данных в приложении.

С помощью Docker Compose можно создавать и уничтожать, изолированную среду очень легко нескольких команд из командной строки или сценариев, таких как следующие команды:

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a>В производственных развертываниях

Также можно создать для развертывания на удаленных подсистемы Docker. Типичный случай — развернуть один экземпляр узла Docker (как в рабочей среде виртуальной Машины или на сервере, предоставлен [машины Docker](https://docs.docker.com/machine/overview/)). Но это также может быть весь [помощью Docker Swarm](https://docs.docker.com/swarm/overview/) кластера, так как кластеры также совместимы с файлами docker compose.yml.

При использовании других orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, т. д.), может потребоваться добавить настройки и метаданные параметры конфигурации, как в docker compose.yml, но в формат, требуемый других orchestrator.

В любом случае составления docker является удобный формат средства и метаданные для рабочих процессов разработки, тестирования и эксплуатации, несмотря на то, что рабочем процессе могут различаться на использовании orchestrator.

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a>С помощью нескольких docker составить файлы для обработки нескольких сред

При разработке для различных сред, следует использовать несколько составить файлы. Это позволяет создавать несколько вариантов конфигурации, в зависимости от среды.

#### <a name="overriding-the-base-docker-compose-file"></a>Переопределение базового docker-compose файла

Можно использовать файл одного docker-compose.yml как упрощенный примеры, приведенные в предыдущих разделах. Тем не менее, не рекомендуется для большинства приложений.

По умолчанию создать считывает два файла, docker-compose.yml и необязательный docker-compose.override.yml файла. Как показано в на рисунке 8 по 11, если вы используете Visual Studio и включение поддержки Docker, Visual Studio также создает эти файлы, а также некоторые дополнительные файлы, используемые для отладки.

![](./media/image12.png)

**На рисунке 8 по 11**. docker создания файлов в Visual Studio 2017 г.

Можно изменить с помощью любого редактора, таких как Visual Studio Code или Sublime, docker-compose файлов и запуск приложения с docker составления up команд.

По соглашению файл docker compose.yml содержит базовой конфигурации и других статических параметров. Это означает, что в зависимости от среды развертывания, который вы используете, не изменяйте конфигурацию службы.

Файл docker compose.override.yml названия, содержит параметры конфигурации, которые переопределяют базовой конфигурации, такие как конфигурация, которая зависит от среды развертывания. Также может иметь несколько переопределение файлов с разными именами. Переопределение файлы обычно содержат дополнительные сведения, необходимые для приложения, кроме определенного среды или развертывание.

#### <a name="targeting-multiple-environments"></a>Предназначенных для нескольких сред

Типичный случай использования является при определении нескольких образуют файлов позволяет разрабатывать несколько сред, таких как производство, промежуточное хранение CI или разработки. Для поддержки этих различий, вы можете разделить создать конфигурацию на несколько файлов, как показано на рисунке 8-12.

![](./media/image13.png)

**Рис. 8-12**. Несколько docker составления переопределение значений в файле базового docker-compose.yml файлов

Начните с базового docker-compose.yml файла. Этот базовый файл должен содержать базовый или статические параметры, которые не изменяются в зависимости от среды. Например eShopOnContainers имеет следующий файл docker compose.yml как основного файла.

```yml
#docker-compose.yml (Base)
version: '2'

services:
  basket.api:
    image: eshop/basket.api
    build:
    context: ./src/Services/Basket/Basket.API
    dockerfile: Dockerfile
    depends_on:
      - basket.data
      - identity.api
      - rabbitmq

  catalog.api:
    image: eshop/catalog.api
    build:
    context: ./src/Services/Catalog/Catalog.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  identity.api:
    image: eshop/identity.api
    build:
    context: ./src/Services/Identity/Identity.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data

  ordering.api:
    image: eshop/ordering.api
    build:
    context: ./src/Services/Ordering/Ordering.API
    dockerfile: Dockerfile
    depends_on:
      - sql.data
      - rabbitmq

  webspa:
    image: eshop/webspa
    build:
    context: ./src/Web/WebSPA
    dockerfile: Dockerfile
    depends_on:
      - identity.api
      - basket.api

  webmvc:
    image: eshop/webmvc
    build:
    context: ./src/Web/WebMVC
    dockerfile: Dockerfile
    depends_on:
      - catalog.api
      - ordering.api
      - identity.api
      - basket.api

  sql.data:
    image: microsoft/mssql-server-linux
    basket.data:
    image: redis
    expose:
      - "6379"
    rabbitmq:
    image: rabbitmq
    ports:
      - "5672:5672"

  webstatus:
    image: eshop/webstatus
    build:
    context: ./src/Web/WebStatus
    dockerfile: Dockerfile
```

Не следует изменять значения в файле базового docker-compose.yml из-за различных целевых средах развертывания.

Если установить фокус на webmvc определение службы, для экземпляра, вы увидите как эти сведения будут так же, независимо от того, какой среде вы может выделить. У вас есть следующие сведения:

-   Имя службы: webmvc.

-   Пользовательский образ контейнера: eshop/webmvc.

-   Команда для создания пользовательского образа Docker, позволяющее определить, какой файл Dockerfile для использования.

-   В зависимости от других служб, поэтому данный контейнер не будет начата до запуска других контейнеров зависимостей.

Имеется дополнительная настройка, но важно то, что в файле базового docker-compose.yml необходимо просто задать информацию, которая является общей для нескольких сред. Затем в docker compose.override.yml или аналогичных файлов для производственного или промежуточного хранения, необходимо поместить конфигурации, характерное для каждой среды.

Docker — compose.override.yml, обычно используется для среды разработки, как показано в следующем примере из eShopOnContainers:

```yml
#docker-compose.override.yml (Extended config for DEVELOPMENT env.)
version: '2'

services:
# Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database=Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Pass@word
      - ExternalCatalogBaseUrl=http://localhost:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
    - ASPNETCORE_ENVIRONMENT=Development
    - ASPNETCORE_URLS=http://0.0.0.0:5105
    - SpaClient=http://localhost:5104
    - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
    - MvcClient=http://localhost:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT=Development
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://localhost:5101
      - OrderingUrl=http://localhost:5102
      - IdentityUrl=http://localhost:5105
      - BasketUrl=http:// localhost:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Pass@word
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

В этом примере конфигурации переопределение разработки предоставляет некоторые порты на узел, определяет переменные среды с перенаправления URL-адресов, а также определяет строки подключения для среды разработки. Эти параметры используются все, что для среды разработки.

При запуске docker составить вверх (или запустите его из Visual Studio), команда считывает переопределения автоматически как если бы он объединение обоих файлов.

Предположим, что вы хотите другой файл создания сообщения для рабочей среды, со значениями другой конфигурации. Можно создать другой файл переопределения, следующим образом. (Этот файл может храниться в другой репозиторий Git или управляемые и защищены от другой команды.)

```yml
#docker-compose.prod.yml (Extended config for PRODUCTION env.)
version: '2'

services:
  # Simplified number of services here:
  catalog.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5101
      - ConnectionString=Server=sql.data; Database = Microsoft.eShopOnContainers.Services.CatalogDb; User Id=sa;Password=Prod@Pass
      - ExternalCatalogBaseUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
    ports:
      - "5101:5101"

  identity.api:
    environment:
      - ASPNETCORE_ENVIRONMENT=Production
      - ASPNETCORE_URLS=http://0.0.0.0:5105
      - SpaClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5104
      - ConnectionStrings__DefaultConnection = Server=sql.data;Database=Microsoft.eShopOnContainers.Service.IdentityDb;User Id=sa;Password=Pass@word
      - MvcClient=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5100
    ports:
      - "5105:5105"

  webspa:
    environment:
      - ASPNETCORE_ENVIRONMENT= Production
      - ASPNETCORE_URLS=http://0.0.0.0:5104
      - CatalogUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5101
      - OrderingUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5102
      - IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
      - BasketUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5103
    ports:
      - "5104:5104"

  sql.data:
    environment:
      - SA_PASSWORD=Prod@Pass
      - ACCEPT_EULA=Y
    ports:
      - "5433:1433"
```

#### <a name="how-to-deploy-with-a-specific-override-file"></a>Развертывание с помощью файла конкретного переопределения

Чтобы использовать несколько файлов переопределение, или переопределение файл с другим именем, можно использовать параметр -f с docker создание команды и укажите файлы. Создайте файлы слияний в порядке, в котором они указаны в командной строке. Приведенный ниже показано, как развертывать с помощью переопределения файлы.

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a>Использование переменных среды в docker создания файлов

Он является удобным, особенно в производственной среде, чтобы иметь возможность получать сведения о конфигурации из переменных среды, как было показано в предыдущих примерах. Ссылки на переменные среды в файлах с помощью синтаксиса docker-compose \${MY\_VAR}. Следующая строка из файла docker compose.prod.yml показано, как для ссылки на значение переменной среды.

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

Переменные среды создаются и инициализируются разными способами, в зависимости от среды узла (Linux, Windows, кластер облака, и т. д.). Однако удобный подход — использовать файл .env. Файлы docker-compose поддерживает объявление переменных среды по умолчанию в файле .env. Эти значения для переменных среды являются значениями по умолчанию. Однако они могут быть переопределены значения, которые определены в каждой из сред (операционной системе сервера или переменные среды из кластера). Поместить этот файл .env в той папке, где составления docker команда выполняется.

В следующем примере показано файла .env как [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) файл eShopOnContainers приложения.

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

Составить docker ожидает, что каждая строка в файле .env, чтобы быть в формате &lt;переменной&gt;=&lt;значение&gt;.

Обратите внимание, что значения, заданные в среде выполнения, всегда переопределяют значения, определенные в файле .env. Аналогичным образом значения, переданные аргументы командной строки также переопределить значения по умолчанию, заданные в файле .env.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Общие сведения о Docker составления**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)

-   **Несколько файлов составление**
    [*https://docs.docker.com/compose/extends/\#составить файлы несколько*](https://docs.docker.com/compose/extends/#multiple-compose-files)

### <a name="building-optimized-aspnet-core-docker-images"></a>Создание оптимизированных образов ASP.NET Core Docker

Если вы исследуете Docker и .NET Core на источников в Интернете, вы обнаружите, что файлы Dockerfile, демонстрирующие Простота создания образа Docker, скопировав источника в контейнер. Эти примеры предложения, используя простую конфигурацию, может иметь образа Docker среде упаковать с приложением. В следующем примере показано простое Dockerfile в этом вена.

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

Файл Dockerfile, как это будет работать. Тем не менее большей части можно оптимизировать вашей образы, особенно вашей рабочей среде.

В контейнере и микрослужбами модели постоянно запуске контейнеров. Типичный способ использования контейнеров не перезапускает контейнер находится в спящем режиме, так как контейнер может быть уничтожен. Orchestrators (например, помощью Docker Swarm, Kubernetes, DCOS или Azure Service Fabric) просто создать новые экземпляры изображений. Это значит, может потребоваться оптимизировать с помощью предварительной компиляции приложения при его построении таким образом, при создании экземпляра процесса быстрее. При запуске контейнера должны быть готовы к запуску. Не следует восстановить и компиляции во время выполнения, с помощью dotnet восстановления и dotnet сборки команды из dotnet CLI, как показано в записях блога о .NET Core и Docker.

Команда .NET предоставляет важные действия, чтобы заставить .NET Core и ASP.NET Core framework, оптимизированными для контейнера. Не только такое .NET Core облегченная платформа с небольшой объем памяти; основное внимание уделено производительность при запуске и, как произведено некоторые оптимизированных образов Docker группой [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) изображения, имеющаяся на [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), по сравнению с обычного [ Microsoft и dotnet](https://hub.docker.com/r/microsoft/dotnet/) или [microsoft-nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) изображения. [Microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) приведена Автоматическая настройка aspnetcore\_URL-адресов для порта 80 и pre ngend кэша сборок; оба этих параметра привести к более быстрый запуск.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Создание оптимизированных образов Docker с ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)

### <a name="building-the-application-from-a-build-ci-container"></a>Сборка приложения в другой контейнер сборки (CI)

Другим преимуществом Docker является созданием приложения из предварительно настроенных контейнера, как показано в на рисунке 8 – 13, поэтому необходимо создать компьютер сборки или виртуальной Машины для построения приложения. Можно использовать или тестовый контейнер этой сборки, запустив его на компьютере разработки. Однако самое еще более интересное, которые можно использовать один и тот же контейнер сборки из конвейера CI (непрерывной интеграции).

![](./media/image14.png)

**На рисунке 8 – 13**. Сборка .NET биты в другой контейнер компонентов

В этом сценарии мы предоставляем [aspnetcore/microsoft построения](https://hub.docker.com/r/microsoft/aspnetcore-build/) изображение, которое можно использовать для компиляции и сборки приложений на ASP.NET Core. Выходные данные помещаются в изображения на основе [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) изображение, которое является изображение оптимизированная среда выполнения, как описано выше.

Изображение aspnetcore сборки содержит все необходимое для компиляции приложения ASP.NET Core, включая .NET Core, пакет SDK для ASP.NET, npm, Bower, Gulp, и т. д.

Эти зависимости необходимо во время построения. Но мы не нужно выполнить их с приложением во время выполнения, так как это сделает изображение излишне большим. В приложении eShopOnContainers можно построить приложение из контейнера, просто выполнив следующие docker создание команды.

```
  docker-compose -f docker-compose.ci.build.yml up
```

Рис. 8-14 показано это команда, которая выполняется из командной строки.

![](./media/image15.png)

**Рис. 8-14.** Построение приложений .NET из контейнера

Как видите, контейнер, который работает под управлением имеет сборки ci\_1 контейнер. Основывается на образе aspnetcore построения, чтобы его можно скомпилировать и построить приложение целиком из этого контейнера, а не с вашего компьютера. Т. е. Почему на самом деле он построения и компиляция проектов .NET Core в Linux, так как этот контейнер выполняется на узле Docker Linux по умолчанию.

[Docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) -файле для этого образа (часть eShopOnContainers) содержит следующий код. Вы увидите запускает контейнер сборки с помощью [aspnetcore/microsoft построения](https://hub.docker.com/r/microsoft/aspnetcore-build/) изображения.

```yml
version: '2'
  services:
    ci-build:
      image: microsoft/aspnetcore-build:1.0-1.1
      volumes:
        - .:/src
      working_dir: /src
      command: /bin/bash -c "pushd ./src/Web/WebSPA && npm rebuild node-sass && pushd ./../../.. && dotnet restore ./eShopOnContainers-ServicesAndWebApps.sln && dotnet publish ./eShopOnContainers-ServicesAndWebApps.sln -c Release -o ./obj/Docker/publish"
```

* Начиная с **.NET Core 2.0**, `dotnet restore` команда автоматически выполняется при `dotnet publish` выполняется команда.

После построения контейнера запущен и работает, он работает восстановления dotnet .NET SDK и dotnet опубликовать команд для всех проектов в решении, чтобы скомпилировать биты .NET. Таким образом так как eShopOnContainers также SPA на основе TypeScript и угловой для клиентского кода, его также необходимо проверить зависимости JavaScript с помощью npm, но это действие не связано с биты .NET.

Dotnet публикации построений команды и публикует выходные данные компиляции в каждый проект в папке... папка /obj/Docker/Publish, как показано на рисунке 8-15.

![](./media/image16.png)

**Рис. 8-15.** Команда публикации двоичные файлы, созданные dotnet

#### <a name="creating-the-docker-images-from-the-cli"></a>Создание образов Docker из CLI

После публикации выходных данных приложения в связанных папки (в каждом проекте) следующий шаг — фактически создание образов Docker. Для этого используйте сборку docker-compose и docker — составить команды, как показано на рисунке 8-16.

![](./media/image17.png)

**На рисунке 8-16.** Создание образов Docker и выполнение контейнеров

В на рисунке 8-17, можно увидеть как docker-compose сборка выполняется команда.

![](./media/image18.png)

**На рисунке 8-17**. Создание образов Docker с помощью docker-создание команды построения

Разница между docker-compose построения и составлять docker копирование команды является то, что docker составления построения и запуска изображений.

При использовании Visual Studio, на самом деле выполняются следующие действия. Visual Studio компилирует приложения .NET, создает образы Docker и развертывает контейнеры в узле Docker. Visual Studio предлагает дополнительные функции, такие как возможность отладки в контейнеры, работающего в Docker, напрямую из Visual Studio.

Здесь общую takeway является возможность создавать приложения, каким образом конвейер CI/CD должны использовать его же — из контейнера, а не с локального компьютера. После того, изображения, созданные, затем необходимо просто выполнить образов Docker, с помощью docker-составления копирование команды.

#### <a name="additional-resources"></a>Дополнительные ресурсы

-   **Построение биты в другой контейнер: Настройка eShopOnContainers решение в среде Windows CLI (dotnet CLI, Docker CLI и VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-UP-in-a-Windows-CLI-Environment-(DotNet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))


>[!div class="step-by-step"]
[Предыдущие] (данные управляемых crud-microservice.md) [Далее] (база данных сервера container.md)
