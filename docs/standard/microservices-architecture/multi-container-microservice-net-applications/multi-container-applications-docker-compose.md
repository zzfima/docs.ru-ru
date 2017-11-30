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
# <a name="defining-your-multi-container-application-with-docker-composeyml"></a><span data-ttu-id="94fe3-104">Определение приложения несколькими контейнера с docker compose.yml</span><span class="sxs-lookup"><span data-stu-id="94fe3-104">Defining your multi-container application with docker-compose.yml</span></span> 

<span data-ttu-id="94fe3-105">В этом руководстве [docker compose.yml](https://docs.docker.com/compose/compose-file/) файла была представлена в разделе [шаг 4. Определение службы в docker compose.yml при построении приложения несколькими контейнера Docker](#step4_define_svcs_in_docker_compose_yml).</span><span class="sxs-lookup"><span data-stu-id="94fe3-105">In this guide, the [docker-compose.yml](https://docs.docker.com/compose/compose-file/) file was introduced in the section [Step 4. Define your services in docker-compose.yml when building a multi-container Docker application](#step4_define_svcs_in_docker_compose_yml).</span></span> <span data-ttu-id="94fe3-106">Тем не менее существуют дополнительные способы использования docker-compose файлы, которые являются более подробно исследовать.</span><span class="sxs-lookup"><span data-stu-id="94fe3-106">However, there are additional ways to use the docker-compose files that are worth exploring in further detail.</span></span>

<span data-ttu-id="94fe3-107">Например можно явно описать способ развертывания приложения в файле docker compose.yml несколькими контейнера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-107">For example, you can explicitly describe how you want to deploy your multi-container application in the docker-compose.yml file.</span></span> <span data-ttu-id="94fe3-108">При необходимости также можно описать, как необходимо для построения пользовательских образов Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-108">Optionally, you can also describe how you are going to build your custom Docker images.</span></span> <span data-ttu-id="94fe3-109">(Пользовательские образы Docker можно также создавать с помощью Docker CLI.)</span><span class="sxs-lookup"><span data-stu-id="94fe3-109">(Custom Docker images can also be built with the Docker CLI.)</span></span>

<span data-ttu-id="94fe3-110">По сути определение каждого из контейнеров, которые требуется развернуть, а также определенные характеристики для каждого развертывания контейнера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-110">Basically, you define each of the containers you want to deploy plus certain characteristics for each container deployment.</span></span> <span data-ttu-id="94fe3-111">Как только файл описания развертывание нескольких контейнера, можно развернуть все решение в рамках одной операции, под управлением [docker создания копии](https://docs.docker.com/compose/overview/) команду CLI, или его можно развернуть прозрачно с Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94fe3-111">Once you have a multi-container deployment description file, you can deploy the whole solution in a single action orchestrated by the [docker-compose up](https://docs.docker.com/compose/overview/) CLI command, or you can deploy it transparently from Visual Studio.</span></span> <span data-ttu-id="94fe3-112">В противном случае необходимо использовать Docker CLI для развертывания контейнера в несколько этапов с помощью docker, выполните команду из командной строки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-112">Otherwise, you would need to use the Docker CLI to deploy container-by-container in multiple steps by using the docker run command from the command line.</span></span> <span data-ttu-id="94fe3-113">Таким образом каждой службы, определенной в docker compose.yml необходимо указать ровно одно изображение или сборки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-113">Therefore, each service defined in docker-compose.yml must specify exactly one image or build.</span></span> <span data-ttu-id="94fe3-114">Остальные ключи являются необязательными и аналогичны их docker, запустите аналогами из командной строки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-114">Other keys are optional, and are analogous to their docker run command-line counterparts.</span></span>

<span data-ttu-id="94fe3-115">В следующем примере кода YAML является определением файла невозможно, но один глобальный docker-compose.yml eShopOnContainers образца.</span><span class="sxs-lookup"><span data-stu-id="94fe3-115">The following YAML code is the definition of a possible global but single docker-compose.yml file for the eShopOnContainers sample.</span></span> <span data-ttu-id="94fe3-116">Это не фактический docker-compose файл из eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="94fe3-116">This is not the actual docker-compose file from eShopOnContainers.</span></span> <span data-ttu-id="94fe3-117">Вместо этого это версия упрощенной и объединенные в один файл, который не является наиболее подходящий способ работы с docker составить файлы, как будет описано ниже.</span><span class="sxs-lookup"><span data-stu-id="94fe3-117">Instead, it is a simplified and consolidated version in a single file, which is not the best way to work with docker-compose files, as will be explained later.</span></span>

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

<span data-ttu-id="94fe3-118">Корневой ключ в этом файле — служб.</span><span class="sxs-lookup"><span data-stu-id="94fe3-118">The root key in this file is services.</span></span> <span data-ttu-id="94fe3-119">В данном разделе определения службы, нужно развернуть и запустить при выполнении docker составлять команды или при развертывании из Visual Studio с помощью этого файла docker compose.yml.</span><span class="sxs-lookup"><span data-stu-id="94fe3-119">Under that key you define the services you want to deploy and run when you execute the docker-compose up command or when you deploy from Visual Studio by using this docker-compose.yml file.</span></span> <span data-ttu-id="94fe3-120">В этом случае файл docker compose.yml имеет несколько служб, которые определены, как описано в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="94fe3-120">In this case, the docker-compose.yml file has multiple services defined, as described in the following list.</span></span>

-   <span data-ttu-id="94fe3-121">webmvc контейнера, включая приложения ASP.NET Core MVC, использование микрослужбами из C на стороне сервера\#</span><span class="sxs-lookup"><span data-stu-id="94fe3-121">webmvc Container including the ASP.NET Core MVC application consuming the microservices from server-side C\#</span></span>

-   <span data-ttu-id="94fe3-122">Catalog.API контейнера, включая микрослужбу каталога ASP.NET Core веб-API</span><span class="sxs-lookup"><span data-stu-id="94fe3-122">catalog.api Container including the Catalog ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="94fe3-123">Ordering.API контейнера, включая микрослужбу упорядочение веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="94fe3-123">ordering.api Container including the Ordering ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="94fe3-124">SQL.Data контейнер с SQL Server для Linux, удерживая микрослужбами баз данных</span><span class="sxs-lookup"><span data-stu-id="94fe3-124">sql.data Container running SQL Server for Linux, holding the microservices databases</span></span>

-   <span data-ttu-id="94fe3-125">Basket.API контейнер с микрослужбу корзины ASP.NET Core веб-API</span><span class="sxs-lookup"><span data-stu-id="94fe3-125">basket.api Container with the Basket ASP.NET Core Web API microservice</span></span>

-   <span data-ttu-id="94fe3-126">Basket.Data контейнера, запущенного служба кэша REDIS корзины базы данных в качестве кэша REDIS</span><span class="sxs-lookup"><span data-stu-id="94fe3-126">basket.data Container running the REDIS cache service, with the basket database as a REDIS cache</span></span>

### <a name="a-simple-web-service-api-container"></a><span data-ttu-id="94fe3-127">Простой контейнер API веб-службы</span><span class="sxs-lookup"><span data-stu-id="94fe3-127">A simple Web Service API container</span></span>

<span data-ttu-id="94fe3-128">Сосредоточившись на один контейнер catalog.api контейнера микрослужбу имеет простой определение:</span><span class="sxs-lookup"><span data-stu-id="94fe3-128">Focusing on a single container, the catalog.api container-microservice has a straightforward definition:</span></span>

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

<span data-ttu-id="94fe3-129">Контейнерного сервисе следующей базовой конфигурацией:</span><span class="sxs-lookup"><span data-stu-id="94fe3-129">This containerized service has the following basic configuration:</span></span>

-   <span data-ttu-id="94fe3-130">Он основан на eshop/catalog.api пользовательского образа.</span><span class="sxs-lookup"><span data-stu-id="94fe3-130">It is based on the custom eshop/catalog.api image.</span></span> <span data-ttu-id="94fe3-131">Чтобы упростить понимание является построение: параметр в файле ключа.</span><span class="sxs-lookup"><span data-stu-id="94fe3-131">For simplicity’s sake, there is no build: key setting in the file.</span></span> <span data-ttu-id="94fe3-132">Это означает, что образ должен был ранее создавали (с сборка docker), или были загружены (командой docker pull) из любой реестра Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-132">This means that the image must have been previously built (with docker build) or have been downloaded (with the docker pull command) from any Docker registry.</span></span>

-   <span data-ttu-id="94fe3-133">Он определяет переменную среды с именем "ConnectionString" в строке подключения для использования платформы Entity Framework для доступа к экземпляру SQL Server, содержащий модель данных каталога.</span><span class="sxs-lookup"><span data-stu-id="94fe3-133">It defines an environment variable named ConnectionString with the connection string to be used by Entity Framework to access the SQL Server instance that contains the catalog data model.</span></span> <span data-ttu-id="94fe3-134">В этом случае один и тот же контейнер SQL Server содержится несколько баз данных.</span><span class="sxs-lookup"><span data-stu-id="94fe3-134">In this case, the same SQL Server container is holding multiple databases.</span></span> <span data-ttu-id="94fe3-135">Таким образом требуется меньше памяти в компьютере разработки для Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-135">Therefore, you need less memory in your development machine for Docker.</span></span> <span data-ttu-id="94fe3-136">Однако можно также развернуть один контейнер SQL Server для каждой базы данных микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-136">However, you could also deploy one SQL Server container for each microservice database.</span></span>

-   <span data-ttu-id="94fe3-137">Имя SQL Server — sql.data, это же имя, используемое для контейнера, на котором выполняется экземпляр SQL Server для Linux.</span><span class="sxs-lookup"><span data-stu-id="94fe3-137">The SQL Server name is sql.data, which is the same name used for the container that is running the SQL Server instance for Linux.</span></span> <span data-ttu-id="94fe3-138">Это удобно; сетевой адрес разрешается в возможность использования этого разрешения имен (внутренний узел Docker), вам требуется знать внутренний IP-адрес для контейнеров, запрашиваемых от других контейнеров.</span><span class="sxs-lookup"><span data-stu-id="94fe3-138">This is convenient; being able to use this name resolution (internal to the Docker host) will resolve the network address so you don’t need to know the internal IP for the containers you are accessing from other containers.</span></span>

<span data-ttu-id="94fe3-139">Так как строка подключения определяется переменной среды, можно задать эту переменную посредством другого механизма и в другое время.</span><span class="sxs-lookup"><span data-stu-id="94fe3-139">Because the connection string is defined by an environment variable, you could set that variable through a different mechanism and at a different time.</span></span> <span data-ttu-id="94fe3-140">Например можно задать другую строку соединения при развертывании в рабочей среде, в окончательной узлов или выполнив из конвейеры CI/CD в VSTS или предпочтительный DevOps системы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-140">For example, you could set a different connection string when deploying to production in the final hosts, or by doing it from your CI/CD pipelines in VSTS or your preferred DevOps system.</span></span>

-   <span data-ttu-id="94fe3-141">Он предоставляет порт 80 для внутреннего доступа к службе catalog.api узел Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-141">It exposes port 80 for internal access to the catalog.api service within the Docker host.</span></span> <span data-ttu-id="94fe3-142">Этот узел является виртуальной Машины Linux, так как оно зависит от образа Docker для Linux, но можно настроить контейнер для запуска в образ Windows, вместо этого.</span><span class="sxs-lookup"><span data-stu-id="94fe3-142">The host is currently a Linux VM because it is based on a Docker image for Linux, but you could configure the container to run on a Windows image instead.</span></span>

-   <span data-ttu-id="94fe3-143">Она передает предоставленный порт 80 для контейнера с портом 5101 на хост-компьютере Docker (виртуальной Машине Linux).</span><span class="sxs-lookup"><span data-stu-id="94fe3-143">It forwards the exposed port 80 on the container to port 5101 on the Docker host machine (the Linux VM).</span></span>

-   <span data-ttu-id="94fe3-144">Ссылки на службу sql.data (экземпляр SQL Server для Linux базы данных, запущенные в контейнере) веб-службы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-144">It links the web service to the sql.data service (the SQL Server instance for Linux database running in a container).</span></span> <span data-ttu-id="94fe3-145">При указании этой зависимости catalog.api контейнера не будет начата до начала sql.data контейнера; Это важно, поскольку catalog.api должен иметь базы данных SQL Server и запущена сначала.</span><span class="sxs-lookup"><span data-stu-id="94fe3-145">When you specify this dependency, the catalog.api container will not start until the sql.data container has already started; this is important because catalog.api needs to have the SQL Server database up and running first.</span></span> <span data-ttu-id="94fe3-146">Тем не менее этого вида зависимостей контейнера недостаточно во многих случаях потому, что Docker проверяет только на уровне контейнера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-146">However, this kind of container dependency is not enough in many cases, because Docker checks only at the container level.</span></span> <span data-ttu-id="94fe3-147">Иногда (в этом вариантов SQL Server) по-прежнему не возможно, служба готова, поэтому рекомендуется реализовать логику повторных попыток с экспоненциально растущим в микрослужбами вашего клиента.</span><span class="sxs-lookup"><span data-stu-id="94fe3-147">Sometimes the service (in this case SQL Server) might still not be ready, so it is advisable to implement retry logic with exponential backoff in your client microservices.</span></span> <span data-ttu-id="94fe3-148">Таким образом, если контейнер зависимостей не готов в течение некоторого времени, приложение по-прежнему будет устойчивыми.</span><span class="sxs-lookup"><span data-stu-id="94fe3-148">That way, if a dependency container is not ready for a short time, the application will still be resilient.</span></span>

-   <span data-ttu-id="94fe3-149">Он настроен для разрешения доступа к внешним серверам: дополнительного\_параметр узлов позволяет получить доступ к внешним серверам или машины за пределами узла Docker (то есть за пределами виртуальных Машин Linux, который Docker разработки по умолчанию размещения), например локального SQL Экземпляр сервера на Компьютере разработки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-149">It is configured to allow access to external servers: the extra\_hosts setting allows you to access external servers or machines outside of the Docker host (that is, outside the default Linux VM which is a development Docker host), such as a local SQL Server instance on your development PC.</span></span>

<span data-ttu-id="94fe3-150">Также существуют другие, дополнительные параметры docker compose.yml, которые обсуждаются в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="94fe3-150">There are also other, more advanced docker-compose.yml settings that we will discuss in the following sections.</span></span>

### <a name="using-docker-compose-files-to-target-multiple-environments"></a><span data-ttu-id="94fe3-151">С помощью docker составить файлы для нескольких сред</span><span class="sxs-lookup"><span data-stu-id="94fe3-151">Using docker-compose files to target multiple environments</span></span>

<span data-ttu-id="94fe3-152">Файлы docker compose.yml файлы определения и могут использоваться несколько инфраструктур, которые распознает этот формат.</span><span class="sxs-lookup"><span data-stu-id="94fe3-152">The docker-compose.yml files are definition files and can be used by multiple infrastructures that understand that format.</span></span> <span data-ttu-id="94fe3-153">Средство самый простой — docker-создание команды, но другие средства, как orchestrators (например, помощью Docker Swarm) также знание этого файла.</span><span class="sxs-lookup"><span data-stu-id="94fe3-153">The most straightforward tool is the docker-compose command, but other tools like orchestrators (for example, Docker Swarm) also understand that file.</span></span>

<span data-ttu-id="94fe3-154">Таким образом, с помощью docker создание команды ориентировании следующих основных сценариев.</span><span class="sxs-lookup"><span data-stu-id="94fe3-154">Therefore, by using the docker-compose command you can target the following main scenarios.</span></span>

#### <a name="development-environments"></a><span data-ttu-id="94fe3-155">Для сред разработки</span><span class="sxs-lookup"><span data-stu-id="94fe3-155">Development environments</span></span>

<span data-ttu-id="94fe3-156">При разработке приложений важно иметь возможность запускать приложения в изолированной среде разработки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-156">When you develop applications, it is important to be able to run an application in an isolated development environment.</span></span> <span data-ttu-id="94fe3-157">Можно использовать команду CLI для создания этой среды или использовать Visual Studio, которая использует docker составления на самом деле составления docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-157">You can use the docker-compose CLI command to create that environment or use Visual Studio which uses docker-compose under the covers.</span></span>

<span data-ttu-id="94fe3-158">В файле docker compose.yml можно настроить и задокументировать все зависимости приложения от службы (других служб, кэша, базы данных, очереди, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="94fe3-158">The docker-compose.yml file allows you to configure and document all your application’s service dependencies (other services, cache, databases, queues, etc.).</span></span> <span data-ttu-id="94fe3-159">С помощью docker составить команду CLI, можно создать и запустить один или несколько контейнеров для каждой зависимости, с помощью одной команды (docker составления вверх).</span><span class="sxs-lookup"><span data-stu-id="94fe3-159">Using the docker-compose CLI command, you can create and start one or more containers for each dependency with a single command (docker-compose up).</span></span>

<span data-ttu-id="94fe3-160">Это файлы конфигурации, интерпретируемые подсистемой Docker docker compose.yml, но также выступать в качестве файлов удобный документации о структуре приложения несколькими контейнера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-160">The docker-compose.yml files are configuration files interpreted by Docker engine but also serve as convenient documentation files about the composition of your multi-container application.</span></span>

#### <a name="testing-environments"></a><span data-ttu-id="94fe3-161">В средах тестирования</span><span class="sxs-lookup"><span data-stu-id="94fe3-161">Testing environments</span></span>

<span data-ttu-id="94fe3-162">Модульные тесты и тесты интеграции, являются важной частью процесса непрерывного развертывания (CD) ни один процесс непрерывной интеграции (CI).</span><span class="sxs-lookup"><span data-stu-id="94fe3-162">An important part of any continuous deployment (CD) or continuous integration (CI) process are the unit tests and integration tests.</span></span> <span data-ttu-id="94fe3-163">Эти автоматические тесты требуются изолированной среде, поэтому они не затрагивает пользователей или любое другое изменение данных в приложении.</span><span class="sxs-lookup"><span data-stu-id="94fe3-163">These automated tests require an isolated environment so they are not impacted by the users or any other change in the application’s data.</span></span>

<span data-ttu-id="94fe3-164">С помощью Docker Compose можно создавать и уничтожать, изолированную среду очень легко нескольких команд из командной строки или сценариев, таких как следующие команды:</span><span class="sxs-lookup"><span data-stu-id="94fe3-164">With Docker Compose you can create and destroy that isolated environment very easily in a few commands from your command prompt or scripts, like the following commands:</span></span>

```
docker-compose up -d
./run_unit_tests
docker-compose down
```

#### <a name="production-deployments"></a><span data-ttu-id="94fe3-165">В производственных развертываниях</span><span class="sxs-lookup"><span data-stu-id="94fe3-165">Production deployments</span></span>

<span data-ttu-id="94fe3-166">Также можно создать для развертывания на удаленных подсистемы Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-166">You can also use Compose to deploy to a remote Docker Engine.</span></span> <span data-ttu-id="94fe3-167">Типичный случай — развернуть один экземпляр узла Docker (как в рабочей среде виртуальной Машины или на сервере, предоставлен [машины Docker](https://docs.docker.com/machine/overview/)).</span><span class="sxs-lookup"><span data-stu-id="94fe3-167">A typical case is to deploy to a single Docker host instance (like a production VM or server provisioned with [Docker Machine](https://docs.docker.com/machine/overview/)).</span></span> <span data-ttu-id="94fe3-168">Но это также может быть весь [помощью Docker Swarm](https://docs.docker.com/swarm/overview/) кластера, так как кластеры также совместимы с файлами docker compose.yml.</span><span class="sxs-lookup"><span data-stu-id="94fe3-168">But it could also be an entire [Docker Swarm](https://docs.docker.com/swarm/overview/) cluster, because clusters are also compatible with the docker-compose.yml files.</span></span>

<span data-ttu-id="94fe3-169">При использовании других orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, т. д.), может потребоваться добавить настройки и метаданные параметры конфигурации, как в docker compose.yml, но в формат, требуемый других orchestrator.</span><span class="sxs-lookup"><span data-stu-id="94fe3-169">If you are using any other orchestrator (Azure Service Fabric, Mesos DC/OS, Kubernetes, etc.), you might need to add setup and metadata configuration settings like those in docker-compose.yml, but in the format required by the other orchestrator.</span></span>

<span data-ttu-id="94fe3-170">В любом случае составления docker является удобный формат средства и метаданные для рабочих процессов разработки, тестирования и эксплуатации, несмотря на то, что рабочем процессе могут различаться на использовании orchestrator.</span><span class="sxs-lookup"><span data-stu-id="94fe3-170">In any case, docker-compose is a convenient tool and metadata format for development, testing and production workflows, although the production workflow might vary on the orchestrator you are using.</span></span>

### <a name="using-multiple-docker-compose-files-to-handle-several-environments"></a><span data-ttu-id="94fe3-171">С помощью нескольких docker составить файлы для обработки нескольких сред</span><span class="sxs-lookup"><span data-stu-id="94fe3-171">Using multiple docker-compose files to handle several environments</span></span>

<span data-ttu-id="94fe3-172">При разработке для различных сред, следует использовать несколько составить файлы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-172">When targeting different environments, you should use multiple compose files.</span></span> <span data-ttu-id="94fe3-173">Это позволяет создавать несколько вариантов конфигурации, в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="94fe3-173">This lets you create multiple configuration variants depending on the environment.</span></span>

#### <a name="overriding-the-base-docker-compose-file"></a><span data-ttu-id="94fe3-174">Переопределение базового docker-compose файла</span><span class="sxs-lookup"><span data-stu-id="94fe3-174">Overriding the base docker-compose file</span></span>

<span data-ttu-id="94fe3-175">Можно использовать файл одного docker-compose.yml как упрощенный примеры, приведенные в предыдущих разделах.</span><span class="sxs-lookup"><span data-stu-id="94fe3-175">You could use a single docker-compose.yml file as in the simplified examples shown in previous sections.</span></span> <span data-ttu-id="94fe3-176">Тем не менее, не рекомендуется для большинства приложений.</span><span class="sxs-lookup"><span data-stu-id="94fe3-176">However, that is not recommended for most applications.</span></span>

<span data-ttu-id="94fe3-177">По умолчанию создать считывает два файла, docker-compose.yml и необязательный docker-compose.override.yml файла.</span><span class="sxs-lookup"><span data-stu-id="94fe3-177">By default, Compose reads two files, a docker-compose.yml and an optional docker-compose.override.yml file.</span></span> <span data-ttu-id="94fe3-178">Как показано в на рисунке 8 по 11, если вы используете Visual Studio и включение поддержки Docker, Visual Studio также создает эти файлы, а также некоторые дополнительные файлы, используемые для отладки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-178">As shown in Figure 8-11, when you are using Visual Studio and enabling Docker support, Visual Studio also creates those files plus some additional files used for debugging.</span></span>

![](./media/image12.png)

<span data-ttu-id="94fe3-179">**На рисунке 8 по 11**.</span><span class="sxs-lookup"><span data-stu-id="94fe3-179">**Figure 8-11**.</span></span> <span data-ttu-id="94fe3-180">docker создания файлов в Visual Studio 2017 г.</span><span class="sxs-lookup"><span data-stu-id="94fe3-180">docker-compose files in Visual Studio 2017</span></span>

<span data-ttu-id="94fe3-181">Можно изменить с помощью любого редактора, таких как Visual Studio Code или Sublime, docker-compose файлов и запуск приложения с docker составления up команд.</span><span class="sxs-lookup"><span data-stu-id="94fe3-181">You can edit the docker-compose files with any editor, like Visual Studio Code or Sublime, and run the application with the docker-compose up command.</span></span>

<span data-ttu-id="94fe3-182">По соглашению файл docker compose.yml содержит базовой конфигурации и других статических параметров.</span><span class="sxs-lookup"><span data-stu-id="94fe3-182">By convention, the docker-compose.yml file contains your base configuration and other static settings.</span></span> <span data-ttu-id="94fe3-183">Это означает, что в зависимости от среды развертывания, который вы используете, не изменяйте конфигурацию службы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-183">That means that the service configuration should not change depending on the deployment environment you are targeting.</span></span>

<span data-ttu-id="94fe3-184">Файл docker compose.override.yml названия, содержит параметры конфигурации, которые переопределяют базовой конфигурации, такие как конфигурация, которая зависит от среды развертывания.</span><span class="sxs-lookup"><span data-stu-id="94fe3-184">The docker-compose.override.yml file, as its name suggests, contains configuration settings that override the base configuration, such as configuration that depends on the deployment environment.</span></span> <span data-ttu-id="94fe3-185">Также может иметь несколько переопределение файлов с разными именами.</span><span class="sxs-lookup"><span data-stu-id="94fe3-185">You can have multiple override files with different names also.</span></span> <span data-ttu-id="94fe3-186">Переопределение файлы обычно содержат дополнительные сведения, необходимые для приложения, кроме определенного среды или развертывание.</span><span class="sxs-lookup"><span data-stu-id="94fe3-186">The override files usually contain additional information needed by the application but specific to an environment or to a deployment.</span></span>

#### <a name="targeting-multiple-environments"></a><span data-ttu-id="94fe3-187">Предназначенных для нескольких сред</span><span class="sxs-lookup"><span data-stu-id="94fe3-187">Targeting multiple environments</span></span>

<span data-ttu-id="94fe3-188">Типичный случай использования является при определении нескольких образуют файлов позволяет разрабатывать несколько сред, таких как производство, промежуточное хранение CI или разработки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-188">A typical use case is when you define multiple compose files so you can target multiple environments, like production, staging, CI, or development.</span></span> <span data-ttu-id="94fe3-189">Для поддержки этих различий, вы можете разделить создать конфигурацию на несколько файлов, как показано на рисунке 8-12.</span><span class="sxs-lookup"><span data-stu-id="94fe3-189">To support these differences, you can split your Compose configuration into multiple files, as shown in Figure 8-12.</span></span>

![](./media/image13.png)

<span data-ttu-id="94fe3-190">**Рис. 8-12**.</span><span class="sxs-lookup"><span data-stu-id="94fe3-190">**Figure 8-12**.</span></span> <span data-ttu-id="94fe3-191">Несколько docker составления переопределение значений в файле базового docker-compose.yml файлов</span><span class="sxs-lookup"><span data-stu-id="94fe3-191">Multiple docker-compose files overriding values in the base docker-compose.yml file</span></span>

<span data-ttu-id="94fe3-192">Начните с базового docker-compose.yml файла.</span><span class="sxs-lookup"><span data-stu-id="94fe3-192">You start with the base docker-compose.yml file.</span></span> <span data-ttu-id="94fe3-193">Этот базовый файл должен содержать базовый или статические параметры, которые не изменяются в зависимости от среды.</span><span class="sxs-lookup"><span data-stu-id="94fe3-193">This base file has to contain the base or static configuration settings that do not change depending on the environment.</span></span> <span data-ttu-id="94fe3-194">Например eShopOnContainers имеет следующий файл docker compose.yml как основного файла.</span><span class="sxs-lookup"><span data-stu-id="94fe3-194">For example, the eShopOnContainers has the following docker-compose.yml file as the base file.</span></span>

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

<span data-ttu-id="94fe3-195">Не следует изменять значения в файле базового docker-compose.yml из-за различных целевых средах развертывания.</span><span class="sxs-lookup"><span data-stu-id="94fe3-195">The values in the base docker-compose.yml file should not change because of different target deployment environments.</span></span>

<span data-ttu-id="94fe3-196">Если установить фокус на webmvc определение службы, для экземпляра, вы увидите как эти сведения будут так же, независимо от того, какой среде вы может выделить.</span><span class="sxs-lookup"><span data-stu-id="94fe3-196">If you focus on the webmvc service definition, for instance, you can see how that information is much the same no matter what environment you might be targeting.</span></span> <span data-ttu-id="94fe3-197">У вас есть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="94fe3-197">You have the following information:</span></span>

-   <span data-ttu-id="94fe3-198">Имя службы: webmvc.</span><span class="sxs-lookup"><span data-stu-id="94fe3-198">The service name: webmvc.</span></span>

-   <span data-ttu-id="94fe3-199">Пользовательский образ контейнера: eshop/webmvc.</span><span class="sxs-lookup"><span data-stu-id="94fe3-199">The container’s custom image: eshop/webmvc.</span></span>

-   <span data-ttu-id="94fe3-200">Команда для создания пользовательского образа Docker, позволяющее определить, какой файл Dockerfile для использования.</span><span class="sxs-lookup"><span data-stu-id="94fe3-200">The command to build the custom Docker image, indicating which Dockerfile to use.</span></span>

-   <span data-ttu-id="94fe3-201">В зависимости от других служб, поэтому данный контейнер не будет начата до запуска других контейнеров зависимостей.</span><span class="sxs-lookup"><span data-stu-id="94fe3-201">Dependencies on other services, so this container does not start until the other dependency containers have started.</span></span>

<span data-ttu-id="94fe3-202">Имеется дополнительная настройка, но важно то, что в файле базового docker-compose.yml необходимо просто задать информацию, которая является общей для нескольких сред.</span><span class="sxs-lookup"><span data-stu-id="94fe3-202">You can have additional configuration, but the important point is that in the base docker-compose.yml file, you just want to set the information that is common across environments.</span></span> <span data-ttu-id="94fe3-203">Затем в docker compose.override.yml или аналогичных файлов для производственного или промежуточного хранения, необходимо поместить конфигурации, характерное для каждой среды.</span><span class="sxs-lookup"><span data-stu-id="94fe3-203">Then in the docker-compose.override.yml or similar files for production or staging, you should place configuration that is specific for each environment.</span></span>

<span data-ttu-id="94fe3-204">Docker — compose.override.yml, обычно используется для среды разработки, как показано в следующем примере из eShopOnContainers:</span><span class="sxs-lookup"><span data-stu-id="94fe3-204">Usually, the docker-compose.override.yml is used for your development environment, as in the following example from eShopOnContainers:</span></span>

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

<span data-ttu-id="94fe3-205">В этом примере конфигурации переопределение разработки предоставляет некоторые порты на узел, определяет переменные среды с перенаправления URL-адресов, а также определяет строки подключения для среды разработки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-205">In this example, the development override configuration exposes some ports to the host, defines environment variables with redirect URLs, and specifies connection strings for the development environment.</span></span> <span data-ttu-id="94fe3-206">Эти параметры используются все, что для среды разработки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-206">These settings are all just for the development environment.</span></span>

<span data-ttu-id="94fe3-207">При запуске docker составить вверх (или запустите его из Visual Studio), команда считывает переопределения автоматически как если бы он объединение обоих файлов.</span><span class="sxs-lookup"><span data-stu-id="94fe3-207">When you run docker-compose up (or launch it from Visual Studio), the command reads the overrides automatically as if it were merging both files.</span></span>

<span data-ttu-id="94fe3-208">Предположим, что вы хотите другой файл создания сообщения для рабочей среды, со значениями другой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="94fe3-208">Suppose that you want another Compose file for the production environment, with different configuration values.</span></span> <span data-ttu-id="94fe3-209">Можно создать другой файл переопределения, следующим образом.</span><span class="sxs-lookup"><span data-stu-id="94fe3-209">You can create another override file, like the following.</span></span> <span data-ttu-id="94fe3-210">(Этот файл может храниться в другой репозиторий Git или управляемые и защищены от другой команды.)</span><span class="sxs-lookup"><span data-stu-id="94fe3-210">(This file might be stored in a different Git repo or managed and secured by a different team.)</span></span>

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

#### <a name="how-to-deploy-with-a-specific-override-file"></a><span data-ttu-id="94fe3-211">Развертывание с помощью файла конкретного переопределения</span><span class="sxs-lookup"><span data-stu-id="94fe3-211">How to deploy with a specific override file</span></span>

<span data-ttu-id="94fe3-212">Чтобы использовать несколько файлов переопределение, или переопределение файл с другим именем, можно использовать параметр -f с docker создание команды и укажите файлы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-212">To use multiple override files, or an override file with a different name, you can use the -f option with the docker-compose command and specify the files.</span></span> <span data-ttu-id="94fe3-213">Создайте файлы слияний в порядке, в котором они указаны в командной строке.</span><span class="sxs-lookup"><span data-stu-id="94fe3-213">Compose merges files in the order they are specified on the command line.</span></span> <span data-ttu-id="94fe3-214">Приведенный ниже показано, как развертывать с помощью переопределения файлы.</span><span class="sxs-lookup"><span data-stu-id="94fe3-214">The following example shows how to deploy with override files.</span></span>

```
docker-compose -f docker-compose.yml -f docker-compose.prod.yml up -d
```

#### <a name="using-environment-variables-in-docker-compose-files"></a><span data-ttu-id="94fe3-215">Использование переменных среды в docker создания файлов</span><span class="sxs-lookup"><span data-stu-id="94fe3-215">Using environment variables in docker-compose files</span></span>

<span data-ttu-id="94fe3-216">Он является удобным, особенно в производственной среде, чтобы иметь возможность получать сведения о конфигурации из переменных среды, как было показано в предыдущих примерах.</span><span class="sxs-lookup"><span data-stu-id="94fe3-216">It is convenient, especially in production environments, to be able to get configuration information from environment variables, as we have shown in previous examples.</span></span> <span data-ttu-id="94fe3-217">Ссылки на переменные среды в файлах с помощью синтаксиса docker-compose \${MY\_VAR}.</span><span class="sxs-lookup"><span data-stu-id="94fe3-217">You reference an environment variable in your docker-compose files using the syntax \${MY\_VAR}.</span></span> <span data-ttu-id="94fe3-218">Следующая строка из файла docker compose.prod.yml показано, как для ссылки на значение переменной среды.</span><span class="sxs-lookup"><span data-stu-id="94fe3-218">The following line from a docker-compose.prod.yml file shows how to reference the value of an environment variable.</span></span>

```yml
IdentityUrl=http://${ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP}:5105
```

<span data-ttu-id="94fe3-219">Переменные среды создаются и инициализируются разными способами, в зависимости от среды узла (Linux, Windows, кластер облака, и т. д.).</span><span class="sxs-lookup"><span data-stu-id="94fe3-219">Environment variables are created and initialized in different ways, depending on your host environment (Linux, Windows, Cloud cluster, etc.).</span></span> <span data-ttu-id="94fe3-220">Однако удобный подход — использовать файл .env.</span><span class="sxs-lookup"><span data-stu-id="94fe3-220">However, a convenient approach is to use an .env file.</span></span> <span data-ttu-id="94fe3-221">Файлы docker-compose поддерживает объявление переменных среды по умолчанию в файле .env.</span><span class="sxs-lookup"><span data-stu-id="94fe3-221">The docker-compose files support declaring default environment variables in the .env file.</span></span> <span data-ttu-id="94fe3-222">Эти значения для переменных среды являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94fe3-222">These values for the environment variables are the default values.</span></span> <span data-ttu-id="94fe3-223">Однако они могут быть переопределены значения, которые определены в каждой из сред (операционной системе сервера или переменные среды из кластера).</span><span class="sxs-lookup"><span data-stu-id="94fe3-223">But they can be overridden by the values you might have defined in each of your environments (host OS or environment variables from your cluster).</span></span> <span data-ttu-id="94fe3-224">Поместить этот файл .env в той папке, где составления docker команда выполняется.</span><span class="sxs-lookup"><span data-stu-id="94fe3-224">You place this .env file in the folder where the docker-compose command is executed from.</span></span>

<span data-ttu-id="94fe3-225">В следующем примере показано файла .env как [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) файл eShopOnContainers приложения.</span><span class="sxs-lookup"><span data-stu-id="94fe3-225">The following example shows an .env file like the [.env](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/.env) file for the eShopOnContainers application.</span></span>

```
# .env file

ESHOP_EXTERNAL_DNS_NAME_OR_IP=localhost

ESHOP_PROD_EXTERNAL_DNS_NAME_OR_IP=10.121.122.92
```

<span data-ttu-id="94fe3-226">Составить docker ожидает, что каждая строка в файле .env, чтобы быть в формате &lt;переменной&gt;=&lt;значение&gt;.</span><span class="sxs-lookup"><span data-stu-id="94fe3-226">Docker-compose expects each line in an .env file to be in the format &lt;variable&gt;=&lt;value&gt;.</span></span>

<span data-ttu-id="94fe3-227">Обратите внимание, что значения, заданные в среде выполнения, всегда переопределяют значения, определенные в файле .env.</span><span class="sxs-lookup"><span data-stu-id="94fe3-227">Note that the values set in the runtime environment always override the values defined inside the .env file.</span></span> <span data-ttu-id="94fe3-228">Аналогичным образом значения, переданные аргументы командной строки также переопределить значения по умолчанию, заданные в файле .env.</span><span class="sxs-lookup"><span data-stu-id="94fe3-228">In a similar way, values passed via command-line command arguments also override the default values set in the .env file.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="94fe3-229">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="94fe3-229">Additional resources</span></span>

-   <span data-ttu-id="94fe3-230">**Общие сведения о Docker составления**
    [*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span><span class="sxs-lookup"><span data-stu-id="94fe3-230">**Overview of Docker Compose**
[*https://docs.docker.com/compose/overview/*](https://docs.docker.com/compose/overview/)</span></span>

-   <span data-ttu-id="94fe3-231">**Несколько файлов составление**
    [*https://docs.docker.com/compose/extends/\#составить файлы несколько*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span><span class="sxs-lookup"><span data-stu-id="94fe3-231">**Multiple Compose files**
[*https://docs.docker.com/compose/extends/\#multiple-compose-files*](https://docs.docker.com/compose/extends/#multiple-compose-files)</span></span>

### <a name="building-optimized-aspnet-core-docker-images"></a><span data-ttu-id="94fe3-232">Создание оптимизированных образов ASP.NET Core Docker</span><span class="sxs-lookup"><span data-stu-id="94fe3-232">Building optimized ASP.NET Core Docker images</span></span>

<span data-ttu-id="94fe3-233">Если вы исследуете Docker и .NET Core на источников в Интернете, вы обнаружите, что файлы Dockerfile, демонстрирующие Простота создания образа Docker, скопировав источника в контейнер.</span><span class="sxs-lookup"><span data-stu-id="94fe3-233">If you are exploring Docker and .NET Core on sources on the Internet, you will find Dockerfiles that demonstrate the simplicity of building a Docker image by copying your source into a container.</span></span> <span data-ttu-id="94fe3-234">Эти примеры предложения, используя простую конфигурацию, может иметь образа Docker среде упаковать с приложением.</span><span class="sxs-lookup"><span data-stu-id="94fe3-234">These examples suggest that by using a simple configuration, you can have a Docker image with the environment packaged with your application.</span></span> <span data-ttu-id="94fe3-235">В следующем примере показано простое Dockerfile в этом вена.</span><span class="sxs-lookup"><span data-stu-id="94fe3-235">The following example shows a simple Dockerfile in this vein.</span></span>

```
FROM microsoft/dotnet

WORKDIR /app

ENV ASPNETCORE_URLS http://+:80

EXPOSE 80

COPY . .

RUN dotnet restore

ENTRYPOINT ["dotnet", "run"]
```

<span data-ttu-id="94fe3-236">Файл Dockerfile, как это будет работать.</span><span class="sxs-lookup"><span data-stu-id="94fe3-236">A Dockerfile like this will work.</span></span> <span data-ttu-id="94fe3-237">Тем не менее большей части можно оптимизировать вашей образы, особенно вашей рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="94fe3-237">However, you can substantially optimize your images, especially your production images.</span></span>

<span data-ttu-id="94fe3-238">В контейнере и микрослужбами модели постоянно запуске контейнеров.</span><span class="sxs-lookup"><span data-stu-id="94fe3-238">In the container and microservices model, you are constantly starting containers.</span></span> <span data-ttu-id="94fe3-239">Типичный способ использования контейнеров не перезапускает контейнер находится в спящем режиме, так как контейнер может быть уничтожен.</span><span class="sxs-lookup"><span data-stu-id="94fe3-239">The typical way of using containers does not restart a sleeping container, because the container is disposable.</span></span> <span data-ttu-id="94fe3-240">Orchestrators (например, помощью Docker Swarm, Kubernetes, DCOS или Azure Service Fabric) просто создать новые экземпляры изображений.</span><span class="sxs-lookup"><span data-stu-id="94fe3-240">Orchestrators (like Docker Swarm, Kubernetes, DCOS or Azure Service Fabric) simply create new instances of images.</span></span> <span data-ttu-id="94fe3-241">Это значит, может потребоваться оптимизировать с помощью предварительной компиляции приложения при его построении таким образом, при создании экземпляра процесса быстрее.</span><span class="sxs-lookup"><span data-stu-id="94fe3-241">What this means is that you would need to optimize by precompiling the application when it is built so the instantiation process will be faster.</span></span> <span data-ttu-id="94fe3-242">При запуске контейнера должны быть готовы к запуску.</span><span class="sxs-lookup"><span data-stu-id="94fe3-242">When the container is started, it should be ready to run.</span></span> <span data-ttu-id="94fe3-243">Не следует восстановить и компиляции во время выполнения, с помощью dotnet восстановления и dotnet сборки команды из dotnet CLI, как показано в записях блога о .NET Core и Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-243">You should not restore and compile at run time, using dotnet restore and dotnet build commands from the dotnet CLI that, as you see in many blog posts about .NET Core and Docker.</span></span>

<span data-ttu-id="94fe3-244">Команда .NET предоставляет важные действия, чтобы заставить .NET Core и ASP.NET Core framework, оптимизированными для контейнера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-244">The .NET team has been doing important work to make .NET Core and ASP.NET Core a container-optimized framework.</span></span> <span data-ttu-id="94fe3-245">Не только такое .NET Core облегченная платформа с небольшой объем памяти; основное внимание уделено производительность при запуске и, как произведено некоторые оптимизированных образов Docker группой [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) изображения, имеющаяся на [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), по сравнению с обычного [ Microsoft и dotnet](https://hub.docker.com/r/microsoft/dotnet/) или [microsoft-nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) изображения.</span><span class="sxs-lookup"><span data-stu-id="94fe3-245">Not only is .NET Core a lightweight framework with a small memory footprint; the team has focused on startup performance and produced some optimized Docker images, like the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image available at [Docker Hub](https://hub.docker.com/r/microsoft/aspnetcore/), in comparison to the regular [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/) or [microsoft/nanoserver](https://github.com/dotnet/dotnet-docker/blob/master/1.0/nanoserver/runtime/Dockerfile) images.</span></span> <span data-ttu-id="94fe3-246">[Microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) приведена Автоматическая настройка aspnetcore\_URL-адресов для порта 80 и pre ngend кэша сборок; оба этих параметра привести к более быстрый запуск.</span><span class="sxs-lookup"><span data-stu-id="94fe3-246">The [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image provides automatic setting of aspnetcore\_urls to port 80 and the pre-ngend cache of assemblies; both of these settings result in faster startup.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="94fe3-247">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="94fe3-247">Additional resources</span></span>

-   <span data-ttu-id="94fe3-248">**Создание оптимизированных образов Docker с ASP.NET Core**
    [*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span><span class="sxs-lookup"><span data-stu-id="94fe3-248">**Building Optimized Docker Images with ASP.NET Core**
[*https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/*](https://blogs.msdn.microsoft.com/stevelasker/2016/09/29/building-optimized-docker-images-with-asp-net-core/)</span></span>

### <a name="building-the-application-from-a-build-ci-container"></a><span data-ttu-id="94fe3-249">Сборка приложения в другой контейнер сборки (CI)</span><span class="sxs-lookup"><span data-stu-id="94fe3-249">Building the application from a build (CI) container</span></span>

<span data-ttu-id="94fe3-250">Другим преимуществом Docker является созданием приложения из предварительно настроенных контейнера, как показано в на рисунке 8 – 13, поэтому необходимо создать компьютер сборки или виртуальной Машины для построения приложения.</span><span class="sxs-lookup"><span data-stu-id="94fe3-250">Another benefit of Docker is that you can build your application from a preconfigured container, as shown in Figure 8-13, so you do not need to create a build machine or VM to build your application.</span></span> <span data-ttu-id="94fe3-251">Можно использовать или тестовый контейнер этой сборки, запустив его на компьютере разработки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-251">You can use or test that build container by running it at your development machine.</span></span> <span data-ttu-id="94fe3-252">Однако самое еще более интересное, которые можно использовать один и тот же контейнер сборки из конвейера CI (непрерывной интеграции).</span><span class="sxs-lookup"><span data-stu-id="94fe3-252">But what is even more interesting is that you can use the same build container from your CI (Continuous Integration) pipeline.</span></span>

![](./media/image14.png)

<span data-ttu-id="94fe3-253">**На рисунке 8 – 13**.</span><span class="sxs-lookup"><span data-stu-id="94fe3-253">**Figure 8-13**.</span></span> <span data-ttu-id="94fe3-254">Сборка .NET биты в другой контейнер компонентов</span><span class="sxs-lookup"><span data-stu-id="94fe3-254">Components building .NET bits from a container</span></span>

<span data-ttu-id="94fe3-255">В этом сценарии мы предоставляем [aspnetcore/microsoft построения](https://hub.docker.com/r/microsoft/aspnetcore-build/) изображение, которое можно использовать для компиляции и сборки приложений на ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="94fe3-255">For this scenario, we provide the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image, which you can use to compile and build your ASP.NET Core apps.</span></span> <span data-ttu-id="94fe3-256">Выходные данные помещаются в изображения на основе [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) изображение, которое является изображение оптимизированная среда выполнения, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="94fe3-256">The output is placed in an image based on the [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) image, which is an optimized runtime image, as previously noted.</span></span>

<span data-ttu-id="94fe3-257">Изображение aspnetcore сборки содержит все необходимое для компиляции приложения ASP.NET Core, включая .NET Core, пакет SDK для ASP.NET, npm, Bower, Gulp, и т. д.</span><span class="sxs-lookup"><span data-stu-id="94fe3-257">The aspnetcore-build image contains everything you need in order to compile an ASP.NET Core application, including .NET Core, the ASP.NET SDK, npm, Bower, Gulp, etc.</span></span>

<span data-ttu-id="94fe3-258">Эти зависимости необходимо во время построения.</span><span class="sxs-lookup"><span data-stu-id="94fe3-258">We need these dependencies at build time.</span></span> <span data-ttu-id="94fe3-259">Но мы не нужно выполнить их с приложением во время выполнения, так как это сделает изображение излишне большим.</span><span class="sxs-lookup"><span data-stu-id="94fe3-259">But we do not want to carry these with the application at runtime, because it would make the image unnecessarily large.</span></span> <span data-ttu-id="94fe3-260">В приложении eShopOnContainers можно построить приложение из контейнера, просто выполнив следующие docker создание команды.</span><span class="sxs-lookup"><span data-stu-id="94fe3-260">In the eShopOnContainers application, you can build the application from a container by just running the following docker-compose command.</span></span>

```
  docker-compose -f docker-compose.ci.build.yml up
```

<span data-ttu-id="94fe3-261">Рис. 8-14 показано это команда, которая выполняется из командной строки.</span><span class="sxs-lookup"><span data-stu-id="94fe3-261">Figure 8-14 shows this command running at the command line.</span></span>

![](./media/image15.png)

<span data-ttu-id="94fe3-262">**Рис. 8-14.**</span><span class="sxs-lookup"><span data-stu-id="94fe3-262">**Figure 8-14.**</span></span> <span data-ttu-id="94fe3-263">Построение приложений .NET из контейнера</span><span class="sxs-lookup"><span data-stu-id="94fe3-263">Building your .NET application from a container</span></span>

<span data-ttu-id="94fe3-264">Как видите, контейнер, который работает под управлением имеет сборки ci\_1 контейнер.</span><span class="sxs-lookup"><span data-stu-id="94fe3-264">As you can see, the container that is running is the ci-build\_1 container.</span></span> <span data-ttu-id="94fe3-265">Основывается на образе aspnetcore построения, чтобы его можно скомпилировать и построить приложение целиком из этого контейнера, а не с вашего компьютера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-265">This is based on the aspnetcore-build image so that it can compile and build your whole application from within that container instead of from your PC.</span></span> <span data-ttu-id="94fe3-266">Т. е. Почему на самом деле он построения и компиляция проектов .NET Core в Linux, так как этот контейнер выполняется на узле Docker Linux по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="94fe3-266">That is why in reality it is building and compiling the .NET Core projects in Linux—because that container is running on the default Docker Linux host.</span></span>

<span data-ttu-id="94fe3-267">[Docker compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) -файле для этого образа (часть eShopOnContainers) содержит следующий код.</span><span class="sxs-lookup"><span data-stu-id="94fe3-267">The [docker-compose.ci.build.yml](https://github.com/dotnet/eShopOnContainers/blob/master/docker-compose.ci.build.yml) file for that image (part of eShopOnContainers) contains the following code.</span></span> <span data-ttu-id="94fe3-268">Вы увидите запускает контейнер сборки с помощью [aspnetcore/microsoft построения](https://hub.docker.com/r/microsoft/aspnetcore-build/) изображения.</span><span class="sxs-lookup"><span data-stu-id="94fe3-268">You can see that it starts a build container using the [microsoft/aspnetcore-build](https://hub.docker.com/r/microsoft/aspnetcore-build/) image.</span></span>

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

* <span data-ttu-id="94fe3-269">Начиная с **.NET Core 2.0**, `dotnet restore` команда автоматически выполняется при `dotnet publish` выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="94fe3-269">Starting with **.NET Core 2.0**, `dotnet restore` command executes automatically when the `dotnet publish` command is executed.</span></span>

<span data-ttu-id="94fe3-270">После построения контейнера запущен и работает, он работает восстановления dotnet .NET SDK и dotnet опубликовать команд для всех проектов в решении, чтобы скомпилировать биты .NET.</span><span class="sxs-lookup"><span data-stu-id="94fe3-270">Once the build container is up and running, it runs the .NET SDK dotnet restore and dotnet publish commands against all the projects in the solution in order to compile the .NET bits.</span></span> <span data-ttu-id="94fe3-271">Таким образом так как eShopOnContainers также SPA на основе TypeScript и угловой для клиентского кода, его также необходимо проверить зависимости JavaScript с помощью npm, но это действие не связано с биты .NET.</span><span class="sxs-lookup"><span data-stu-id="94fe3-271">In this case, because eShopOnContainers also has an SPA based on TypeScript and Angular for the client code, it also needs to check JavaScript dependencies with npm, but that action is not related to the .NET bits.</span></span>

<span data-ttu-id="94fe3-272">Dotnet публикации построений команды и публикует выходные данные компиляции в каждый проект в папке... папка /obj/Docker/Publish, как показано на рисунке 8-15.</span><span class="sxs-lookup"><span data-stu-id="94fe3-272">The dotnet publish command builds and publishes the compiled output within each project’s folder to the ../obj/Docker/publish folder, as shown in Figure 8-15.</span></span>

![](./media/image16.png)

<span data-ttu-id="94fe3-273">**Рис. 8-15.**</span><span class="sxs-lookup"><span data-stu-id="94fe3-273">**Figure 8-15.**</span></span> <span data-ttu-id="94fe3-274">Команда публикации двоичные файлы, созданные dotnet</span><span class="sxs-lookup"><span data-stu-id="94fe3-274">Binary files generated by the dotnet publish command</span></span>

#### <a name="creating-the-docker-images-from-the-cli"></a><span data-ttu-id="94fe3-275">Создание образов Docker из CLI</span><span class="sxs-lookup"><span data-stu-id="94fe3-275">Creating the Docker images from the CLI</span></span>

<span data-ttu-id="94fe3-276">После публикации выходных данных приложения в связанных папки (в каждом проекте) следующий шаг — фактически создание образов Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-276">Once the application output is published to the related folders (within each project), the next step is to actually build the Docker images.</span></span> <span data-ttu-id="94fe3-277">Для этого используйте сборку docker-compose и docker — составить команды, как показано на рисунке 8-16.</span><span class="sxs-lookup"><span data-stu-id="94fe3-277">To do this, you use the docker-compose build and docker-compose up commands, as shown in Figure 8-16.</span></span>

![](./media/image17.png)

<span data-ttu-id="94fe3-278">**На рисунке 8-16.**</span><span class="sxs-lookup"><span data-stu-id="94fe3-278">**Figure 8-16.**</span></span> <span data-ttu-id="94fe3-279">Создание образов Docker и выполнение контейнеров</span><span class="sxs-lookup"><span data-stu-id="94fe3-279">Building Docker images and running the containers</span></span>

<span data-ttu-id="94fe3-280">В на рисунке 8-17, можно увидеть как docker-compose сборка выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="94fe3-280">In Figure 8-17, you can see how the docker-compose build command runs.</span></span>

![](./media/image18.png)

<span data-ttu-id="94fe3-281">**На рисунке 8-17**.</span><span class="sxs-lookup"><span data-stu-id="94fe3-281">**Figure 8-17**.</span></span> <span data-ttu-id="94fe3-282">Создание образов Docker с помощью docker-создание команды построения</span><span class="sxs-lookup"><span data-stu-id="94fe3-282">Building the Docker images with the docker-compose build command</span></span>

<span data-ttu-id="94fe3-283">Разница между docker-compose построения и составлять docker копирование команды является то, что docker составления построения и запуска изображений.</span><span class="sxs-lookup"><span data-stu-id="94fe3-283">The difference between the docker-compose build and docker-compose up commands is that docker-compose up both builds and starts the images.</span></span>

<span data-ttu-id="94fe3-284">При использовании Visual Studio, на самом деле выполняются следующие действия.</span><span class="sxs-lookup"><span data-stu-id="94fe3-284">When you use Visual Studio, all these steps are performed under the covers.</span></span> <span data-ttu-id="94fe3-285">Visual Studio компилирует приложения .NET, создает образы Docker и развертывает контейнеры в узле Docker.</span><span class="sxs-lookup"><span data-stu-id="94fe3-285">Visual Studio compiles your .NET application, creates the Docker images, and deploys the containers into the Docker host.</span></span> <span data-ttu-id="94fe3-286">Visual Studio предлагает дополнительные функции, такие как возможность отладки в контейнеры, работающего в Docker, напрямую из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="94fe3-286">Visual Studio offers additional features, like the ability to debug your containers running in Docker, directly from Visual Studio.</span></span>

<span data-ttu-id="94fe3-287">Здесь общую takeway является возможность создавать приложения, каким образом конвейер CI/CD должны использовать его же — из контейнера, а не с локального компьютера.</span><span class="sxs-lookup"><span data-stu-id="94fe3-287">The overall takeway here is that you are able to build your application the same way your CI/CD pipeline should build it—from a container instead of from a local machine.</span></span> <span data-ttu-id="94fe3-288">После того, изображения, созданные, затем необходимо просто выполнить образов Docker, с помощью docker-составления копирование команды.</span><span class="sxs-lookup"><span data-stu-id="94fe3-288">After having the images created, then you just need to run the Docker images using the docker-compose up command.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="94fe3-289">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="94fe3-289">Additional resources</span></span>

-   <span data-ttu-id="94fe3-290">**Построение биты в другой контейнер: Настройка eShopOnContainers решение в среде Windows CLI (dotnet CLI, Docker CLI и VS Code)**
    [*https://github.com/dotnet/eShopOnContainers/wiki/ 03.-Setting-the-eShopOnContainers-Solution-UP-in-a-Windows-CLI-Environment-(DotNet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span><span class="sxs-lookup"><span data-stu-id="94fe3-290">**Building bits from a container: Setting the eShopOnContainers solution up in a Windows CLI environment (dotnet CLI, Docker CLI and VS Code)**
[*https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)*](https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code))</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="94fe3-291">[Предыдущие] (данные управляемых crud-microservice.md) [Далее] (база данных сервера container.md)</span><span class="sxs-lookup"><span data-stu-id="94fe3-291">[Previous] (data-driven-crud-microservice.md) [Next] (database-server-container.md)</span></span>
