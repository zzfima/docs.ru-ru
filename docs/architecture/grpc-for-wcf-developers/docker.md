---
title: DOCKER-gRPC для разработчиков WCF
description: Создание образов DOCKER для ASP.NET Core приложений gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: cc369da9494ade532187dfc8d19a94a3a037ebab
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841657"
---
# <a name="docker"></a><span data-ttu-id="e237e-103">Docker</span><span class="sxs-lookup"><span data-stu-id="e237e-103">Docker</span></span>

<span data-ttu-id="e237e-104">В этом разделе рассматриваются создание образов DOCKER для ASP.NET Core приложений gRPC, готовых к работе в DOCKER, Kubernetes или в других средах контейнеров.</span><span class="sxs-lookup"><span data-stu-id="e237e-104">This section will cover the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="e237e-105">Пример приложения, используемый с веб-приложением ASP.NET Core MVC и службой gRPC, доступен в репозитории [DotNet-Architecture/gRPC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на сайте GitHub.</span><span class="sxs-lookup"><span data-stu-id="e237e-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="e237e-106">Базовые образы Майкрософт для приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e237e-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="e237e-107">Корпорация Майкрософт предоставляет ряд базовых образов для создания и запуска приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e237e-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="e237e-108">Чтобы создать образ ASP.NET Core 3,0, используются два базовых образа: образ пакета SDK для сборки и публикации приложения, а также образ среды выполнения для развертывания.</span><span class="sxs-lookup"><span data-stu-id="e237e-108">To create an ASP.NET Core 3.0 image, two base images are used: an SDK image to build and publish the application, and a runtime image for deployment.</span></span>

| <span data-ttu-id="e237e-109">Изображение</span><span class="sxs-lookup"><span data-stu-id="e237e-109">Image</span></span> | <span data-ttu-id="e237e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e237e-110">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="e237e-111">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="e237e-111">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="e237e-112">Для создания приложений с `docker build`.</span><span class="sxs-lookup"><span data-stu-id="e237e-112">For building applications with `docker build`.</span></span> <span data-ttu-id="e237e-113">Не для использования в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="e237e-113">Not to be used in production.</span></span> |
| [<span data-ttu-id="e237e-114">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="e237e-114">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="e237e-115">Содержит зависимости среды выполнения и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e237e-115">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="e237e-116">Для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="e237e-116">For production.</span></span> |

<span data-ttu-id="e237e-117">Для каждого образа существует четыре варианта, основанные на разных дистрибутивах Linux, различающихся по тегам.</span><span class="sxs-lookup"><span data-stu-id="e237e-117">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="e237e-118">Теги изображений</span><span class="sxs-lookup"><span data-stu-id="e237e-118">Image tag(s)</span></span> | <span data-ttu-id="e237e-119">Linux</span><span class="sxs-lookup"><span data-stu-id="e237e-119">Linux</span></span> | <span data-ttu-id="e237e-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="e237e-120">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="e237e-121">3,0-бустер, 3,0</span><span class="sxs-lookup"><span data-stu-id="e237e-121">3.0-buster, 3.0</span></span> | <span data-ttu-id="e237e-122">Debian 10</span><span class="sxs-lookup"><span data-stu-id="e237e-122">Debian 10</span></span> | <span data-ttu-id="e237e-123">Изображение по умолчанию, если не указан вариант ОС.</span><span class="sxs-lookup"><span data-stu-id="e237e-123">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="e237e-124">3,0-Alpine</span><span class="sxs-lookup"><span data-stu-id="e237e-124">3.0-alpine</span></span> | <span data-ttu-id="e237e-125">Alpine 3,9</span><span class="sxs-lookup"><span data-stu-id="e237e-125">Alpine 3.9</span></span> | <span data-ttu-id="e237e-126">Базовые образы Alpine намного меньше, чем Debian или Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="e237e-126">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="e237e-127">3,0-Disco</span><span class="sxs-lookup"><span data-stu-id="e237e-127">3.0-disco</span></span> | <span data-ttu-id="e237e-128">Ubuntu 19,04</span><span class="sxs-lookup"><span data-stu-id="e237e-128">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="e237e-129">3,0-Бионик</span><span class="sxs-lookup"><span data-stu-id="e237e-129">3.0-bionic</span></span> | <span data-ttu-id="e237e-130">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="e237e-130">Ubuntu 18.04</span></span> | |

<span data-ttu-id="e237e-131">Базовый образ Alpine составляет около 100 МБ по сравнению с 200 МБ для образов Debian и Ubuntu, но некоторые программные пакеты или библиотеки могут быть недоступны в управлении пакетами Alpine.</span><span class="sxs-lookup"><span data-stu-id="e237e-131">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images, but some software packages or libraries may not be available in Alpine's package management.</span></span> <span data-ttu-id="e237e-132">Если вы не знаете, какой образ следует использовать, лучше подойдет к Debian по умолчанию, если нет необходимости использовать другой дистрибутив.</span><span class="sxs-lookup"><span data-stu-id="e237e-132">If you're not sure which image to use, it's best to stick to the default Debian unless you have a compelling need to use a different distro.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e237e-133">Убедитесь, что для сборки и среды выполнения используется один и тот же вариант Linux.</span><span class="sxs-lookup"><span data-stu-id="e237e-133">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="e237e-134">Приложения, созданные и опубликованные на одном варианте, могут не работать на другом.</span><span class="sxs-lookup"><span data-stu-id="e237e-134">Applications built and published on one variant may not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="e237e-135">Создание образа DOCKER</span><span class="sxs-lookup"><span data-stu-id="e237e-135">Create a Docker image</span></span>

<span data-ttu-id="e237e-136">Образ DOCKER определяется *Dockerfile*, текстовым файлом, содержащим все команды, необходимые для построения приложения, и установки всех зависимостей, необходимых для сборки или запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="e237e-136">A Docker image is defined by a *Dockerfile*, a text file that contains all the commands that are needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="e237e-137">В следующем примере показан самый простой Dockerfile для приложения ASP.NET Core 3,0:</span><span class="sxs-lookup"><span data-stu-id="e237e-137">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

```dockerfile
# Application build steps
FROM mcr.microsoft.com/dotnet/core/sdk:3.0 as builder

WORKDIR /src

COPY . .

RUN dotnet restore

RUN dotnet publish -c Release -o /published src/StockData/StockData.csproj

# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

# Uncomment the line below if running with HTTPS
# ENV ASPNETCORE_URLS=https://+:443

WORKDIR /app

COPY --from=builder /published .

ENTRYPOINT [ "dotnet", "StockData.dll" ]
```

<span data-ttu-id="e237e-138">Dockerfile состоит из двух частей: первый использует базовый образ `sdk` для сборки и публикации приложения; второй создает образ среды выполнения из базы `aspnet`.</span><span class="sxs-lookup"><span data-stu-id="e237e-138">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="e237e-139">Это связано с тем, что `sdk` образ составляет около 900 МБ по сравнению с 200 МБ для образа среды выполнения, и большая часть его содержимого не требуется во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e237e-139">This is because the `sdk` image is around 900 MB compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="e237e-140">Этапы сборки</span><span class="sxs-lookup"><span data-stu-id="e237e-140">The build steps</span></span>

| <span data-ttu-id="e237e-141">Шаг</span><span class="sxs-lookup"><span data-stu-id="e237e-141">Step</span></span> | <span data-ttu-id="e237e-142">Описание</span><span class="sxs-lookup"><span data-stu-id="e237e-142">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="e237e-143">Объявляет базовый образ и назначает псевдоним `builder` (описание см. в следующем разделе).</span><span class="sxs-lookup"><span data-stu-id="e237e-143">Declares the base image and assigns the `builder` alias (see next section for explanation).</span></span> |
| `WORKDIR /src` | <span data-ttu-id="e237e-144">Создает `/src` каталог и задает его в качестве текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="e237e-144">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="e237e-145">Копирует все, что находится под текущим каталогом на узле, в текущий каталог на образе.</span><span class="sxs-lookup"><span data-stu-id="e237e-145">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="e237e-146">Восстанавливает все внешние пакеты (ASP.NET Core 3,0 Framework предварительно устанавливается вместе с пакетом SDK).</span><span class="sxs-lookup"><span data-stu-id="e237e-146">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="e237e-147">Создает и публикует сборку выпуска.</span><span class="sxs-lookup"><span data-stu-id="e237e-147">Builds and publishes a Release build.</span></span> <span data-ttu-id="e237e-148">Обратите внимание, что флаг `--runtime` не требуется.</span><span class="sxs-lookup"><span data-stu-id="e237e-148">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="e237e-149">Шаги образа среды выполнения</span><span class="sxs-lookup"><span data-stu-id="e237e-149">The runtime image steps</span></span>

| <span data-ttu-id="e237e-150">Шаг</span><span class="sxs-lookup"><span data-stu-id="e237e-150">Step</span></span> | <span data-ttu-id="e237e-151">Описание</span><span class="sxs-lookup"><span data-stu-id="e237e-151">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="e237e-152">Объявляет новый базовый образ.</span><span class="sxs-lookup"><span data-stu-id="e237e-152">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="e237e-153">Создает `/app` каталог и задает его в качестве текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="e237e-153">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="e237e-154">Копирует опубликованное приложение из предыдущего образа, используя псевдоним `builder` из первой `FROM` строки.</span><span class="sxs-lookup"><span data-stu-id="e237e-154">Copies the published application from the previous image, using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="e237e-155">Задает выполнение команды при запуске контейнера.</span><span class="sxs-lookup"><span data-stu-id="e237e-155">Sets the command to run when the container starts.</span></span> <span data-ttu-id="e237e-156">Команда `dotnet` в образе среды выполнения может запускать только DLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="e237e-156">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="e237e-157">HTTPS в DOCKER</span><span class="sxs-lookup"><span data-stu-id="e237e-157">HTTPS in Docker</span></span>

<span data-ttu-id="e237e-158">Базовые образы Майкрософт для DOCKER задают `http://+:80`переменной среды `ASPNETCORE_URLS`, что означает, что для этого порта Kestrel будет выполняться без протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e237e-158">Microsoft's base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel will run without HTTPS on that port.</span></span> <span data-ttu-id="e237e-159">Если вы используете протокол HTTPS с пользовательским сертификатом (как описано в [предыдущем разделе](self-hosted.md)), его следует переопределить, задав переменную среды **в части создания образа среды выполнения** Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e237e-159">If you're using HTTPS with a custom certificate (as described in [the previous section](self-hosted.md)), you should override this by setting the environment variable **in the runtime image creation part** of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="e237e-160">Файл dockerignore</span><span class="sxs-lookup"><span data-stu-id="e237e-160">The .dockerignore file</span></span>

<span data-ttu-id="e237e-161">Во многом подобно `.gitignore` файлам, которые исключают определенные файлы и каталоги из системы управления версиями, файл `.dockerignore` можно использовать для исключения копирования файлов и каталогов в образ во время сборки.</span><span class="sxs-lookup"><span data-stu-id="e237e-161">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="e237e-162">Это не только экономит время, но и позволяет избежать некоторых непонятных ошибок, которые возникают из-за того, что каталог `obj` на компьютере скопирован в образ.</span><span class="sxs-lookup"><span data-stu-id="e237e-162">This not only saves time copying, but can also avoid some confusing errors that arise from having (particularly) the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="e237e-163">Необходимо добавить по крайней мере записи для `bin` и `obj` в файл `.dockerignore`.</span><span class="sxs-lookup"><span data-stu-id="e237e-163">You should add at least entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="e237e-164">Сборка образа</span><span class="sxs-lookup"><span data-stu-id="e237e-164">Build the image</span></span>

<span data-ttu-id="e237e-165">Для решения с одним приложением и, таким способом, одним Dockerfile, проще всего разместить Dockerfile в базовом каталоге. то есть тот же каталог, что и файл `.sln`.</span><span class="sxs-lookup"><span data-stu-id="e237e-165">For a solution with a single application, and thus a single Dockerfile, it is simplest to put the Dockerfile in the base directory; that is, the same directory as the `.sln` file.</span></span> <span data-ttu-id="e237e-166">В этом случае для создания образа используйте следующую команду `docker build` из каталога, содержащего Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e237e-166">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="e237e-167">Непонятный именованный флаг `--tag` (который можно сократить до `-t`) задает полное имя изображения, *включая* фактический тег, если он указан.</span><span class="sxs-lookup"><span data-stu-id="e237e-167">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, *including* the actual tag if specified.</span></span> <span data-ttu-id="e237e-168">`.` в конце указывает *контекст* , в котором будет выполняться сборка. текущий рабочий каталог для команд `COPY` в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="e237e-168">The `.` at the end specifies the *context* in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="e237e-169">Если в одном решении имеется несколько приложений, можно сохранить Dockerfile для каждого приложения в отдельной папке рядом с файлом `.csproj`, но по-прежнему следует выполнить команду `docker build` из базового каталога, чтобы убедиться, что решение и все проекты скопированы в образ.</span><span class="sxs-lookup"><span data-stu-id="e237e-169">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file, but you should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="e237e-170">Вы можете указать Dockerfile под текущим каталогом с помощью флага `--file` (или `-f`).</span><span class="sxs-lookup"><span data-stu-id="e237e-170">You can specify a Dockerfile below the current directory using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="e237e-171">Запуск образа в контейнере на компьютере</span><span class="sxs-lookup"><span data-stu-id="e237e-171">Run the image in a container on your machine</span></span>

<span data-ttu-id="e237e-172">Чтобы запустить образ в локальном экземпляре DOCKER, используйте команду `docker run`.</span><span class="sxs-lookup"><span data-stu-id="e237e-172">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="e237e-173">Флаг `-ti` подключает текущий терминал к терминалу контейнера и выполняется в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="e237e-173">The `-ti` flag connects your current terminal to the container's terminal and runs in interactive mode.</span></span> <span data-ttu-id="e237e-174">`-p 5000:80` публикует (ссылки) порт 80 в контейнере на порт 80 на сетевом интерфейсе localhost.</span><span class="sxs-lookup"><span data-stu-id="e237e-174">The `-p 5000:80` publishes (links) port 80 on the container to port 80 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="e237e-175">Отправка образа в реестр</span><span class="sxs-lookup"><span data-stu-id="e237e-175">Push the image to a registry</span></span>

<span data-ttu-id="e237e-176">Убедившись, что образ работает, необходимо отправить его в реестр DOCKER, чтобы сделать доступным в других системах.</span><span class="sxs-lookup"><span data-stu-id="e237e-176">Once you've verified that the image works, you need to push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="e237e-177">Внутренним сетям потребуется подготавливать реестр DOCKER.</span><span class="sxs-lookup"><span data-stu-id="e237e-177">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="e237e-178">Это может быть так же просто, как и [собственный образ docker `registry`](https://docs.docker.com/registry/deploying/) (это верно, реестр DOCKER выполняется в контейнере DOCKER), но доступны различные более комплексные решения.</span><span class="sxs-lookup"><span data-stu-id="e237e-178">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (that's right, the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="e237e-179">Для внешнего общего доступа и использования в облаке доступны различные управляемые реестры, такие как [Реестр контейнеров Azure](https://docs.microsoft.com/azure/container-registry/) или [DOCKER Hub](https://docs.docker.com/docker-hub/repos/).</span><span class="sxs-lookup"><span data-stu-id="e237e-179">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="e237e-180">Чтобы отправить в центр DOCKER, добавьте перед именем образа имя пользователя или организации.</span><span class="sxs-lookup"><span data-stu-id="e237e-180">To push to the Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="e237e-181">Чтобы отправить в частный реестр, добавьте перед именем образа имя узла реестра и имя Организации.</span><span class="sxs-lookup"><span data-stu-id="e237e-181">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="e237e-182">После того как образ находится в реестре, его можно развернуть на отдельных узлах DOCKER или в ядре оркестрации контейнера, например Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e237e-182">Once the image is in a registry, you can deploy it to individual Docker hosts or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e237e-183">[Назад](self-hosted.md)
>[Вперед](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="e237e-183">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
