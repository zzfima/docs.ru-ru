---
title: Создание образов Docker для .NET Core
description: Общие сведения об образах Docker и .NET Core
author: jralexander
ms.author: johalex
ms.date: 11/06/2017
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f539efe15ce68a77890538430a170da64ff325e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="building-docker-images-for-net-core-applications"></a>Создание образов Docker для приложений .NET Core

 Это руководство посвящено использованию .NET Core в Docker. Сначала мы рассмотрим различные образы Docker, предоставляемые и поддерживаемые корпорацией Майкрософт, а также варианты их использования. Потом мы научимся создавать и добавлять в Docker приложение ASP.NET Core.

В ходе работы с этим руководством вы:
> [!div class="checklist"]
> * узнаете о создании образов Docker для Microsoft .NET Core; 
> * получите пример приложения ASP.NET Core для добавления в Docker;
> * запустите пример приложения ASP.NET локально;
> * создадите и запустите пример с Docker для контейнеров Linux;
> * Создание и запуск примера с Docker для контейнеров Windows

## <a name="docker-image-optimizations"></a>Оптимизация образов Docker

При создании образов Docker для разработчиков мы сосредоточились на трех основных сценариях:

* образы, используемые для разработки приложений .NET Core;
* образы, используемые для сборки приложений .NET Core;
* образы, используемые для выполнения приложений .NET Core.

Зачем нужны три образа
При разработке, сборке и выполнении приложений в контейнерах приоритеты будут разными.

* **Разработка**. Основное внимание уделяется быстрой итерации по изменениям и возможности их отладки. Размер образа не так важен, как возможность быстро вносить изменения в код и просматривать их.

* **Сборка**. Этот образ содержит все необходимое для компиляции приложения, включая компилятор и другие зависимости для оптимизации двоичных файлов.  Образ сборки нужен для создания ресурсов, помещаемых в рабочий образ. Этот образ будет применяться при непрерывной интеграции или в среде сборки. Такой подход позволяет агенту сборки компилировать и собрать приложение (со всеми необходимыми зависимостями) в экземпляре образа сборки. Агенту сборки необходимо знать только, как запускать этот образ Docker.

* **Рабочая среда**. Как можно быстро развернуть и запустить образ. Этот образ имеет небольшой размер, что позволяет оптимизировать передачу по сети из реестра Docker на узлы Docker. Содержимое готово к запуску, поэтому период времени от запуска Docker до обработки результатов минимален. В модели Docker динамическая компиляция кода не требуется. Содержимое, помещаемое в этот образ, ограничено двоичными файлами и содержимым, которые необходимы для работы приложения.

    Например, выходные данные `dotnet publish` содержат:

    * скомпилированные двоичные файлы;
    * файлы JS и CSS.


Причиной для включения выходных данных команды `dotnet publish` в рабочий образ является стремление свести его размер к минимуму.

Некоторые образы .NET Core совместно используют слои между разными тегами, поэтому скачивание последнего тега осуществляется довольно просто. Если на компьютере уже есть более старая версия, эта архитектура снижает необходимое дисковое пространство.

Когда несколько приложений используют общие образы на одном компьютере, память используется этими общими образами совместно. Для совместного использования образы должны совпадать.

## <a name="docker-image-variations"></a>Варианты образов Docker

Для достижения указанных выше целей мы предоставляет варианты образов в [`microsoft/dotnet`](https://hub.docker.com/r/microsoft/dotnet/).

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Этот образ содержит пакет SDK для .NET Core, который включает платформу .NET Core и программы командной строки (CLI). Этот образ соответствует **сценарию развертывания**. Он используется для локальной разработки, отладки и модульного тестирования. Этот образ также можно использовать для сценариев **сборки**. Использование `microsoft/dotnet:sdk` всегда предоставляет последнюю версию.

> [!TIP]
> Если вы точно не знаете о своих потребностях, рекомендуется использовать образ `microsoft/dotnet:<version>-sdk`. Являясь образом "де-факто", он предназначен для использования в качестве одноразового контейнера (подключите исходный код и запустите контейнер для запуска приложения) и в качестве базового образа для создания других образов.

* `microsoft/dotnet:<version>-runtime`. Этот образ содержит .NET Core (среду выполнения и библиотеки) и оптимизирован для запуска приложений .NET Core в **рабочей среде**.

## <a name="alternative-images"></a>Альтернативные образы

Помимо образов, оптимизированных для разработки, сборки и рабочей среды, мы предоставляем дополнительные образы.

* `microsoft/dotnet:<version>-runtime-deps`. Образ **runtime-deps** содержит операционную систему со всеми собственными зависимостями, требуемыми платформе .NET Core. Этот образ предназначен для [автономных приложений](../deploying/index.md).

Последние версии каждого варианта:

* `microsoft/dotnet` или `microsoft/dotnet:latest` (псевдоним для образа SDK)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Примеры для изучения

* [В этом примере Docker для ASP.NET Core](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) демонстрируется рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде. Этот пример поддерживается в контейнерах Linux и Windows.

* В этом примере Docker для .NET Core демонстрируется рекомендуемый шаблон [создания образов Docker для приложений .NET Core в рабочей среде](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod).

## <a name="your-first-aspnet-core-docker-app"></a>Ваше первое приложение Docker для ASP.NET Core

В этом руководстве мы будем использовать пример приложения Docker для ASP.NET Core в качестве приложения, которое хотим добавить в Docker. Этот пример приложения Docker для ASP.NET Core демонстрирует рекомендуемый шаблон создания образов Docker для приложений ASP.NET Core в рабочей среде. Этот пример поддерживается в контейнерах Linux и Windows.

Пример Dockerfile создает образ Docker для приложения ASP.NET Core на основе базового образа Docker для среды выполнения ASP.NET Core.

Он использует [функцию многоэтапной сборки Docker](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) для:

* сборки примера в контейнере на основе **большего по размеру** базового образа Docker сборки ASP.NET Core; 
* копирование итогового результата сборки в образ Docker на основе **меньшего по размеру** базового образа среды выполнения Docker для ASP.NET Core.

> [!NOTE]
> Образ сборки содержит необходимые средства для создания приложений, а образ среды выполнения — нет.

### <a name="prerequisites"></a>Предварительные требования

Чтобы выполнить сборку и запуск, установите следующие компоненты:

#### <a name="net-core-20-sdk"></a>Пакет SDK для .NET Core 2.0

* Установите [пакет SDK для .NET Core 2.0](https://www.microsoft.com/net/core).

* Установите любой привычный для вас редактор кода, если еще не сделали этого.

> [!TIP]
> Нужно ли устанавливать редактор кода? Попробуйте использовать [Visual Studio](https://visualstudio.com/downloads).

#### <a name="installing-docker-client"></a>Установка клиента Docker

Установите клиент [Docker 17.06](https://docs.docker.com/release-notes/docker-ce/) или более поздней версии.

Клиент Docker можно установить в:

* Дистрибутивах Linux

   * [CentOS](https://www.docker.com/docker-centos-distribution)

   * [Debian](https://www.docker.com/docker-debian)

   * [Fedora](https://www.docker.com/docker-fedora)

   * [Ubuntu](https://www.docker.com/docker-ubuntu)

* [macOS](https://docs.docker.com/docker-for-mac/)

* [Windows](https://docs.docker.com/docker-for-windows/)

#### <a name="installing-git-for-sample-repository"></a>Установка Git для образца репозитория

* Установите [git](https://git-scm.com/download), если хотите клонировать репозиторий.

### <a name="getting-the-sample-application"></a>Получение примера приложения

Чтобы получить пример, проще всего клонировать [репозиторий с примерами](https://github.com/dotnet/dotnet-docker-samples) с git, руководствуясь следующими инструкциями: 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

Вы также можете скачать этот репозиторий (он довольно небольшой) в виде ZIP-файла из репозитория примеров Docker для .NET Core.

### <a name="run-the-aspnet-app-locally"></a>Запуск приложения ASP.NET локально

Чтобы получить ориентир, перед упаковкой приложения в контейнер запустите его локально.

Вы можете создать и запустить приложение локально с помощью пакета SDK для .NET Core 2.0, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):

```console
cd aspnetapp
dotnet run
```

После запуска приложения перейдите по адресу **http://localhost:5000** в веб-браузере.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Создание и запуск примера с Docker для контейнеров Linux

Вы можете создать и запустить пример в Docker с помощью контейнеров Linux, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!NOTE]
> Аргумент `docker run` "-p" сопоставляет порт 5000 на локальном компьютере с портом 80 в контейнере (форма сопоставления порта — `host:container`). Дополнительные сведения см. в справочнике по команде [docker run](https://docs.docker.com/engine/reference/commandline/exec/) с описанием параметров командной строки.

После запуска приложения перейдите по адресу **http://localhost:5000** в веб-браузере.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Создание и запуск примера с Docker для контейнеров Windows

Вы можете создать и запустить пример в Docker с помощью контейнеров Windows, используя следующие команды (в инструкциях предполагается, что вы находитесь в корне репозитория):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> При использовании контейнеров Windows вам нужно перейти прямо по **IP-адресу контейнера** (а не по адресу http://localhost) в браузере. Вы можете получить IP-адрес контейнера с помощью следующих действий:

* Откройте другую командную строку.
* Запустите `docker ps` для просмотра запущенных контейнеров. В списке должен присутствовать контейнер "aspnetcore_sample".
* Запустите `docker exec aspnetcore_sample ipconfig`.
* Скопируйте IP-адрес контейнера и вставьте в адресную строку браузера (например, 172.29.245.43).

> [!NOTE]
> Исполняемый файл Docker поддерживает идентификацию контейнеров по имени или хэшу. В нашем примере используется имя (aspnetcore_sample).

См. следующий пример, показывающий, как получить IP-адрес запущенного контейнера Windows.

```console
docker exec aspnetcore_sample ipconfig

Windows IP Configuration

Ethernet adapter Ethernet:

   Connection-specific DNS Suffix  . : contoso.com
   Link-local IPv6 Address . . . . . : fe80::1967:6598:124:cfa3%4
   IPv4 Address. . . . . . . . . . . : 172.29.245.43
   Subnet Mask . . . . . . . . . . . : 255.255.240.0
   Default Gateway . . . . . . . . . : 172.29.240.1
```

> [!NOTE]
> Исполняемый файл Docker выполняет новую команду в запущенном контейнере. Дополнительные сведения см. в справочнике по команде [docker exec](https://docs.docker.com/engine/reference/commandline/exec/) с описанием параметров командной строки.

Вы можете создать приложение, готовое к развертыванию в рабочей среде, локально с помощью команды [dotnet publish](../tools/dotnet-publish.md).

```console
dotnet publish -c release -o published
```

> [!NOTE]
> Аргумент выпуска -c приводит к сборке приложения в режиме выпуска (по умолчанию используется режим отладки). Дополнительные сведения см. в справочнике по команде [dotnet run](../tools/dotnet-run.md) с описанием параметров командной строки.

Запустить приложение в **Windows** можно с помощью приведенной ниже команды.

```console
dotnet published\aspnetapp.dll
```

Запустить приложение в **Linux** или **macOS** можно с помощью приведенной ниже команды.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>Образы Docker, используемые в этом примере

В этом примере используются следующие образы Docker:

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

Поздравляем! Вы только что:
> [!div class="checklist"]
> * узнали о создании образов Docker для Microsoft .NET Core;
> * получили пример приложения ASP.NET Core для добавления в Docker;
> * запустили пример приложения ASP.NET локально;
> * создали и запустили пример с Docker для контейнеров Linux;
> * создали и запустили пример с Docker для контейнеров Windows.


**Следующие шаги**

Ниже приведены некоторые действия, которые можно предпринять:

* [Работа со средствами Visual Studio для Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Развертывание образов Docker из реестра контейнеров Azure в службе "Экземпляры контейнеров Azure](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/) 
* [Отладка с помощью Visual Studio Code](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Получение практических навыков по работе с Visual Studio для Mac, контейнерами и бессерверным кодом в облаке](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Getting started integrating with Docker containers in Visual Studio for Mac](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started) (Приступая к интеграции с контейнерами Docker в Visual Studio для Mac)

> [!NOTE]
> Если у вас нет подписки Azure, [зарегистрируйте сейчас](https://azure.microsoft.com/free/?b=16.48) бесплатную учетную запись на 30 дней и получите 200 долл. США на счет в Azure, чтобы опробовать любое сочетание служб Azure.
