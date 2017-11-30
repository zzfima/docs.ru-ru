---
title: "Создание образов Docker для .NET Core"
description: "Общие сведения об образах Docker и .NET Core"
keywords: .NET, .NET Core, Docker
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
ms.openlocfilehash: 3ec2d5a58b46e332de41b618f1c3fac663b29bee
ms.sourcegitcommit: 5fb6646b5ee3769ffb214e672041833ea4ceeb26
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2017
---
# <a name="building-docker-images-for-net-core-applications"></a>Создание образов Docker для приложений .NET Core

 В этом учебнике рассматривается использование .NET Core на Docker. Во-первых мы исследуем различные изображения Docker предлагаемых и поддерживаются корпорацией Майкрософт и вариантов использования. Затем рассказано способ построения и dockerize приложения ASP.NET Core.

В ходе этого учебника вы узнаете:
> [!div class="checklist"]
> * Дополнительные сведения о Microsoft .NET Core Docker images 
> * Получить ASP.NET Core примера приложения для Dockerize
> * Пример приложения ASP.NET запускаются
> * Построение и запуск образца с помощью Docker для контейнеров Linux
> * Построение и запуск образца с помощью контейнеров Docker для Windows

## <a name="docker-image-optimizations"></a>Оптимизация образов Docker

При создании образов Docker для разработчиков мы сосредоточились на трех основных сценариях:

* образы, используемые для разработки приложений .NET Core;
* образы, используемые для сборки приложений .NET Core;
* образы, используемые для выполнения приложений .NET Core.

Зачем нужны три образа
При разработке, построении и запуске приложений в контейнерах, у нас есть различные приоритеты.

* **Разработка:** приоритет уделяется быстро перечисления изменений, а также возможность отладки изменения. Размер изображения не столь важно, вместо этого можно внести изменения в код и быстро просматривать их?

* **Сборка:** этот образ содержит все необходимое для компиляции приложения, включая компилятор и другие зависимости, для оптимизации двоичных файлов.  Вы используете образ сборки для создания активов, размещаемых в рабочей среде образ. Образ сборки будет использоваться для непрерывной интеграции или в среде построения. Такой подход позволяет агент сборки для компиляции и построения приложения (с необходимые зависимости) в экземпляре сборки образа. Агенту сборки необходимо знать только, как запускать этот образ Docker.

* **Порождение:** как быстро развернуть и запустить образ? Этот образ мал, поэтому производительность сети из реестра Docker на узлах Docker оптимизирован. Содержимое готово к запуску, поэтому период времени от запуска Docker до обработки результатов минимален. В модели Docker динамической компиляции кода не требуется. Содержимое, помещаемое в этот образ, ограничено двоичными файлами и содержимым, которые необходимы для работы приложения.

    Например `dotnet publish` содержит выходные данные:

    * скомпилированные двоичные файлы
    * .js и CSS-файлы


Причина для включения `dotnet publish` будут сохранены выходные данные команды в рабочей среде образ его "размер до минимума.

Некоторые образы .NET Core Общие слои между различия в тегах, загружает последние тег является довольно простой. Если уже имеется более старой версии на компьютере, эта архитектура снижает необходимое дисковое пространство.

Если несколько приложений используют общие образы на том же компьютере, память распределяется между общие образы. Изображения должны совпадать для совместного использования.

## <a name="docker-image-variations"></a>Варианты образов Docker

Для достижения целей выше, мы предоставляем варианты образа в разделе [ `microsoft/dotnet` ](https://hub.docker.com/r/microsoft/dotnet/).

* `microsoft/dotnet:<version>-sdk`(`microsoft/dotnet:2.0.0-sdk`) Этот образ содержит Core SDK .NET, включая .NET Core и средства командной строки (CLI). Этот образ соответствует **сценарию развертывания**. Использование этого образа для локальной разработки, отладки и тестирования модулей. Этот образ также можно использовать для сценариев **сборки**. С помощью `microsoft/dotnet:sdk` всегда позволяет получить последнюю версию.

> [!TIP]
> Если вы не знаете о вашим потребностям, вы хотите использовать `microsoft/dotnet:<version>-sdk` изображения. Как «фактически» изображение, она предназначена для использования в качестве исключения размещения контейнера (подключить исходный код и запустите контейнер для запуска приложения) и в качестве базового образа для создания других образов из.

* `microsoft/dotnet:<version>-runtime`: Этот образ содержит основные функции .NET (среды выполнения и библиотек) и оптимизирован для запущенных приложений .NET Core **рабочей**.

## <a name="alternative-images"></a>Альтернативные образы

Помимо образов, оптимизированных для разработки, сборки и рабочей среды, мы предоставляем дополнительные образы.

* `microsoft/dotnet:<version>-runtime-deps`: **Deps среды выполнения** образ содержит операционную систему с все собственного зависимости, необходимые для .NET Core. Этот образ является для [автономные приложения](https://docs.microsoft.com/dotnet/core/deploying/index).

Последние версии каждого варианта:

* `microsoft/dotnet`или `microsoft/dotnet:latest` (псевдоним для образа SDK)
* `microsoft/dotnet:sdk`
* `microsoft/dotnet:runtime`
* `microsoft/dotnet:runtime-deps`

## <a name="samples-to-explore"></a>Образцы для исследования

* [В этом примере ASP.NET Core Docker](https://github.com/dotnet/dotnet-docker-samples/tree/master/aspnetapp) показан шаблон лучший подход для создания образов Docker для ASP.NET Core приложений для рабочей среды. Образец работает с контейнерами Windows и Linux.

* В этом примере .NET Core Docker демонстрируется лучше всего рекомендаций для [построения образов Docker для приложений .NET Core для рабочей среды.](https://github.com/dotnet/dotnet-docker-samples/tree/master/dotnetapp-prod)

## <a name="your-first-aspnet-core-docker-app"></a>Своего первого приложения ASP.NET Core Docker

В этом учебнике позволяет использовать образец приложения ASP.NET Core Docker для приложения, которое мы хотим dockerize. В этом образце приложения ASP.NET Core Docker показан шаблон лучший подход для создания образов Docker для ASP.NET Core приложений для рабочей среды. Образец работает с контейнерами Windows и Linux.

В образце Dockerfile создается образ Docker приложения ASP.NET Core на основе этих базового образа Docker среды выполнения ASP.NET Core.

Она использует [Docker многоэтапным построения функции](https://docs.docker.com/engine/userguide/eng-image/multistage-build/) для:

* Построение образца в контейнере на основе **больше** базового образа Docker сборки ASP.NET Core 
* копирует результат последнего построения в Docker изображение на основе **меньше** базового образа среды выполнения ASP.NET Core Docker

> [!Note]
> Образ сборки содержит необходимые средства для создания приложений, а образа среды выполнения — нет.

### <a name="prerequisites"></a>Предварительные требования

Построение и запуск, установите следующие элементы:

#### <a name="net-core-20-sdk"></a>.NET core 2.0 SDK

* Установка [.NET Core SDK 2.0](https://www.microsoft.com/net/core).

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

#### <a name="installing-git-for-sample-repository"></a>Установка Git для образца репозитория

* Установка [git](https://git-scm.com/download) чтобы клонировать репозиторий.

### <a name="getting-the-sample-application"></a>Получение примера приложения

Самый простой способ получить образец — путем клонирования [репозитории samples](https://github.com/dotnet/dotnet-docker-samples) с git, выполнив следующие инструкции: 

```console
git clone https://github.com/dotnet/dotnet-docker-samples/
```

Можно также загрузить хранилище (небольшой) как ZIP-файл, из репозитория примеров .NET Core Docker.

### <a name="run-the-aspnet-app-locally"></a>Приложение ASP.NET запускается локально

Чтобы получить ориентир, перед упаковкой приложения в контейнер запустите его локально.

Можно построить и запустите приложение локально с 2.0 SDK .NET Core с помощью следующих команд (инструкции предполагают корень репозитория):

```console
cd aspnetapp
dotnet run
```

После запуска приложения, посетите **http://localhost: 5000** в веб-браузере.

### <a name="build-and-run-the-sample-with-docker-for-linux-containers"></a>Построение и запуск образца с помощью Docker для контейнеров Linux

Можно построить и запустите образец в Docker с контейнерами Linux с помощью следующих команд (инструкции предполагают корень репозитория):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm -p 5000:80 --name aspnetcore_sample aspnetapp
```

> [!Note] `docker run` "-P" аргумент сопоставления порта 5000 на локальном компьютере для порта 80 в контейнере (форма сопоставления порта `host:container`). Дополнительные сведения см. в разделе [запуска docker](https://docs.docker.com/engine/reference/commandline/exec/) ссылки на параметры командной строки.

После запуска приложения, посетите **http://localhost: 5000** в веб-браузере.

### <a name="build-and-run-the-sample-with-docker-for-windows-containers"></a>Построение и запуск образца с помощью контейнеров Docker для Windows

Можно построить и запустите образец в Docker с помощью контейнеров Windows, с помощью следующих команд (инструкции предполагают корень репозитория):

```console
cd aspnetapp
docker build -t aspnetapp .
docker run -it --rm --name aspnetcore_sample aspnetapp
```

> [!IMPORTANT]
> Необходимо перейти **IP-адрес контейнера** (в отличие от «http://localhost») в браузере напрямую при использовании контейнеров Windows. Можно получить IP-адрес контейнера с помощью следующих действий:

* Откройте другую командную строку.
* Запустите `docker ps` для просмотра вашего запущенные контейнеры. Контейнер «aspnetcore_sample» должно быть существует.
* Запустите `docker exec aspnetcore_sample ipconfig`.
* IP-адрес контейнера, скопируйте и вставьте в адресную строку браузера (например, 172.29.245.43).

> [!Note]
> Docker exec поддерживает идентифицирующие контейнеры с именем или hash. В нашем примере используется имя (aspnetcore_sample).

См. следующий пример того, как получить IP-адрес из запущенного контейнера Windows.

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

> [!Note]
> Docker exec запускает новую команду в запущенного контейнера. Дополнительные сведения см. в разделе [docker exec ссылка](https://docs.docker.com/engine/reference/commandline/exec/) о параметрах командной строки.

Вы можете создавать приложения, которое будет готово к развертыванию в рабочей среде локально с помощью [публикации dotnet](../tools/dotnet-publish.md) команды.

```console
dotnet publish -c release -o published
```

> [!Note]
> Аргумент - c выпуска построения приложения в режиме выпуска (по умолчанию используется режим отладки). Дополнительные сведения см. в разделе [dotnet запуска ссылку](../tools/dotnet-run.md) о параметрах командной строки.

Приложение можно запустить **Windows** с помощью следующей команды.

```console
dotnet published\aspnetapp.dll
```

Приложение можно запустить **Linux** или **macOS** с помощью следующей команды.

```bash
dotnet published/aspnetapp.dll
```

### <a name="docker-images-used-in-this-sample"></a>Docker изображений, используемых в этом образце

В этом образце используются следующие образы Docker

* `microsoft/aspnetcore-build:2.0`
* `microsoft/aspnetcore:2.0`

Поздравляем! у вас есть только:
> [!div class="checklist"]
> * Узнали о Microsoft .NET Core Docker images
> * Получить ASP.NET Core примера приложения для Dockerize
> * Запускался локально в пример приложения ASP.NET
> * Построения и запуска образца с помощью Docker для контейнеров Linux
> * Построения и запуска образца с помощью контейнеров Docker для Windows


**Дальнейшие действия**

Ниже приведены действия, которые можно предпринять.

* [Работа со средствами Visual Studio Docker](https://docs.microsoft.com/aspnet/core/publishing/visual-studio-tools-for-docker)
* [Развертывание образов Docker из реестра контейнер Azure с экземплярами Azure контейнера](https://blogs.msdn.microsoft.com/stevelasker/2017/07/28/deploying-docker-images-from-the-azure-container-registry-to-azure-container-instances/)
* [Отладка с кодом Visual Studio](https://code.visualstudio.com/docs/nodejs/debugging-recipes#_nodejs-typescript-docker-container) 
* [Получение руки по с помощью Visual Studio для Mac, контейнеры и без сервера кода в облаке](https://blogs.msdn.microsoft.com/visualstudio/2017/08/31/hands-on-with-visual-studio-for-mac-containers-serverless-code-in-the-cloud/#comments)
* [Начало работы с Docker и Visual Studio для Mac лаборатории](https://github.com/Microsoft/vs4mac-labs/tree/master/Docker/Getting-Started)

> [!Note]
> Если у вас подписка на Azure, [Зарегистрируйтесь](https://azure.microsoft.com/free/?b=16.48) для бесплатной 30-дневной учетной записи и get 200 в кредиты Azure, чтобы испытать любое сочетание служб Azure.
