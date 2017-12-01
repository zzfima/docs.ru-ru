---
title: "Основы Docker с помощью .NET Core"
description: "Docker и учебник по .NET Core"
keywords: ".NET, .NET core, Docker, учебник"
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 03c28597-7e73-46d6-a9c3-f9cb55642739
ms.custom: mvc
manager: wpickett
ms.openlocfilehash: 5935f67d7e4ca9c9e8768373e2bcaa9febccfdc5
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2017
---
# <a name="learn-docker-basics-with-net-core"></a>Основы Docker с помощью .NET Core

В этом учебнике показано Docker контейнера построение и развертывание задачи для приложения .NET Core. В ходе этого учебника вы узнаете:

> [!div class="checklist"]
> * Как создать файл Dockerfile
> * Инструкции по созданию приложения .NET Core.
> * Как развернуть приложение в контейнер Docker.

[Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистемы Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) быстро построить и пакет приложения в качестве [Docker images](https://docs.docker.com/glossary/?term=image). Эти образы на языке [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) формат, чтобы развернуть и запустить [многоуровневая контейнер](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

## <a name="net-core-easiest-way-to-get-started"></a>.NET core: Простой способ приступить к работе

Перед созданием образа Docker, необходимо упаковываете приложение. Его можно создать в Windows, Linux или MacOS. Самый быстрый и легкий способ сделать, которая должна использоваться .NET Core.

Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/index.md).

Можно создавать контейнеры Windows и Linux с помощью [несколькими архитектура на основе тегов](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>Своего первого приложения .NET Core Docker

### <a name="prerequisites"></a>Предварительные требования

Для выполнения заданий данного учебника:

#### <a name="net-core-20-sdk"></a>.NET core 2.0 SDK

* Установка [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

Полный список операционных систем, поддерживаемых .NET Core 2.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла см. на странице [Версии ОС, поддерживаемые .NET Core 2.x](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).

* Если это еще не сделано, установите редактора избранные кода.

> [!TIP]
> Необходимо установить редактор кода? Повторите [Visual Studio](https://visualstudio.com/downloads)!

#### <a name="installing-docker-client"></a>Установка клиента Docker

Установка [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии клиента Docker.

В можно установить клиента Docker.

* Дистрибутивы Linux

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/).

### <a name="create-a-net-core-20-console-app-for-dockerization"></a>Создание консольного приложения .NET Core 2.0 для Dockerization

Откройте командную строку и создайте папку с именем *Hello*. Перейдите в папку, созданную и введите следующие команды:

```console
dotnet new console
dotnet run
```

Вкратце рассмотрим эти команды.

1. `$ dotnet new console`

   [`dotnet new`](../tools/dotnet-new.md) создает актуальный файл проекта `Hello.csproj` с зависимостями, необходимыми для создания консольного приложения.  Эта команда также создает `Program.cs` — простой файл, содержащий точку входа для приложения.
   
   `Hello.csproj`:

   В файле проекта указываются все данные, необходимые для восстановления зависимостей и создания программы.

   * Тег `OutputType` указывает, что мы создаем исполняемый файл — другими словами, консольное приложение.
   * Тег `TargetFramework` указывает, какая реализация.NET является целевой. В более сложных случаях можно указать несколько целевых платформ и сборки для указанной платформы в одной операции. В этом учебнике мы создаем для основных компонентов .NET 2.0.

   `Program.cs`:

   При запуске программы `using System`. Оно означает, «перевести все, что `System` пространства имен в области видимости для этого файла.» Пространство имен `System` содержит основные конструкции, такие как `string`, или числовые типы.

   Затем мы определяем пространство имен с именем `Hello`. Пространство имен можно изменить на нужной информации. Класс `Program` определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента. Этот массив содержит список аргументов, передаваемых при вызове скомпилированной программы. В нашем примере программа записывает только «Hello World!» в консоль.

2. `$ dotnet restore`

   В .NET Core 2.x **dotnet новый** выполняется [ `dotnet restore` ](../tools/dotnet-restore.md) команды. **Восстановление DotNet** восстанавливает дерево зависимостей с [NuGet](https://www.nuget.org/)вызова (диспетчер пакетов .NET).
   NuGet выполняет следующие задачи:
   * анализирует *Hello.csproj* файла 
   * загружает файл зависимостей (или грабс из кэша машины)
   * Записывает *obj/project.assets.json* файла

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
   
   *Project.assets.json* файл представляет собой полный набор граф зависимостей NuGet, разрешения привязки и другие метаданные приложения. Это потребовало создания файла используется другими средствами, например [ `dotnet build` ](../tools/dotnet-build.md) и [ `dotnet run` ](../tools/dotnet-run.md), для правильной обработки исходного кода.
   
3. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md)вызовы [ `dotnet build` ](../tools/dotnet-build.md) для подтверждения успешной сборки, а затем вызывает `dotnet <assembly.dll>` для запуска приложения.
   
    ```console
    $ dotnet run
    
    Hello World!
    ```

    Для более сложных сценариев, в разделе [развертывание приложений .NET Core](../deploying/index.md) подробные сведения.

## <a name="dockerize-the-net-core-application"></a>Dockerize приложения .NET Core

Консольное приложение Hello .NET Core успешно выполняется локально. Теперь рассмотрим его шаг дальнейшей и построить и запустить приложение в Docker.

### <a name="your-first-dockerfile"></a>Первый Dockerfile

Откройте в текстовом редакторе и давайте начнем! Мы работаем по-прежнему из каталога Hello, мы создали приложение в.

Добавьте следующие инструкции Docker для либо Linux или [контейнеры Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) в новый файл. При необходимости можно сохранить его в корневом каталоге Hello как **Dockerfile**, без расширения (может потребоваться задать файлов данного типа `All types (*.*)` или что-нибудь подобное).

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile содержит инструкции сборки Docker, запускаемых последовательно.

Первая инструкция должна быть [ **FROM**](https://docs.docker.com/engine/reference/builder/#from). Эта инструкция инициализирует нового этапа сборки и задает базового образа для инструкциям. Контейнеры Windows или Linux по запросу несколькими arch теги в зависимости от того, Docker для Windows [режим контейнера](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers). От базового образа в нашем примере — это изображение 2.0 sdk из репозитория microsoft/dotnet

```Dockerfile
FROM microsoft/dotnet:2.0-sdk
```

[ **WORKDIR** ](https://docs.docker.com/engine/reference/builder/#workdir) инструкция задает рабочий каталог для любые оставшиеся ВЫПОЛНЕНИЯ, CMD, точки входа, КОПИРОВАНИЯ и добавить Dockerfile инструкции. Если каталог не существует, он создается. В этом случае WORKDIR установлено в каталог приложения.

```Dockerfile
WORKDIR /app
```

[ **КОПИРОВАНИЯ** ](https://docs.docker.com/engine/reference/builder/#copy) инструкция копирует новые файлы или каталоги из исходного пути и добавляет их в целевой контейнер файловой системе. С помощью следующей инструкции выполняется копирование файла проекта C# в контейнер.

```Dockerfile
COPY *.csproj ./
```

[ **ЗАПУСКА** ](https://docs.docker.com/engine/reference/builder/#run) инструкция выполняет все команды в новый слой поверх текущего образа и зафиксировать результаты. Полученное изображение зафиксированных используется к следующему шагу в Dockerfile. Мы создали **восстановления dotnet** получение необходимых зависимостей файла проекта C#. 

```Dockerfile
RUN dotnet restore
```

Это **КОПИРОВАНИЯ** инструкция копирует остальные файлы в нашем контейнер в новых [слои](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

Мы публикуем приложения с этим **ЗАПУСКА** инструкции. [ **Публикации dotnet** ](../tools/dotnet-publish.md) команды компилирует приложение считывает его зависимости, заданные в файле проекта и публикует результирующий набор файлов в каталоге. Нашего приложения публикуется с **выпуска** конфигурации и выходные данные в каталоге по умолчанию.

```Dockerfile
RUN dotnet publish -c Release -o out
```

[ **ENTRYPOINT** ](https://docs.docker.com/engine/reference/builder/#entrypoint) инструкция предоставляет контейнеру возможность запуска как исполняемого файла.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Теперь у вас есть файл Dockerfile:

* копирует образ приложения
* зависимости приложения в образ
* выполняет построение приложения для запуска в качестве исполняемого файла

### <a name="build-and-run-the-hello-net-core-20-app"></a>Построение и запуск приложения Hello .NET Core 2.0

#### <a name="essential-docker-commands"></a>Основные команды Docker

Эти команды Docker имеют большое значение:

* [сборка docker](https://docs.docker.com/engine/reference/commandline/build/)
* [Запустите docker](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [образ docker](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Построение и запуск

Записано dockerfile; Теперь Docker создает приложения, а затем запускает контейнер.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

Выходные данные `docker build` команды должен быть аналогичен следующие выходные данные в консоли:

```console
Sending build context to Docker daemon   72.7kB
Step 1/7 : FROM microsoft/dotnet:2.0-sdk
 ---> d84f64b126a6
Step 2/7 : WORKDIR /app
 ---> Using cache
 ---> 9af1fbdc7972
Step 3/7 : COPY *.csproj ./
 ---> Using cache
 ---> 86c8c332d4b3
Step 4/7 : RUN dotnet restore
 ---> Using cache
 ---> 86fcd7dd0ea4
Step 5/7 : COPY . ./
 ---> Using cache
 ---> 6faf0a53607f
Step 6/7 : RUN dotnet publish -c Release -o out
 ---> Using cache
 ---> f972328318c8
Step 7/7 : ENTRYPOINT dotnet out/Hello.dll
 ---> Using cache
 ---> 53c337887e18
Successfully built 53c337887e18
Successfully tagged dotnetapp-dev:latest
```

Как видно из выходных данных, подсистема Docker можно создать нашей контейнер Dockerfile.

Выходные данные `docker run` команды должен быть аналогичен следующие выходные данные в консоли:

```console
Hello World!
```

Поздравляем! у вас есть только:
> [!div class="checklist"]
> * Создать локальное приложение .NET Core
> * Создать файл Dockerfile для создания первого контейнера
> * Построение и запустили приложение Dockerized



## <a name="next-steps"></a>Дальнейшие действия

Ниже приведены действия, которые можно предпринять.

* [Общие сведения о видео образы Docker .NET](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Visual Studio, Docker & экземпляры контейнером Azure вместе лучше!](https://blogs.msdn.microsoft.com/alimaz/2017/08/17/visual-studio-docker-azure-container-instances-better-together/)
* [Docker для краткие руководства по Azure](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Разверните приложение на Docker для Azure](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Если у вас подписка на Azure, [Зарегистрируйтесь](https://azure.microsoft.com/free/?b=16.48) для бесплатной 30-дневной учетной записи и get 200 в кредиты Azure, чтобы испытать любое сочетание служб Azure.

## <a name="docker-images-used-in-this-sample"></a>Docker изображений, используемых в этом образце

В этом образце используются следующие образы Docker

* [`microsoft/dotnet:2.0-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Связанные ресурсы

* [Образцы .NET core Docker](https://github.com/dotnet/dotnet-docker-samples/README.md)
* [Dockerfile в контейнерах Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Примеры .NET framework Docker](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core на DockerHub](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Dockerize приложение .NET Core — учебник Docker](https://docs.docker.com/engine/examples/dotnetcore/)
* [Работа со средствами Visual Studio Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Развертывание образов Docker из реестра контейнер Azure с экземплярами Azure контейнера](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)