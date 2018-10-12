---
title: Определение многоконтейнерного приложения с помощью docker-compose.yml
description: Архитектура микрослужб .NET для контейнерных приложений .NET | Определение многоконтейнерного приложения с помощью docker-compose.yml
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/30/2017
ms.openlocfilehash: d1c4166129716ccbbc86855e38d631f493b82290
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46937609"
---
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="76dc6-103">Определение многоконтейнерного приложения с помощью docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="76dc6-103">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="76dc6-104">В данном руководстве файл [docker-compose.yml](https://docs.docker.com/compose/compose-file/) был представлен в разделе [Шаг 4. Определение служб в файле docker-compose.yml при сборке многоконтейнерного приложения Docker](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="76dc6-104">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="76dc6-105">Тем не менее существуют дополнительные способы использования файлов docker-compose, которые стоит изучить более подробно.</span><span class="sxs-lookup"><span data-stu-id="76dc6-105">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="76dc6-106">Например, в файле docker-compose.yml вы можете явно описать, как следует развертывать ваше многоконтейнерное приложение.</span><span class="sxs-lookup"><span data-stu-id="76dc6-106">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="76dc6-107">При необходимости также можно описать, как вы планируете собирать свои пользовательские образы Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-107">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="76dc6-108">(Пользовательские образы Docker можно также собрать с помощью Docker CLI.)</span><span class="sxs-lookup"><span data-stu-id="76dc6-108">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="76dc6-109">В сущности, вы определяете каждый из контейнеров, которые планируете развернуть, и конкретные характеристики для каждого развертывания контейнера.</span><span class="sxs-lookup"><span data-stu-id="76dc6-109">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="76dc6-110">Создав файл описания многоконтейнерного развертывания, вы можете развернуть все решение в одном действии, управляемом командой CLI [docker-compose up](https://docs.docker.com/compose/overview/), или развернуть решение прозрачно из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="76dc6-110">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="76dc6-111">В противном случае придется использовать Docker CLI, чтобы разворачивать контейнер за контейнером в несколько этапов с помощью команды docker run из командной строки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-111">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="76dc6-112">Таким образом, для каждой службы, определенной в файле docker-compose.yml, необходимо указать ровно один образ или сборку.</span><span class="sxs-lookup"><span data-stu-id="76dc6-112">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="76dc6-113">Остальные ключи являются необязательными и соответствуют своим аналогам в командной строке docker run.</span><span class="sxs-lookup"><span data-stu-id="76dc6-113">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="76dc6-114">В следующем примере кода YAML представлено определение возможно глобального, но единственного файла docker-compose.yml для примера eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="76dc6-114">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="76dc6-115">Это ненастоящий файл docker-compose из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="76dc6-115">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="76dc6-116">Это упрощенная и объединенная в один файл версия, представляющая не лучший способ работы с файлами docker-compose, как будет показано ниже.</span><span class="sxs-lookup"><span data-stu-id="76dc6-116">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

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

<span data-ttu-id="76dc6-117">Корневой ключ в этом файле — services.</span><span class="sxs-lookup"><span data-stu-id="76dc6-117">The root key in this file is services.</span></span> <span data-ttu-id="76dc6-118">Под этим ключом определяются службы, которые требуется развернуть и запустить при выполнении команды docker-compose или при развертывании из Visual Studio с помощью этого файла docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="76dc6-118">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="76dc6-119">В данном случае в файле docker-compose.yml определено несколько служб, как показано в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="76dc6-119">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="76dc6-120">webmvc — контейнер, включающий приложение MVC ASP.NET Core и использующий микрослужбы из C\# на стороне сервера.</span><span class="sxs-lookup"><span data-stu-id="76dc6-120">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="76dc6-121">catalog.api — контейнер, включающий микрослужбу Catalog веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="76dc6-121">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="76dc6-122">ordering.api — контейнер, включающий микрослужбу Ordering веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="76dc6-122">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="76dc6-123">sql.data — контейнер, запускающий SQL Server для Linux, в котором содержатся базы данных микрослужб.</span><span class="sxs-lookup"><span data-stu-id="76dc6-123">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="76dc6-124">basket.api — контейнер с микрослужбой Basket веб-API ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="76dc6-124">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="76dc6-125">basket.data — контейнер, запускающий службу кэша REDIS, с базой данных basket в качестве кэша REDIS.</span><span class="sxs-lookup"><span data-stu-id="76dc6-125">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="76dc6-126">Простой контейнер API веб-службы</span><span class="sxs-lookup"><span data-stu-id="76dc6-126">A simple Web Service API container</span></span>

<span data-ttu-id="76dc6-127">Рассмотрим один контейнер. Контейнер-микрослужба catalog.api имеет простое определение:</span><span class="sxs-lookup"><span data-stu-id="76dc6-127">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

```yml
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
```

<span data-ttu-id="76dc6-128">Эта контейнерная служба имеет следующую базовую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="76dc6-128">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="76dc6-129">Она основывается на пользовательском образе eshop/catalog.api.</span><span class="sxs-lookup"><span data-stu-id="76dc6-129">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="76dc6-130">Проще говоря, в файле не задан ключ build:.</span><span class="sxs-lookup"><span data-stu-id="76dc6-130">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="76dc6-131">Это означает, что образ должен быть предварительно создан (с помощью команды docker build) или загружен (с помощью команды docker pull) из любого реестра Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-131">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="76dc6-132">Она определяет переменную среды с именем ConnectionString со строкой подключения, которая должна использоваться Entity Framework для доступа к экземпляру SQL Server, содержащему модель данных каталога.</span><span class="sxs-lookup"><span data-stu-id="76dc6-132">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="76dc6-133">В данном случае в одном контейнере SQL Server содержатся несколько баз данных.</span><span class="sxs-lookup"><span data-stu-id="76dc6-133">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="76dc6-134">Поэтому на компьютере разработки потребуется меньше памяти для Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-134">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="76dc6-135">Однако можно было бы также развернуть по одному контейнеру SQL Server для каждой базы данных микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="76dc6-135">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="76dc6-136">Имя SQL Server — sql.data; это же имя используется для контейнера, в котором выполняется экземпляр SQL Server для Linux.</span><span class="sxs-lookup"><span data-stu-id="76dc6-136">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="76dc6-137">Это удобно; благодаря этой возможности служба разрешения имен (внутренняя для узла Docker) будет разрешать сетевой адрес, так что вам не нужно знать внутренний IP-адрес для контейнеров при доступе к ним из других контейнеров.</span><span class="sxs-lookup"><span data-stu-id="76dc6-137">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="76dc6-138">Так как строка подключения определяется переменной среды, можно задавать эту переменную посредством другого механизма и в другое время.</span><span class="sxs-lookup"><span data-stu-id="76dc6-138">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="76dc6-139">Например, можно задать другую строку подключения при развертывании в рабочей среде на финальных узлах или сделать это из конвейеров CI/CD в Azure DevOps Services или в другой предпочитаемой системе DevOps.</span><span class="sxs-lookup"><span data-stu-id="76dc6-139">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in Azure DevOps Services or your preferred DevOps system.</span></span>

-   <span data-ttu-id="76dc6-140">Она представляет порт 80 для внутреннего доступа к службе catalog.api в узле Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-140">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="76dc6-141">В данном случае этот узел является виртуальной машиной Linux, так как он основан на образе Docker для Linux, но можно настроить контейнер для запуска в образе Windows.</span><span class="sxs-lookup"><span data-stu-id="76dc6-141">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="76dc6-142">Она переадресует предоставленный порт 80 в порт 5101 на хост-компьютере Docker (виртуальной машине Linux).</span><span class="sxs-lookup"><span data-stu-id="76dc6-142">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="76dc6-143">Она связывает веб-службу со службой sql.data (экземпляром SQL Server для базы данных Linux, запущенным в контейнере).</span><span class="sxs-lookup"><span data-stu-id="76dc6-143">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="76dc6-144">Если вы указываете эту зависимость, контейнер catalog.api не будет запускаться до запуска контейнера sql.data. Это важно, поскольку для catalog.api требуется уже запущенная база данных SQL Server.</span><span class="sxs-lookup"><span data-stu-id="76dc6-144">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="76dc6-145">Тем не менее во многих случаях недостаточно использовать этот вид зависимости контейнера, так как Docker выполняет проверку только на уровне контейнера.</span><span class="sxs-lookup"><span data-stu-id="76dc6-145">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="76dc6-146">Иногда служба (в данном случае SQL Server) может быть еще не готова, поэтому рекомендуется реализовать в клиентских микрослужбах логику повторов с экспоненциальным отходом.</span><span class="sxs-lookup"><span data-stu-id="76dc6-146">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="76dc6-147">Таким образом, если контейнер зависимостей будет не готов в течение некоторого времени, приложение по-прежнему будет устойчивым.</span><span class="sxs-lookup"><span data-stu-id="76dc6-147">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="76dc6-148">Она настроена для разрешения доступа к внешним серверам: параметр extra\_hosts позволяет получать доступ к внешним серверам или компьютерам за пределами узла Docker (то есть за пределами виртуальной машины Linux по умолчанию, которая является узлом разработки Docker), таким как локальный экземпляр SQL Server на компьютере разработки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-148">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="76dc6-149">В файле docker-compose.yml также имеются другие, более сложные параметры, которые рассматриваются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="76dc6-149">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="76dc6-150">Использование файлов docker-compose для нескольких сред</span><span class="sxs-lookup"><span data-stu-id="76dc6-150">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="76dc6-151">Файлы docker-compose.yml являются файлами определения и могут использоваться несколькими инфраструктурами, которые распознают этот формат.</span><span class="sxs-lookup"><span data-stu-id="76dc6-151">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="76dc6-152">Самый простой инструмент — это команда docker-compose, но с этим файлом могут работать и другие инструменты, такие как оркестраторы (например, Docker Swarm).</span><span class="sxs-lookup"><span data-stu-id="76dc6-152">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="76dc6-153">Таким образом, используя команду docker-compose, вы можете реализовать следующие основные сценарии.</span><span class="sxs-lookup"><span data-stu-id="76dc6-153">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="76dc6-154">Среды разработки</span><span class="sxs-lookup"><span data-stu-id="76dc6-154">Development environments</span></span>

<span data-ttu-id="76dc6-155">При разработке приложений важно иметь возможность запускать приложение в изолированной среде разработки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-155">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="76dc6-156">Можно создать такую среду с помощью команды CLI docker-compose или использовать Visual Studio, в котором команда docker-compose применяется внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="76dc6-156">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="76dc6-157">Файл docker-compose.yml позволяет настраивать и документировать все зависимости служб вашего приложения (другие службы, кэш, базы данных, очереди и т. п.).</span><span class="sxs-lookup"><span data-stu-id="76dc6-157">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="76dc6-158">С помощью команды CLI docker-compose вы можете создавать и запускать один или несколько контейнеров для каждой зависимости одной командой (docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="76dc6-158">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="76dc6-159">Файлы docker-compose.yml — это файлы конфигурации, интерпретированные подсистемой Docker, но они также служат в качестве удобных файлов документирования сведений о составе вашего многоконтейнерного приложения.</span><span class="sxs-lookup"><span data-stu-id="76dc6-159">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="76dc6-160">Тестовые среды</span><span class="sxs-lookup"><span data-stu-id="76dc6-160">Testing environments</span></span>

<span data-ttu-id="76dc6-161">Важной частью любого процесса непрерывного развертывания (CD) или непрерывной интеграции (CI) являются модульные тесты и интеграционные тесты.</span><span class="sxs-lookup"><span data-stu-id="76dc6-161">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="76dc6-162">Для этих автоматических тестов требуется изолированная среда, чтобы на них не влияли пользователи или какие-либо изменения данных в приложении.</span><span class="sxs-lookup"><span data-stu-id="76dc6-162">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="76dc6-163">Используя Docker Compose, можно очень просто создавать и уничтожать такую изолированную среду с помощью нескольких команд, выполненных в командной строке, или скриптов; например, с помощью следующих команд:</span><span class="sxs-lookup"><span data-stu-id="76dc6-163">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="76dc6-164">Рабочие развертывания</span><span class="sxs-lookup"><span data-stu-id="76dc6-164">Production deployments</span></span>

<span data-ttu-id="76dc6-165">Команду Compose можно также использовать для развертывания в удаленной подсистеме Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-165">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="76dc6-166">Типичный случай — развертывание на один экземпляр узла Docker (такой как рабочая виртуальная машина или сервер с установленной [машиной Docker](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="76dc6-166">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="76dc6-167">Но это также может быть весь кластер [Docker Swarm](https://docs.docker.com/swarm/overview/), поскольку кластеры тоже совместимы с файлами docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="76dc6-167">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="76dc6-168">При использовании любых других оркестраторов (Azure Service Fabric, Mesos DC/OS, Kubernetes и т. п.) может потребоваться добавить параметры настройки и конфигурации метаданных, аналогичные имеющимся в файле docker-compose.yml, но в формате, необходимом для этого другого оркестратора.</span><span class="sxs-lookup"><span data-stu-id="76dc6-168">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="76dc6-169">В любом случае docker-compose является удобным инструментом и форматом метаданных для рабочих процессов развертывания, тестирования и работы, хотя рабочий процесс работы может отличаться в зависимости от используемого оркестратора.</span><span class="sxs-lookup"><span data-stu-id="76dc6-169">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="76dc6-170">Использование нескольких файлов docker-compose для обработки разных сред</span><span class="sxs-lookup"><span data-stu-id="76dc6-170">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="76dc6-171">Если планируются разные среды, необходимо использовать несколько файлов compose.</span><span class="sxs-lookup"><span data-stu-id="76dc6-171">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="76dc6-172">Это позволяет создать несколько вариантов конфигурации в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-172">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="76dc6-173">Переопределение базового файла docker-compose</span><span class="sxs-lookup"><span data-stu-id="76dc6-173">Overriding the base docker-compose file</span></span>

<span data-ttu-id="76dc6-174">Вы можете использовать единственный файл docker-compose.yml, как показано в упрощенных примерах, приведенных в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="76dc6-174">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="76dc6-175">Однако для большинства приложений это не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="76dc6-175">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="76dc6-176">По умолчанию Compose читает два файла, docker-compose.yml и дополнительный файл docker-compose.override.yml.</span><span class="sxs-lookup"><span data-stu-id="76dc6-176">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="76dc6-177">Как показано на рисунке 8-11, если вы работаете в Visual Studio и включаете поддержку Docker, Visual Studio при этом создает дополнительный файл docker-compose.ci.build.yml для использования из конвейеров CI/CD, как в Azure DevOps Services.</span><span class="sxs-lookup"><span data-stu-id="76dc6-177">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates an additional docker-compose.ci.build,yml file for you to use from your CI/CD pipelines like in Azure DevOps Services.</span></span>

![](./media/image12.png)

<span data-ttu-id="76dc6-178">**Рис. 8-11**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-178">**Figure 8-11**.</span></span> <span data-ttu-id="76dc6-179">Файлы docker-compose в Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="76dc6-179">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="76dc6-180">Файлы docker-compose можно изменить в любом редакторе, например в Visual Studio Code или Sublime, и запустить приложение с помощью команды docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="76dc6-180">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="76dc6-181">По определению файл docker-compose.yml содержит базовую конфигурацию и другие статические параметры.</span><span class="sxs-lookup"><span data-stu-id="76dc6-181">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="76dc6-182">Это означает, что конфигурация службы не должна изменяться в зависимости от целевой среды развертывания.</span><span class="sxs-lookup"><span data-stu-id="76dc6-182">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="76dc6-183">Файл docker-compose.override.yml, как следует из его имени, содержит параметры конфигурации, которые переопределяют базовую конфигурацию, например конфигурацию, зависящую от среды развертывания.</span><span class="sxs-lookup"><span data-stu-id="76dc6-183">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="76dc6-184">У вас может быть несколько файлов переопределения с разными именами.</span><span class="sxs-lookup"><span data-stu-id="76dc6-184">You can have multiple override files with different names also.</span></span> <span data-ttu-id="76dc6-185">Файлы переопределения обычно содержат дополнительные сведения, необходимые для приложения, но относящиеся к конкретной среде или развертыванию.</span><span class="sxs-lookup"><span data-stu-id="76dc6-185">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="76dc6-186">Планирование нескольких сред</span><span class="sxs-lookup"><span data-stu-id="76dc6-186">Targeting multiple environments</span></span>

<span data-ttu-id="76dc6-187">Распространенный вариант использования заключается в том, что определяется несколько файлов compose, чтобы можно было планировать несколько сред, таких как рабочая среда, промежуточная среда, среда CI или среда разработки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-187">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="76dc6-188">Для поддержки этих разных сред можно разделить конфигурацию Compose на несколько файлов, как показано на рисунке 8-12.</span><span class="sxs-lookup"><span data-stu-id="76dc6-188">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="76dc6-189">**Рис. 8-12**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-189">**Figure 8-12**.</span></span> <span data-ttu-id="76dc6-190">Несколько файлов docker-compose, переопределяющих значения в базовом файле docker-compose.yml</span><span class="sxs-lookup"><span data-stu-id="76dc6-190">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="76dc6-191">Вы начинаете с базового файла docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="76dc6-191">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="76dc6-192">Этот базовый файл должен содержать базовые или статические параметры конфигурации, которые не изменяются в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-192">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="76dc6-193">Например, eShopOnContainers имеет в качестве базового файла следующий файл docker-compose.yml.</span><span class="sxs-lookup"><span data-stu-id="76dc6-193">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

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

<span data-ttu-id="76dc6-194">Значения в базовом файле docker-compose.yml не должны изменяться из-за разных целевых сред развертывания.</span><span class="sxs-lookup"><span data-stu-id="76dc6-194">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="76dc6-195">Если рассмотреть, например, определение службы webmvc, то можно увидеть, что эта информация большей частью одинакова независимо от планируемой среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-195">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="76dc6-196">В этом определении содержится следующая информация.</span><span class="sxs-lookup"><span data-stu-id="76dc6-196">You have the following information:</span></span>

-   <span data-ttu-id="76dc6-197">Имя службы: webmvc.</span><span class="sxs-lookup"><span data-stu-id="76dc6-197">The service name: webmvc.</span></span>

-   <span data-ttu-id="76dc6-198">Пользовательский образ контейнера: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="76dc6-198">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="76dc6-199">Команда для создания пользовательского образа Docker, указывающая, какой Dockerfile следует использовать.</span><span class="sxs-lookup"><span data-stu-id="76dc6-199">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="76dc6-200">Зависимости от других служб, чтобы данный контейнер не запускался до запуска других контейнеров зависимостей.</span><span class="sxs-lookup"><span data-stu-id="76dc6-200">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="76dc6-201">У вас могут быть дополнительные параметры конфигурации, но суть в том, что в базовом файле docker-compose.yml вы просто задаете ту информацию, которая является общей для всех сред.</span><span class="sxs-lookup"><span data-stu-id="76dc6-201">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="76dc6-202">Затем в файле docker-compose.override.yml или в аналогичных файлах для рабочей или промежуточной среды необходимо указать конфигурацию, характерную для каждой среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-202">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="76dc6-203">Обычно файл docker-compose.override.yml используется для среды разработки, как в следующем примере из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="76dc6-203">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

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

<span data-ttu-id="76dc6-204">В этом примере конфигурация переопределения для среды разработки представляет некоторые порты для узла, задает переменные среды с URL-адресами перенаправления, а также указывает строки подключения для среды разработки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-204">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="76dc6-205">Все эти параметры предназначены только для среды разработки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-205">These settings are all just for the development environment.</span></span>

<span data-ttu-id="76dc6-206">При выполнении команды `docker-compose up` (или запуске ее из Visual Studio) эта команда считывает переопределения автоматически, как если бы оба файла были объединены.</span><span class="sxs-lookup"><span data-stu-id="76dc6-206">When you run `docker-compose up` (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="76dc6-207">Предположим, что требуется другой файл Compose для рабочей среды, с другими значениями конфигурации, портами или строками подключения.</span><span class="sxs-lookup"><span data-stu-id="76dc6-207">Suppose that you want another Compose file for the production environment, with different configuration values, ports or connection strings.</span></span> <span data-ttu-id="76dc6-208">Вы можете создать другой файл переопределения, например с именем `docker-compose.prod.yml`, содержащий другие параметры и переменные среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-208">You can create another override file, like file named `docker-compose.prod.yml` with different settings and environment variables.</span></span>  <span data-ttu-id="76dc6-209">Этот файл может храниться в другом репозитории Git или управляться и защищаться другой группой.</span><span class="sxs-lookup"><span data-stu-id="76dc6-209">That file might be stored in a different Git repo or managed and secured by a different team.</span></span>

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="76dc6-210">Развертывание с помощью конкретного файла переопределения</span><span class="sxs-lookup"><span data-stu-id="76dc6-210">How to deploy with a specific override file</span></span>

<span data-ttu-id="76dc6-211">Чтобы использовать несколько файлов переопределения или файл переопределения с другим именем, можно указать эти файлы с помощью параметра -f в команде docker-compose.</span><span class="sxs-lookup"><span data-stu-id="76dc6-211">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="76dc6-212">Команда compose объединяет файлы в том порядке, в котором они указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="76dc6-212">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="76dc6-213">В следующем примере показано, как выполняется развертывание с файлами переопределения.</span><span class="sxs-lookup"><span data-stu-id="76dc6-213">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="76dc6-214">Использование переменных среды в файлах docker-compose</span><span class="sxs-lookup"><span data-stu-id="76dc6-214">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="76dc6-215">Удобно, особенно в рабочих средах, иметь возможность получать сведения о конфигурации из переменных среды, как показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="76dc6-215">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="76dc6-216">Ссылки на переменные среды в файлах docker-compose делаются с помощью синтаксиса \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="76dc6-216">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="76dc6-217">Следующая строка из файла docker-compose.prod.yml показывает, как ссылаться на значение переменной среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-217">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="76dc6-218">Переменные среды создаются и инициализируются разными способами в зависимости от среды узла (Linux, Windows, кластер Cloud и т. п.).</span><span class="sxs-lookup"><span data-stu-id="76dc6-218">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="76dc6-219">Однако рекомендуется использовать ENV-файл.</span><span class="sxs-lookup"><span data-stu-id="76dc6-219">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="76dc6-220">Файлы docker-compose поддерживает объявление переменных среды по умолчанию в ENV-файле.</span><span class="sxs-lookup"><span data-stu-id="76dc6-220">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="76dc6-221">Эти значения для переменных среды являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76dc6-221">These values for the environment variables are the default values.</span></span> <span data-ttu-id="76dc6-222">Однако они могут быть переопределены значениями, которые, возможно, заданы в каждой из сред (ОС узла или переменные среды из кластера).</span><span class="sxs-lookup"><span data-stu-id="76dc6-222">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="76dc6-223">Этот ENV-файл следует поместить в ту папку, из которой выполняется команда docker-compose.</span><span class="sxs-lookup"><span data-stu-id="76dc6-223">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="76dc6-224">В следующем примере показан ENV-файл, аналогичный [ENV](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env)-файлу для приложения eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="76dc6-224">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="76dc6-225">Для команды docker-compose необходимо, чтобы каждая строка в ENV-файле была в формате &lt;переменная&gt;=&lt;значение&gt;.</span><span class="sxs-lookup"><span data-stu-id="76dc6-225">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="76dc6-226">Обратите внимание, что значения, установленные в среде выполнения, всегда переопределяют значения, определенные в ENV-файле.</span><span class="sxs-lookup"><span data-stu-id="76dc6-226">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="76dc6-227">Аналогичным образом значения, переданные с помощью аргументов командной строки, тоже переопределяют значения по умолчанию, заданные в ENV-файле.</span><span class="sxs-lookup"><span data-stu-id="76dc6-227">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="76dc6-228">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="76dc6-228">Additional resources</span></span>

-   <span data-ttu-id="76dc6-229">**Общие сведения о Docker Compose**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="76dc6-229">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="76dc6-230">**Несколько файлов Compose**
    [*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="76dc6-230">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="76dc6-231">Создание оптимизированных образов Docker ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="76dc6-231">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="76dc6-232">Если вы изучаете Docker и .NET Core по источникам в Интернете, вы обнаружите файлы Dockerfile, демонстрирующие простоту создания образа Docker путем копирования источника в контейнер.</span><span class="sxs-lookup"><span data-stu-id="76dc6-232">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="76dc6-233">Эти примеры показывают, что, используя простую конфигурацию, можно получить образ Docker со средой, упакованной с приложением.</span><span class="sxs-lookup"><span data-stu-id="76dc6-233">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="76dc6-234">В следующем примере показан такой простой Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="76dc6-234">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="76dc6-235">Такой Dockerfile будет работать.</span><span class="sxs-lookup"><span data-stu-id="76dc6-235">A Dockerfile like this will work.</span></span> <span data-ttu-id="76dc6-236">Тем не менее вы можете существенно оптимизировать ваши образы, особенно образы рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="76dc6-236">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="76dc6-237">В модели контейнера и микрослужб вы постоянно запускаете контейнеры.</span><span class="sxs-lookup"><span data-stu-id="76dc6-237">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="76dc6-238">Обычно контейнеры используются таким образом, чтобы не перезапускать спящий контейнер, так как контейнер является одноразовым.</span><span class="sxs-lookup"><span data-stu-id="76dc6-238">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="76dc6-239">Оркестраторы (такие как Docker Swarm, Kubernetes, DCOS и Azure Service Fabric) просто создают новые экземпляры образов.</span><span class="sxs-lookup"><span data-stu-id="76dc6-239">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="76dc6-240">Это означает, что вам нужно будет выполнить оптимизацию путем предварительной компиляции приложения во время его сборки, чтобы ускорить процесс создания экземпляра.</span><span class="sxs-lookup"><span data-stu-id="76dc6-240">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="76dc6-241">Когда контейнер запускается, он должен быть готов к выполнению.</span><span class="sxs-lookup"><span data-stu-id="76dc6-241">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="76dc6-242">Не следует выполнять восстановление и компиляцию во время выполнения с помощью команд dotnet restore и dotnet build из dotnet CLI, как показано в нескольких записях блога о .NET Core и Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-242">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="76dc6-243">Команда .NET выполняет важнейшую работу, чтобы сделать .NET Core и ASP.NET Core платформой, оптимизированной для работы с контейнерами.</span><span class="sxs-lookup"><span data-stu-id="76dc6-243">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="76dc6-244">.NET Core является не только облегченной платформой с небольшим объемом памяти; команда .NET работала над производительностью при запуске и создала несколько оптимизированных образов Docker, таких как образ [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), доступный в [Центре Docker](https://hub.docker.com/r/microsoft/aspnetcore/), в сравнении с обычными образами [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) или [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile).</span><span class="sxs-lookup"><span data-stu-id="76dc6-244">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="76dc6-245">Образ [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) обеспечивает автоматическую настройку aspnetcore\_urls в порт 80 и кэш pre-ngend сборок; оба эти параметра приводят к ускорению запуска.</span><span class="sxs-lookup"><span data-stu-id="76dc6-245">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="76dc6-246">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="76dc6-246">Additional resources</span></span>

-   <span data-ttu-id="76dc6-247">**Создание оптимизированных образов Docker в ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="76dc6-247">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="76dc6-248">Сборка приложения из контейнера сборки (CI)</span><span class="sxs-lookup"><span data-stu-id="76dc6-248">Building the application from a build (CI) container</span></span>

<span data-ttu-id="76dc6-249">Другим преимуществом Docker является возможность сборки приложения из предварительно настроенного контейнера, как показано на рисунке 8-13, так что не требуется создавать компьютер сборки или виртуальную машину для сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="76dc6-249">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="76dc6-250">Вы можете воспользоваться этим контейнером сборки или протестировать его, запустив его на компьютере разработки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-250">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="76dc6-251">Но еще интереснее то, что можно использовать один и тот же контейнер сборки из конвейера CI (непрерывной интеграции).</span><span class="sxs-lookup"><span data-stu-id="76dc6-251">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="76dc6-252">**Рис. 8-13**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-252">**Figure 8-13**.</span></span> <span data-ttu-id="76dc6-253">Контейнер сборки Docker, компилирующий двоичные файлы .NET</span><span class="sxs-lookup"><span data-stu-id="76dc6-253">Docker build-container compiling your .NET binaries</span></span> 

<span data-ttu-id="76dc6-254">Для этого сценария мы предоставляем образ [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/), который можно использовать для компиляции и сборки приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="76dc6-254">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="76dc6-255">Результат помещается в образ на основе образа [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/), который представляет собой оптимизированный образ среды выполнения, как указано выше.</span><span class="sxs-lookup"><span data-stu-id="76dc6-255">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="76dc6-256">Образ aspnetcore-build содержит все необходимое для компиляции приложения ASP.NET Core, включая .NET Core, пакет SDK ASP.NET, npm, Bower, Gulp и т. д.</span><span class="sxs-lookup"><span data-stu-id="76dc6-256">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="76dc6-257">Эти зависимости необходимы во время сборки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-257">We need these dependencies at build time.</span></span> <span data-ttu-id="76dc6-258">Но мы не хотим переносить их с приложением в среду выполнения, так как это сделает образ излишне большим.</span><span class="sxs-lookup"><span data-stu-id="76dc6-258">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="76dc6-259">В приложении eShopOnContainers можно собрать приложение из контейнера, просто выполнив следующую команду docker-compose.</span><span class="sxs-lookup"><span data-stu-id="76dc6-259">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="76dc6-260">На рисунке 8-14 показана эта команда, которая выполняется из командной строки.</span><span class="sxs-lookup"><span data-stu-id="76dc6-260">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="76dc6-261">**Рис. 8-14**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-261">**Figure 8-14.**</span></span> <span data-ttu-id="76dc6-262">Сборка приложения .NET из контейнера</span><span class="sxs-lookup"><span data-stu-id="76dc6-262">Building your .NET application from a container</span></span>

<span data-ttu-id="76dc6-263">Как можно видеть, выполняется контейнер ci-build\_1.</span><span class="sxs-lookup"><span data-stu-id="76dc6-263">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="76dc6-264">Это основывается на образе aspnetcore-build, чтобы можно было выполнять компиляцию и сборку всего приложения из этого контейнера, а не с ПК.</span><span class="sxs-lookup"><span data-stu-id="76dc6-264">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="76dc6-265">Вот почему на самом деле сборка и компиляция проектов .NET Core выполняется в Linux — потому что этот контейнер выполняется на узле Docker Linux по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="76dc6-265">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="76dc6-266">Файл [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) для этого образа (часть eShopOnContainers) содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="76dc6-266">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="76dc6-267">Вы видите, что он запускает контейнер сборки с помощью образа [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/).</span><span class="sxs-lookup"><span data-stu-id="76dc6-267">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

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

* <span data-ttu-id="76dc6-268">Начиная с **.NET Core 2.0**, команда `dotnet restore` выполняется автоматически при выполнении команды `dotnet publish`.</span><span class="sxs-lookup"><span data-stu-id="76dc6-268">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="76dc6-269">Когда контейнер сборки запустился и начал работать, он выполняет команды dotnet restore и dotnet publish пакета SDK .NET для всех проектов в решении, чтобы скомпилировать биты .NET.</span><span class="sxs-lookup"><span data-stu-id="76dc6-269">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="76dc6-270">В данном случае, поскольку приложение eShopOnContainers также имеет SPA на основе TypeScript и Angular для клиентского кода, ему, в свою очередь, необходимо проверить зависимости JavaScript с помощью команды npm, но это действие не связано с битами .NET.</span><span class="sxs-lookup"><span data-stu-id="76dc6-270">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="76dc6-271">Команда dotnet publish выполняет сборку и публикует скомпилированные выходные данные в каждой папке проекта в папку ../obj/Docker/publish, как показано на рисунке 8-15.</span><span class="sxs-lookup"><span data-stu-id="76dc6-271">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="76dc6-272">**Рис. 8-15**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-272">**Figure 8-15.**</span></span> <span data-ttu-id="76dc6-273">Двоичные файлы, созданные командой dotnet publish</span><span class="sxs-lookup"><span data-stu-id="76dc6-273">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="76dc6-274">Создание образов Docker из CLI</span><span class="sxs-lookup"><span data-stu-id="76dc6-274">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="76dc6-275">После публикации выходных данных приложения в связанных папках (в каждом проекте) следующий шаг заключается в фактическом создании образов Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-275">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="76dc6-276">Для этого используются команды docker-compose build и docker-compose up, как показано на рисунке 8-16.</span><span class="sxs-lookup"><span data-stu-id="76dc6-276">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="76dc6-277">**Рис. 8-16**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-277">**Figure 8-16.**</span></span> <span data-ttu-id="76dc6-278">Создание образов Docker и запуск контейнеров</span><span class="sxs-lookup"><span data-stu-id="76dc6-278">Building Docker images and running the containers</span></span>

<span data-ttu-id="76dc6-279">На рисунке 8-17 показано, как выполняется команда docker-compose build.</span><span class="sxs-lookup"><span data-stu-id="76dc6-279">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="76dc6-280">**Рис. 8-17**.</span><span class="sxs-lookup"><span data-stu-id="76dc6-280">**Figure 8-17**.</span></span> <span data-ttu-id="76dc6-281">Создание образов Docker с помощью команды docker-compose build</span><span class="sxs-lookup"><span data-stu-id="76dc6-281">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="76dc6-282">Различие между командами docker-compose build и docker-compose up состоит в том, что команда docker-compose up и создает, и запускает образы.</span><span class="sxs-lookup"><span data-stu-id="76dc6-282">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="76dc6-283">При использовании Visual Studio все эти действия выполняются внутренним образом.</span><span class="sxs-lookup"><span data-stu-id="76dc6-283">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="76dc6-284">Visual Studio компилирует приложение .NET, создает образы Docker и развертывает контейнеры в узле Docker.</span><span class="sxs-lookup"><span data-stu-id="76dc6-284">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="76dc6-285">Visual Studio предлагает дополнительные функциональные возможности, такие как возможность отладки контейнеров, работающих в Docker, непосредственно из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="76dc6-285">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="76dc6-286">Общий вывод заключается в том, что вы можете выполнять сборку приложения таким же образом, каким должен выполнять его сборку ваш конвейер CI/CD — из контейнера, а не с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="76dc6-286">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="76dc6-287">После создания образов остается только запустить эти образы Docker с помощью команды docker-compose up.</span><span class="sxs-lookup"><span data-stu-id="76dc6-287">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="76dc6-288">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="76dc6-288">Additional resources</span></span>

-   <span data-ttu-id="76dc6-289">**Создание битов в контейнере. Настройка решения eShopOnContainers в среде Windows CLI (dotnet CLI, Docker CLI и VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="76dc6-289">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="76dc6-290">[Назад](data-driven-crud-microservice.md)
[Вперед](database-server-container.md)</span><span class="sxs-lookup"><span data-stu-id="76dc6-290">[Previous](data-driven-crud-microservice.md)
[Next](database-server-container.md)</span></span>
