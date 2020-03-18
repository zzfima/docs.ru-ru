---
title: Docker - gRPC для разработчиков WCF
description: Создание изображений Docker для ASP.NET основных приложений gRPC
ms.date: 09/02/2019
ms.openlocfilehash: e67c43f9486fbfe9a5d3e84e3b74770eb621f604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148118"
---
# <a name="create-docker-images"></a><span data-ttu-id="3ff08-103">Создание изображений Докера</span><span class="sxs-lookup"><span data-stu-id="3ff08-103">Create Docker images</span></span>

<span data-ttu-id="3ff08-104">Этот раздел охватывает создание изображений Docker для ASP.NET приложений Core gRPC, готовых к работе в Docker, Kubernetes или других контейнерных средах.</span><span class="sxs-lookup"><span data-stu-id="3ff08-104">This section covers the creation of Docker images for ASP.NET Core gRPC applications, ready to run in Docker, Kubernetes, or other container environments.</span></span> <span data-ttu-id="3ff08-105">Использованное примерное приложение с веб-приложением ASP.NET Core MVC и сервисом gRPC доступно на репозитории [Dotnet-architecture/grpc-for-wcf-разработчикам](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) на GitHub.</span><span class="sxs-lookup"><span data-stu-id="3ff08-105">The sample application used, with an ASP.NET Core MVC web app and a gRPC service, is available on the [dotnet-architecture/grpc-for-wcf-developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) repository on GitHub.</span></span>

## <a name="microsoft-base-images-for-aspnet-core-applications"></a><span data-ttu-id="3ff08-106">Базовые изображения Майкрософт для ASP.NET основных приложений</span><span class="sxs-lookup"><span data-stu-id="3ff08-106">Microsoft base images for ASP.NET Core applications</span></span>

<span data-ttu-id="3ff08-107">Корпорация Майкрософт предоставляет широкий спектр базовых изображений для создания и запуска приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3ff08-107">Microsoft provides a range of base images for building and running .NET Core applications.</span></span> <span data-ttu-id="3ff08-108">Для создания изображения ASP.NET Core 3.0 используется два базовых изображения:</span><span class="sxs-lookup"><span data-stu-id="3ff08-108">To create an ASP.NET Core 3.0 image, you use two base images:</span></span>

- <span data-ttu-id="3ff08-109">Изображение SDK для создания и публикации приложения.</span><span class="sxs-lookup"><span data-stu-id="3ff08-109">An SDK image to build and publish the application.</span></span>
- <span data-ttu-id="3ff08-110">Изображение времени выполнения для развертывания.</span><span class="sxs-lookup"><span data-stu-id="3ff08-110">A runtime image for deployment.</span></span>

| <span data-ttu-id="3ff08-111">Образ —</span><span class="sxs-lookup"><span data-stu-id="3ff08-111">Image</span></span> | <span data-ttu-id="3ff08-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ff08-112">Description</span></span> |
| ----- | ----------- |
| [<span data-ttu-id="3ff08-113">mcr.microsoft.com/dotnet/core/sdk</span><span class="sxs-lookup"><span data-stu-id="3ff08-113">mcr.microsoft.com/dotnet/core/sdk</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-sdk/) | <span data-ttu-id="3ff08-114">Для строительных `docker build`приложений с .</span><span class="sxs-lookup"><span data-stu-id="3ff08-114">For building applications with `docker build`.</span></span> <span data-ttu-id="3ff08-115">Не использовать в производстве.</span><span class="sxs-lookup"><span data-stu-id="3ff08-115">Not to be used in production.</span></span> |
| [<span data-ttu-id="3ff08-116">mcr.microsoft.com/dotnet/core/aspnet</span><span class="sxs-lookup"><span data-stu-id="3ff08-116">mcr.microsoft.com/dotnet/core/aspnet</span></span>](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) | <span data-ttu-id="3ff08-117">Содержит время выполнения и ASP.NET зависимостей Core.</span><span class="sxs-lookup"><span data-stu-id="3ff08-117">Contains the runtime and ASP.NET Core dependencies.</span></span> <span data-ttu-id="3ff08-118">Для производства.</span><span class="sxs-lookup"><span data-stu-id="3ff08-118">For production.</span></span> |

<span data-ttu-id="3ff08-119">Для каждого изображения существует четыре варианта, основанных на различных дистрибутивах Linux, отличаемых тегами.</span><span class="sxs-lookup"><span data-stu-id="3ff08-119">For each image, there are four variants based on different Linux distributions, distinguished by tags.</span></span>

| <span data-ttu-id="3ff08-120">Тег изображения (ы)</span><span class="sxs-lookup"><span data-stu-id="3ff08-120">Image tag(s)</span></span> | <span data-ttu-id="3ff08-121">Linux</span><span class="sxs-lookup"><span data-stu-id="3ff08-121">Linux</span></span> | <span data-ttu-id="3ff08-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ff08-122">Notes</span></span> |
| --------- | ----- | ----- |
| <span data-ttu-id="3ff08-123">3.0-Buster, 3.0</span><span class="sxs-lookup"><span data-stu-id="3ff08-123">3.0-buster, 3.0</span></span> | <span data-ttu-id="3ff08-124">Debian 10</span><span class="sxs-lookup"><span data-stu-id="3ff08-124">Debian 10</span></span> | <span data-ttu-id="3ff08-125">Изображение по умолчанию, если вариант ОС не указан.</span><span class="sxs-lookup"><span data-stu-id="3ff08-125">The default image if no OS variant is specified.</span></span> |
| <span data-ttu-id="3ff08-126">3.0-альпийский</span><span class="sxs-lookup"><span data-stu-id="3ff08-126">3.0-alpine</span></span> | <span data-ttu-id="3ff08-127">Альпийский 3,9</span><span class="sxs-lookup"><span data-stu-id="3ff08-127">Alpine 3.9</span></span> | <span data-ttu-id="3ff08-128">Альпийские базовые изображения намного меньше, чем Debian или Ubuntu.</span><span class="sxs-lookup"><span data-stu-id="3ff08-128">Alpine base images are much smaller than Debian or Ubuntu ones.</span></span> |
| <span data-ttu-id="3ff08-129">3.0-дискотека</span><span class="sxs-lookup"><span data-stu-id="3ff08-129">3.0-disco</span></span> | <span data-ttu-id="3ff08-130">Ubuntu 19.04</span><span class="sxs-lookup"><span data-stu-id="3ff08-130">Ubuntu 19.04</span></span> | |
| <span data-ttu-id="3ff08-131">3.0-бионический</span><span class="sxs-lookup"><span data-stu-id="3ff08-131">3.0-bionic</span></span> | <span data-ttu-id="3ff08-132">Ubuntu 18.04</span><span class="sxs-lookup"><span data-stu-id="3ff08-132">Ubuntu 18.04</span></span> | |

<span data-ttu-id="3ff08-133">Альпийская база изображения составляет около 100 МБ, по сравнению с 200 МБ для Debian и Ubuntu изображений.</span><span class="sxs-lookup"><span data-stu-id="3ff08-133">The Alpine base image is around 100 MB, compared to 200 MB for the Debian and Ubuntu images.</span></span> <span data-ttu-id="3ff08-134">Некоторые пакеты программного обеспечения или библиотеки могут быть недоступны в управлении пакетами Alpine.</span><span class="sxs-lookup"><span data-stu-id="3ff08-134">Some software packages or libraries might not be available in Alpine's package management.</span></span> <span data-ttu-id="3ff08-135">Если вы не уверены, какое изображение использовать, вы, вероятно, следует выбрать Debian по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3ff08-135">If you're not sure which image to use, you should probably choose the default Debian.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ff08-136">Убедитесь, что вы используете тот же вариант Linux для сборки и времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="3ff08-136">Make sure you use the same variant of Linux for the build and the runtime.</span></span> <span data-ttu-id="3ff08-137">Приложения, построенные и опубликованные на одном варианте, могут не работать на другом.</span><span class="sxs-lookup"><span data-stu-id="3ff08-137">Applications built and published on one variant might not work on another.</span></span>

## <a name="create-a-docker-image"></a><span data-ttu-id="3ff08-138">Создайте образ Docker.</span><span class="sxs-lookup"><span data-stu-id="3ff08-138">Create a Docker image</span></span>

<span data-ttu-id="3ff08-139">Изображение Docker определяется *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="3ff08-139">A Docker image is defined by a *Dockerfile*.</span></span> <span data-ttu-id="3ff08-140">Это текстовый файл, содержащий все команды, необходимые для создания приложения и установки любых зависимостей, необходимых для создания или запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="3ff08-140">This is a text file that contains all the commands needed to build the application and install any dependencies that are required for either building or running the application.</span></span> <span data-ttu-id="3ff08-141">Следующий пример показывает простейшую Dockerfile для приложения Core 3.0 ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="3ff08-141">The following example shows the simplest Dockerfile for an ASP.NET Core 3.0 application:</span></span>

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

<span data-ttu-id="3ff08-142">Dockerfile имеет две части: первая использует базовое `sdk` изображение для создания и публикации приложения; второй создает изображение времени выполнения `aspnet` из базы.</span><span class="sxs-lookup"><span data-stu-id="3ff08-142">The Dockerfile has two parts: the first uses the `sdk` base image to build and publish the application; the second creates a runtime image from the `aspnet` base.</span></span> <span data-ttu-id="3ff08-143">Это потому, что `sdk` изображение составляет около 900 МБ, по сравнению с примерно 200 МБ для изображения времени выполнения, и большая часть его содержимого являются ненужными во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3ff08-143">This is because the `sdk` image is around 900 MB, compared to around 200 MB for the runtime image, and most of its contents are unnecessary at runtime.</span></span>

### <a name="the-build-steps"></a><span data-ttu-id="3ff08-144">Шаги сборки</span><span class="sxs-lookup"><span data-stu-id="3ff08-144">The build steps</span></span>

| <span data-ttu-id="3ff08-145">Шаг</span><span class="sxs-lookup"><span data-stu-id="3ff08-145">Step</span></span> | <span data-ttu-id="3ff08-146">Описание</span><span class="sxs-lookup"><span data-stu-id="3ff08-146">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="3ff08-147">Объявляет базовое изображение и `builder` присваивает псевдоним.</span><span class="sxs-lookup"><span data-stu-id="3ff08-147">Declares the base image and assigns the `builder` alias.</span></span> |
| `WORKDIR /src` | <span data-ttu-id="3ff08-148">Создает `/src` каталог и устанавливает его в качестве текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="3ff08-148">Creates the `/src` directory and sets it as the current working directory.</span></span> |
| `COPY . .` | <span data-ttu-id="3ff08-149">Копирует все, что ниже текущего каталога на хосте, в текущий каталог на изображении.</span><span class="sxs-lookup"><span data-stu-id="3ff08-149">Copies everything below the current directory on the host into the current directory on the image.</span></span> |
| `RUN dotnet restore` | <span data-ttu-id="3ff08-150">Восстанавливает любые внешние пакеты (ASP.NET core 3.0, предварительно установленный с помощью SDK).</span><span class="sxs-lookup"><span data-stu-id="3ff08-150">Restores any external packages (ASP.NET Core 3.0 framework is pre-installed with the SDK).</span></span> |
| `RUN dotnet publish ...` | <span data-ttu-id="3ff08-151">Строит и публикует сборку выпуска.</span><span class="sxs-lookup"><span data-stu-id="3ff08-151">Builds and publishes a Release build.</span></span> <span data-ttu-id="3ff08-152">Обратите внимание, `--runtime` что флаг не требуется.</span><span class="sxs-lookup"><span data-stu-id="3ff08-152">Note that the `--runtime` flag isn't required.</span></span> |

### <a name="the-runtime-image-steps"></a><span data-ttu-id="3ff08-153">Шаги изображения времени выполнения</span><span class="sxs-lookup"><span data-stu-id="3ff08-153">The runtime image steps</span></span>

| <span data-ttu-id="3ff08-154">Шаг</span><span class="sxs-lookup"><span data-stu-id="3ff08-154">Step</span></span> | <span data-ttu-id="3ff08-155">Описание</span><span class="sxs-lookup"><span data-stu-id="3ff08-155">Description</span></span> |
| ---- | ----------- |
| `FROM ...` | <span data-ttu-id="3ff08-156">Объявляет новое базовое изображение.</span><span class="sxs-lookup"><span data-stu-id="3ff08-156">Declares a new base image.</span></span> |
| `WORKDIR /app` | <span data-ttu-id="3ff08-157">Создает `/app` каталог и устанавливает его в качестве текущего рабочего каталога.</span><span class="sxs-lookup"><span data-stu-id="3ff08-157">Creates the `/app` directory and sets it as the current working directory.</span></span> |
| `COPY --from=builder ...` | <span data-ttu-id="3ff08-158">Копирует опубликованное приложение из предыдущего `builder` изображения, используя `FROM` псевдоним из первой строки.</span><span class="sxs-lookup"><span data-stu-id="3ff08-158">Copies the published application from the previous image, by using the `builder` alias from the first `FROM` line.</span></span> |
| `ENTRYPOINT [ ... ]` | <span data-ttu-id="3ff08-159">Устанавливает команду для выполнения при запуске контейнера.</span><span class="sxs-lookup"><span data-stu-id="3ff08-159">Sets the command to run when the container starts.</span></span> <span data-ttu-id="3ff08-160">Команда `dotnet` в изображении времени выполнения может запускать только dLL-файлы.</span><span class="sxs-lookup"><span data-stu-id="3ff08-160">The `dotnet` command in the runtime image can only run DLL files.</span></span> |

### <a name="https-in-docker"></a><span data-ttu-id="3ff08-161">HTTPS в Докере</span><span class="sxs-lookup"><span data-stu-id="3ff08-161">HTTPS in Docker</span></span>

<span data-ttu-id="3ff08-162">Базовые изображения Microsoft для `ASPNETCORE_URLS` Docker `http://+:80`устанавливают переменную среды, а это означает, что Kestrel работает без HTTPS в этом порту.</span><span class="sxs-lookup"><span data-stu-id="3ff08-162">Microsoft base images for Docker set the `ASPNETCORE_URLS` environment variable to `http://+:80`, meaning that Kestrel runs without HTTPS on that port.</span></span> <span data-ttu-id="3ff08-163">Если вы используете HTTPS с пользовательским сертификатом (как описано в [самохознательных приложениях gRPC),](self-hosted.md)вы должны переопределить это.</span><span class="sxs-lookup"><span data-stu-id="3ff08-163">If you're using HTTPS with a custom certificate (as described in [Self-hosted gRPC applications](self-hosted.md)), you should override this.</span></span> <span data-ttu-id="3ff08-164">Установите переменную среды в части создания изображения времен выполнения вашего Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="3ff08-164">Set the environment variable in the runtime image creation part of your Dockerfile.</span></span>

```dockerfile
# Runtime image creation
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0

ENV ASPNETCORE_URLS=https://+:443
```

### <a name="the-dockerignore-file"></a><span data-ttu-id="3ff08-165">Файл .dockerignore</span><span class="sxs-lookup"><span data-stu-id="3ff08-165">The .dockerignore file</span></span>

<span data-ttu-id="3ff08-166">Как `.gitignore` и файлы, исключающие определенные `.dockerignore` файлы и каталоги из элемента управления исходным элементом, файл может использоваться для исключения файлов и каталогов из скопирований на изображение во время сборки.</span><span class="sxs-lookup"><span data-stu-id="3ff08-166">Much like `.gitignore` files that exclude certain files and directories from source control, the `.dockerignore` file can be used to exclude files and directories from being copied to the image during build.</span></span> <span data-ttu-id="3ff08-167">Это не только экономит время копирования, но также позволяет `obj` избежать некоторых ошибок, возникающих в результате копирования каталога с вашего компьютера в изображение.</span><span class="sxs-lookup"><span data-stu-id="3ff08-167">This not only saves time copying, but can also avoid some errors that arise from having the `obj` directory from your PC copied into the image.</span></span> <span data-ttu-id="3ff08-168">Как минимум, вы должны добавить записи для `bin` и `obj` в файл. `.dockerignore`</span><span class="sxs-lookup"><span data-stu-id="3ff08-168">At a minimum, you should add entries for `bin` and `obj` to your `.dockerignore` file.</span></span>

```console
bin/
obj/
```

## <a name="build-the-image"></a><span data-ttu-id="3ff08-169">Создание образа</span><span class="sxs-lookup"><span data-stu-id="3ff08-169">Build the image</span></span>

<span data-ttu-id="3ff08-170">Для решения с одним приложением и, таким образом, одним Dockerfile, проще всего поместить Dockerfile в базовый каталог.</span><span class="sxs-lookup"><span data-stu-id="3ff08-170">For a solution with a single application, and thus a single Dockerfile, it's simplest to put the Dockerfile in the base directory.</span></span> <span data-ttu-id="3ff08-171">Другими словами, поместите его в `.sln` тот же каталог, что и файл.</span><span class="sxs-lookup"><span data-stu-id="3ff08-171">In other words, put it in the same directory as the `.sln` file.</span></span> <span data-ttu-id="3ff08-172">В этом случае для создания изображения `docker build` используйте следующую команду из каталога, содержащего Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="3ff08-172">In that case, to build the image, use the following `docker build` command from the directory containing the Dockerfile.</span></span>

```console
docker build --tag stockdata .
```

<span data-ttu-id="3ff08-173">Запутанно `--tag` названный флаг (который `-t`может быть сокращен до) определяет все имя изображения, включая фактический тег, если указано.</span><span class="sxs-lookup"><span data-stu-id="3ff08-173">The confusingly named `--tag` flag (which can be shortened to `-t`) specifies the whole name of the image, including the actual tag if specified.</span></span> <span data-ttu-id="3ff08-174">В `.` конце оговаривается контекст, в котором будет запущена сборка; текущий рабочий `COPY` каталог для команд в Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="3ff08-174">The `.` at the end specifies the context in which the build will be run; the current working directory for the `COPY` commands in the Dockerfile.</span></span>

<span data-ttu-id="3ff08-175">Если у вас есть несколько приложений в рамках одного решения, вы можете сохранить `.csproj` Dockerfile для каждого приложения в своей папке, рядом с файлом.</span><span class="sxs-lookup"><span data-stu-id="3ff08-175">If you have multiple applications within a single solution, you can keep the Dockerfile for each application in its own folder, beside the `.csproj` file.</span></span> <span data-ttu-id="3ff08-176">Вы все равно `docker build` должны запустить команду из базового каталога, чтобы убедиться, что решение и все проекты скопированы в изображение.</span><span class="sxs-lookup"><span data-stu-id="3ff08-176">You should still run the `docker build` command from the base directory to ensure that the solution and all the projects are copied into the image.</span></span> <span data-ttu-id="3ff08-177">Вы можете указать Dockerfile ниже текущего `--file` каталога, используя (или) `-f`флаг.</span><span class="sxs-lookup"><span data-stu-id="3ff08-177">You can specify a Dockerfile below the current directory by using the `--file` (or `-f`) flag.</span></span>

```console
docker build --tag stockdata --file src/StockData/Dockerfile .
```

## <a name="run-the-image-in-a-container-on-your-machine"></a><span data-ttu-id="3ff08-178">Выполнить изображение в контейнере на машине</span><span class="sxs-lookup"><span data-stu-id="3ff08-178">Run the image in a container on your machine</span></span>

<span data-ttu-id="3ff08-179">Для запуска изображения в локальном экземпляре `docker run` Docker используйте команду.</span><span class="sxs-lookup"><span data-stu-id="3ff08-179">To run the image in your local Docker instance, use the `docker run` command.</span></span>

```console
docker run -ti -p 5000:80 stockdata
```

<span data-ttu-id="3ff08-180">Флаг `-ti` соединяет текущий терминал с терминалом контейнера и работает в интерактивном режиме.</span><span class="sxs-lookup"><span data-stu-id="3ff08-180">The `-ti` flag connects your current terminal to the container's terminal, and runs in interactive mode.</span></span> <span data-ttu-id="3ff08-181">Публикует `-p 5000:80` (ссылки) порт 80 на контейнере к порту 5000 на интерфейсе сети localhost.</span><span class="sxs-lookup"><span data-stu-id="3ff08-181">The `-p 5000:80` publishes (links) port 80 on the container to port 5000 on the localhost network interface.</span></span>

## <a name="push-the-image-to-a-registry"></a><span data-ttu-id="3ff08-182">Отправка образа в реестр</span><span class="sxs-lookup"><span data-stu-id="3ff08-182">Push the image to a registry</span></span>

<span data-ttu-id="3ff08-183">После того как вы проверите, что изображение работает, нажмите его на реестр Docker, чтобы сделать его доступным на других системах.</span><span class="sxs-lookup"><span data-stu-id="3ff08-183">After you've verified that the image works, push it to a Docker registry to make it available on other systems.</span></span> <span data-ttu-id="3ff08-184">Внутренние сети должны будут предоставить реестр Docker.</span><span class="sxs-lookup"><span data-stu-id="3ff08-184">Internal networks will need to provision a Docker registry.</span></span> <span data-ttu-id="3ff08-185">Это может быть так же просто, как запуск [собственного `registry` изображения Docker](https://docs.docker.com/registry/deploying/) (реестр Docker работает в контейнере Docker), но существуют различные более всеобъемлющие решения.</span><span class="sxs-lookup"><span data-stu-id="3ff08-185">This can be as simple as running [Docker's own `registry` image](https://docs.docker.com/registry/deploying/) (the Docker registry runs in a Docker container), but there are various more comprehensive solutions available.</span></span> <span data-ttu-id="3ff08-186">Для внешнего совместного использования и использования облачных технологий доступны различные управляемые реестры, такие как [реестр контейнеров Azure](https://docs.microsoft.com/azure/container-registry/) или [Docker Hub.](https://docs.docker.com/docker-hub/repos/)</span><span class="sxs-lookup"><span data-stu-id="3ff08-186">For external sharing and cloud use, there are various managed registries available, such as [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/) or [Docker Hub](https://docs.docker.com/docker-hub/repos/).</span></span>

<span data-ttu-id="3ff08-187">Чтобы нажать на Docker Hub, префикс именем изображения с вашим пользователем или именем организации.</span><span class="sxs-lookup"><span data-stu-id="3ff08-187">To push to Docker Hub, prefix the image name with your user or organization name.</span></span>

```console
docker tag stockdata myorg/stockdata
docker push myorg/stockdata
```

<span data-ttu-id="3ff08-188">Чтобы нажать на частный реестр, префикс имя изображения с именем хоста реестра и название организации.</span><span class="sxs-lookup"><span data-stu-id="3ff08-188">To push to a private registry, prefix the image name with the registry host name and the organization name.</span></span>

```console
docker tag stockdata internal-registry:5000/myorg/stockdata
docker push internal-registry:5000/myorg/stockdata
```

<span data-ttu-id="3ff08-189">После того, как изображение находится в реестре, его можно развернуть в отдельных хостах Docker или в двигатель оркестровки контейнеров, как Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="3ff08-189">After the image is in a registry, you can deploy it to individual Docker hosts, or to a container orchestration engine like Kubernetes.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="3ff08-190">[Предыдущий](self-hosted.md)
>[Следующий](kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="3ff08-190">[Previous](self-hosted.md)
[Next](kubernetes.md)</span></span>
