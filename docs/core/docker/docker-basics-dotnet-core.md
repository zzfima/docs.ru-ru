---
title: Контейнеризация приложения с помощью Docker
description: Узнайте о том, как создать простое приложение .NET Core и добавить его в контейнер с помощью Docker.
ms.date: 10/11/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: eed72553576f4154fe63b2e5cf035a781afe4b7c
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "53169590"
---
# <a name="how-to-containerize-a-net-core-application"></a>Контейнеризация приложения .NET Core

Это руководство описывает задачи сборки и развертывания контейнера Docker для приложения .NET Core. [Платформа Docker](https://docs.docker.com/engine/docker-overview/#the-docker-platform) использует [подсистему Docker](https://docs.docker.com/engine/docker-overview/#docker-engine) для быстрой сборки и упаковки приложений в качестве [образов Docker](https://docs.docker.com/glossary/?term=image). Эти образы имеют формат [Dockerfile](https://docs.docker.com/glossary/?term=Dockerfile) и предназначены для развертывания и запуска в [многоуровневом контейнере](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#container-and-layers).

В ходе работы с этим руководством вы:

> [!div class="checklist"]
> * как создать Dockerfile;
> * как создать приложение .NET Core;
> * как развертывать приложение в контейнер Docker.

## <a name="net-core-easiest-way-to-get-started"></a>.NET Core: самый простой способ начать работу

Перед созданием образа Docker вам потребуется приложение для упаковки в контейнер. Его можно создать в Windows, Linux или MacOS. Самый быстрый и простой способ — использовать .NET Core.

Если вы не знакомы с набором средств CLI .NET Core, прочитайте [обзор пакета SDK для .NET Core](../tools/index.md).

Вы можете создать контейнеры Windows и Linux с использованием [тегов на основе мультиархитектурности](https://github.com/dotnet/announcements/issues/14).

## <a name="your-first-net-core-docker-app"></a>Ваше первое приложение Docker для .NET Core

### <a name="prerequisites"></a>Предварительные требования

Для работы с этим руководством вам понадобится следующее:

#### <a name="net-core-sdk"></a>Пакет SDK для .NET Core

* Установите [пакет SDK для .NET Core 2.1 или более поздней версии](https://www.microsoft.com/net/download).

См. [полный список операционных систем, поддерживаемых .NET Core 2.1.x, неподдерживаемых версий ОС, а также ссылки на политики жизненного цикла](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).

* Установите любой привычный для вас редактор кода, если еще не сделали этого.

> [!TIP]
> Нужно ли устанавливать редактор кода? Попробуйте [Visual Studio Code](https://code.visualstudio.com/download)!

#### <a name="installing-docker-client"></a>Установка клиента Docker

Установите клиент [Docker 18.06](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии.

Клиент Docker можно установить в:

* Дистрибутивах Linux

   * [CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)

   * [Debian](https://docs.docker.com/install/linux/docker-ce/debian/)

   * [Fedora](https://docs.docker.com/install/linux/docker-ce/fedora/)

   * [Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

* [macOS](https://docs.docker.com/docker-for-mac/install/)

* [Windows](https://docs.docker.com/docker-for-windows/install/)

### <a name="create-a-net-core-21-console-app-for-dockerization"></a>Создание консольного приложения .NET Core 2.1 для добавления в Docker

Откройте командную строку и создайте папку с именем *Hello*. Перейдите в созданную папку и введите следующие команды:

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
   * Тег `TargetFramework` указывает, какая реализация.NET является целевой. В расширенном сценарии обработки можно указать несколько целевых платформ и выполнить сборку в них за одну операцию. В этом руководстве описано, как выполнить сборку для .NET Core 2.1.

   `Program.cs`:

   Программа начинается с команды `using System`. Это означает "добавить все данные пространства имен `System` в область видимости для этого файла". Пространство имен `System` содержит основные конструкции, такие как `string`, или числовые типы.

   Затем мы определяем пространство имен с именем `Hello`. Вы можете сменить это пространство имен на любое другое. Класс `Program` определяется в этом пространстве имен с использованием метода `Main`, который принимает массив строк в качестве аргумента. Этот массив содержит список аргументов, передаваемых при вызове скомпилированной программы. В нашем примере программа просто выводит "Hello World!" в консоль.

   **Dotnet new** запускает команду [`dotnet restore`](../tools/dotnet-restore.md). **Dotnet restore** восстанавливает дерево зависимостей с помощью вызова [NuGet](https://www.nuget.org/) (диспетчер пакетов .NET).
   NuGet выполняет следующие задачи:
   * анализирует файл *Hello.csproj*;
   * скачивает файл зависимостей (или получает его из кэша компьютера);
   * записывает файл *obj/project.assets.json*.

   Файл *project.assets.json* содержит полную схему зависимостей NuGet, разрешения привязок и другие метаданные приложения. Этот обязательный файл используется другими средствами, например [`dotnet build`](../tools/dotnet-build.md) и [`dotnet run`](../tools/dotnet-run.md), для правильной обработки исходного кода.

2. `$ dotnet run`

   [`dotnet run`](../tools/dotnet-run.md) вызывает [`dotnet build`](../tools/dotnet-build.md) для подтверждения успешной сборки, а затем `dotnet <assembly.dll>` для запуска приложения.

    ```console
    $ dotnet run

    Hello World!
    ```

    Сведения о более сложных сценариях см. в статье [Развертывание приложений .NET Core](../deploying/index.md).

## <a name="dockerize-the-net-core-application"></a>Добавление приложения .NET Core в Docker

Консольное приложение Hello .NET Core успешно выполняется локально. Теперь продвинемся на шаг вперед, чтобы собрать и запустить приложение в Docker.

### <a name="your-first-dockerfile"></a>Ваш первый Dockerfile

Для начала работы откройте текстовый редактор. Мы все еще работаем из каталога Hello, где создали приложение.

Добавьте в новый файл приведенные ниже инструкции Docker для [контейнеров Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) или Linux. По завершении сохраните его в корне каталога Hello в виде **Dockerfile** без разрешения (вам может потребоваться задать тип файла `All types (*.*)` или другой аналогичный).

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
WORKDIR /app

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Dockerfile содержит инструкции сборки Docker, выполняемые последовательно.

Первой инструкцией должна быть [**FROM**](https://docs.docker.com/engine/reference/builder/#from). Она инициализирует новый этап сборки и задает базовый образ для остальных инструкций. Теги мультиархитектурности запрашивают контейнеры Windows или Linux в зависимости от [режима контейнеров](https://docs.docker.com/docker-for-windows/#switch-between-windows-and-linux-containers) Docker для Windows. Базовым образом для нашего примера является пакет 2.1-sdk из репозитория microsoft/dotnet.

```Dockerfile
FROM microsoft/dotnet:2.1-sdk
```

Инструкция [**WORKDIR**](https://docs.docker.com/engine/reference/builder/#workdir) задает рабочий каталог для всех оставшихся инструкций RUN, CMD, ENTRYPOINT, COPY и ADD в Dockerfile. Если этот каталог не существует, он создается. В этом случае WORKDIR задает каталог приложения.

```Dockerfile
WORKDIR /app
```

Инструкция [**COPY**](https://docs.docker.com/engine/reference/builder/#copy) копирует новые файлы или каталоги из исходного пути и добавляет их в файловую систему конечного контейнера. С этой инструкции мы копируем файл проекта C# в контейнер.

```Dockerfile
COPY *.csproj ./
```

Инструкция [**RUN**](https://docs.docker.com/engine/reference/builder/#run) выполняет все команды в новом слое поверх текущего образа и фиксирует результаты. Полученный зафиксированный образ используется на следующем шаге в Dockerfile. Мы запускаем **dotnet restore**, чтобы получить нужные зависимости файла проекта C#. 

```Dockerfile
RUN dotnet restore
```

Инструкция **COPY** копирует остальные файлы в контейнер на новые [слои](https://docs.docker.com/engine/userguide/storagedriver/imagesandcontainers/#images-and-layers).

```Dockerfile
COPY . ./
```

Мы публикуем приложение с помощью этой инструкции **RUN**. Команда [**dotnet publish**](../tools/dotnet-publish.md) компилирует приложение, считывает его зависимости, указанные в файле проекта, и публикует итоговый набор файлов в каталоге. Наше приложение публикуется с конфигурацией **выпуска** и выводит данные в каталог по умолчанию.

```Dockerfile
RUN dotnet publish -c Release -o out
```

Инструкция [**ENTRYPOINT**](https://docs.docker.com/engine/reference/builder/#entrypoint) предоставляет возможность запускать контейнер как исполняемый файл.

```Dockerfile
ENTRYPOINT ["dotnet", "out/Hello.dll"]
```

Теперь у вас есть Dockerfile, который:

* копирует приложение в образ;
* копирует зависимости приложения в образ;
* выполняет сборку приложения так, чтобы оно выполнялось как исполняемый файл.

### <a name="build-and-run-the-hello-net-core-app"></a>Сборка и запуск приложения Hello .NET Core

#### <a name="essential-docker-commands"></a>Основные команды Docker

Ниже указаны основные команды Docker:

* [docker build](https://docs.docker.com/engine/reference/commandline/build/)
* [docker run](https://docs.docker.com/engine/reference/commandline/run/)
* [docker ps](https://docs.docker.com/engine/reference/commandline/ps/)
* [docker stop](https://docs.docker.com/engine/reference/commandline/stop/)
* [docker rm](https://docs.docker.com/engine/reference/commandline/rm/)
* [docker rmi](https://docs.docker.com/engine/reference/commandline/rmi/)
* [docker image](https://docs.docker.com/engine/reference/commandline/image/)

#### <a name="build-and-run"></a>Сборка и запуск

Вы написали Dockerfile, теперь Docker создает приложение и затем запускает контейнер.

```console
docker build -t dotnetapp-dev .
docker run --rm dotnetapp-dev Hello from Docker
```

Выходные данные команды `docker build` должны быть аналогичны приведенным далее выходным данным консоли:

```console
Sending build context to Docker daemon   173.1kB
Step 1/7 : FROM microsoft/dotnet:2.1-sdk
 ---> 288f8c45f7c2
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
Successfully built 46db075bd98d
Successfully tagged dotnetapp-dev:latest
```

Как видно из выходных данных, подсистема Docker использует Dockerfile для создания контейнера.

Выходные данные команды `docker run` должны быть аналогичны приведенным далее выходным данным консоли:

```console
Hello World!
```

Поздравляем! Вы только что:
> [!div class="checklist"]
> * создали локальное приложение .NET Core;
> * создали Dockerfile для сборки первого контейнера;
> * создали и запустили приложение, добавленное в Docker.

## <a name="next-steps"></a>Следующие шаги

Ниже приведены некоторые действия, которые можно предпринять:

* [Вводный видеоролик об образах Docker для .NET](https://channel9.msdn.com/Shows/Code-Conversations/Introduction-to-NET-Docker-Images-with-Kendra-Havens?term=docker)
* [Преимущества совместного использования Visual Studio, Docker и экземпляров контейнеров Azure](https://medium.com/@AliMazaheri/visual-studio-docker-azure-container-instances-better-together-bf8c2f0419ae)
* [Краткие руководства по Docker для Azure](https://docs.docker.com/docker-for-azure/#docker-community-edition-ce-for-azure)
* [Развертывание приложения в Docker для Azure](https://docs.docker.com/docker-for-azure/deploy/)

> [!Note]
> Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.

## <a name="docker-images-used-in-this-sample"></a>Образы Docker, используемые в этом примере

В этом примере используются следующие образы Docker:

* [`microsoft/dotnet:2.1-sdk`](https://hub.docker.com/r/microsoft/dotnet)

## <a name="related-resources"></a>Связанные ресурсы

* [Примеры Docker для .NET Core](https://github.com/dotnet/dotnet-docker/tree/master/samples)
* [Dockerfile в контейнерах Windows](https://docs.microsoft.com/virtualization/windowscontainers/manage-docker/manage-windows-dockerfile)
* [Примеры Docker для .NET Framework](https://github.com/Microsoft/dotnet-framework-docker-samples)
* [ASP.NET Core в центре Docker](https://hub.docker.com/r/microsoft/aspnetcore/)
* [Добавление приложения .NET Core в Docker — руководство](https://docs.docker.com/engine/examples/dotnetcore/)
* [Работа со средствами Visual Studio для Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) 