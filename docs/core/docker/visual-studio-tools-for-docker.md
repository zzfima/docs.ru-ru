---
title: "Инструменты Visual Studio для Docker"
description: "Использование инструментов Visual Studio для Docker"
keywords: .NET, .NET Core, Docker, ASP.NET Core, Visual Studio
author: spboyer
ms.author: shboyer
ms.date: 04/27/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: dotnet
ms.assetid: 1f3b9a68-4dea-4b60-8cb3-f46164eedbbf
ms.translationtype: HT
ms.sourcegitcommit: 9bb17207ba72bb22f5d6db55e9d1bd77e3013445
ms.openlocfilehash: 113d470a55fd92704de0e6def392a6e0a1a3a118
ms.contentlocale: ru-ru
ms.lasthandoff: 08/25/2017

---

# <a name="visual-studio-tools-for-docker"></a>Инструменты Visual Studio для Docker

[Microsoft Visual Studio 2017](https://www.visualstudio.com/) с [Docker для Windows](https://docs.docker.com/docker-for-windows/install/) поддерживает сборку, отладку и выполнение веб-приложений и консольных приложений .NET Framework и .NET Core с использованием контейнеров Windows и Linux.

## <a name="prerequisites"></a>Предварительные требования

- [Microsoft Visual Studio 2017](https://www.visualstudio.com/) с рабочей нагрузкой .NET Core
- [Docker для Windows](https://docs.docker.com/docker-for-windows/install/)

## <a name="installation-and-setup"></a>Установка и настройка

Установите [Microsoft Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/install/install-visual-studio) с рабочей нагрузкой .NET Core.

Перед установкой Docker ознакомьтесь с разделом [Docker для Windows: что следует знать перед установкой](https://docs.docker.com/docker-for-windows/install/#what-to-know-before-you-install), а затем установите [Docker для Windows](https://docs.docker.com/docker-for-windows/install/).

Обязательная конфигурация Docker для Windows предполагает настройку **[общих дисков](https://docs.docker.com/docker-for-windows/#shared-drives)**. Этот параметр необходим для поддержки сопоставления и отладки томов.

Щелкните правой кнопкой мыши значок Docker в области уведомлений, выберите пункт **Параметры**, а затем **Общие диски**. Выберите диск, на котором Docker будет хранить файлы, и примените эти изменения.

![Общие диски](./media/visual-studio-tools-for-docker/settings-shared-drives-win.png)

## <a name="create-an-aspnet-web-application-and-add-docker-support"></a>Создание веб-приложения ASP.NET и добавление поддержки Docker

С помощью Visual Studio создайте веб-приложение ASP.NET Core. После загрузки приложения выберите пункт **Добавить поддержку Docker** в меню **Проект** или щелкните проект правой кнопкой мыши в обозревателе решений и выберите пункт **Добавить** > **Поддержка Docker**.

Меню "Проект"

!["Проект" > "Поддержка Docker"](./media/visual-studio-tools-for-docker/project-add-docker-support.png)

Контекстное меню проекта

![Щелкните правой кнопкой мыши и выберите пункт "Добавить" > "Поддержка Docker".](./media/visual-studio-tools-for-docker/right-click-add-docker-support.png)

При добавлении в проект поддержки Docker можно выбрать контейнеры Windows или Linux. (Узел Docker должен работать на контейнерах такого же типа. Если вам нужно изменить тип контейнера для работающего экземпляра Docker, щелкните правой кнопкой мыши значок **Docker** в области уведомлений и выберите **Switch to Windows containers** (Переключить на контейнеры Windows) или **Switch to Linux containers** (Переключить на контейнеры Linux). 

В проект будут добавлены указанные ниже файлы.

- **Dockerfile**. Файл Docker для приложений ASP.NET Core основан на образе [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore). Этот образ включает пакеты NuGet платформы ASP.NET Core, которые были предварительно скомпилированы JIT-компилятором для повышения производительности запуска. При создании консольных приложений .NET Core инструкция FROM в файле Dockerfile ссылается на самую последнюю версию образа [microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet).   
- **docker-compose.yml**. Базовый файл Compose в Docker, который служит для определения коллекции образов, сборка и выполнение которых будут выполняться с помощью команд docker-compose build и run.   
- **docker-compose.dev.debug.yml**. Дополнительный файл docker-compose с итеративными изменениями, применяемыми в конфигурации отладки. Для их объединения среда Visual Studio вызывает команду -f docker-compose.yml -f docker-compose.dev.debug.yml. Этот файл Compose используется средствами разработки Visual Studio.   
- **docker-compose.dev.release.yml**. Дополнительный файл Compose в Docker для отладки определения выпуска. Этот файл подключает отладчик к тому, чтобы он не менял содержимое рабочего образа.  

Файл docker-compose.yml содержит имя образа, создаваемого при выполнении проекта. 

```
version '2'

services:
  hellodockertools:
    image:  user/hellodockertools${TAG}
    build:
      context: .
      dockerfile: Dockerfile
    ports:
      - "80"
``` 

В этом примере `image: user/hellodockertools${TAG}` создает образ `user/hellodockertools:dev`, когда приложение выполняется в режиме **отладки**, и образ `user/hellodockertools:latest`, когда оно выполняется в режиме **выпуска**. 

Если вы планируете помещать образ в реестр, значение `user` необходимо изменить на имя пользователя Docker Hub. Например, измените его на `spboyer/hellodockertools` или на URL-адрес своего закрытого реестра `privateregistry.domain.com/` в зависимости от конфигурации.

### <a name="debugging"></a>Отладка

Выберите пункт **Docker** в раскрывающемся списке отладки на панели инструментов и нажмите клавишу F5, чтобы начать отладку приложения. 

- Будет получен образ microsoft/aspnetcore (если его еще нет в вашем кэше).
- Переменной ASPNETCORE_ENVIRONMENT в контейнере будет присвоено значение Development.
- Порт 80 будет открыт и сопоставлен с динамически назначаемым портом для localhost. Порт определяется узлом Docker и может запрашиваться с помощью команды docker ps. 
- Приложение будет скопировано в контейнер.
- Браузер по умолчанию запустится с подключенным к контейнеру отладчиком с использованием динамически назначаемого порта. 

В результате сборки образа Docker будет получен образ `dev` приложения с образами `microsoft/aspnetcore` в качестве базового образа.
Примечание. В образе dev нет содержимого приложения, так как конфигурации отладки используют подключение тома для обеспечения итеративности процесса. Чтобы отправить образ, используйте конфигурацию выпуска.

```console
REPOSITORY                  TAG         IMAGE ID            CREATED         SIZE
spboyer/hellodockertools    dev         0b6e2e44b3df        4 minutes ago   268.9 MB
microsoft/aspnetcore        1.0.1       189ad4312ce7        5 days ago      268.9 MB
```

Приложение выполняется с помощью контейнера, который можно увидеть, выполнив команду `docker ps`.

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   4 minutes ago       Up 4 minutes        0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="edit-and-continue"></a>Изменить и продолжить

Изменения статических полей и файлов шаблонов Razor (CSHTML) применяются автоматически без необходимости выполнять этап компиляции. Внесите изменение, сохраните его и нажмите кнопку "Обновить" в браузере, чтобы увидеть обновление.  

Для внесения изменений в файлы кода требуются компиляция и перезапуск Kestrel в контейнере. После внесения изменения нажмите клавиши CTRL+F5, чтобы выполнить процесс и запустить приложение без контейнера. Повторная сборка или остановка контейнера Docker не производится. Выполнив команду `docker ps` в командной строке, можно увидеть, что исходный контейнер по-прежнему выполняется, как и 10 минут назад. 

```console
CONTAINER ID        IMAGE                          COMMAND               CREATED             STATUS              PORTS                   NAMES
3f240cf686c9        spboyer/hellodockertools:dev   "tail -f /dev/null"   10 minutes ago      Up 10 minutes       0.0.0.0:32769->80/tcp   hellodockertools_hellodockertools_1
```

### <a name="publishing-docker-images"></a>Публикация образов Docker

После завершения цикла разработки и отладки приложения инструменты Visual Studio для Docker помогут вам создать рабочий образ приложения. Выберите в раскрывающемся списке отладки значение **Выпуск** и выполните сборку приложения. Инструментарий создаст образ с тегом `:latest`, который можно отправить в закрытый реестр или в Docker Hub. 

С помощью команды `docker images` можно получить список образов.

```console
REPOSITORY                 TAG                 IMAGE ID            CREATED             SIZE
spboyer/hellodockertools   latest              8184ae38ba91        5 seconds ago       278.4 MB
spboyer/hellodockertools   dev                 0b6e2e44b3df        About an hour ago   268.9 MB
microsoft/aspnetcore       1.0.1               189ad4312ce7        5 days ago          268.9 MB
```

Вы могли ожидать, что рабочий образ или образ выпуска будет иметь меньший размер, чем образ **dev**. Однако из-за использования сопоставления томов отладчик и приложение на самом деле выполнялись с локального компьютера, а не в контейнере. В образ **latest** был упакован весь код приложения, необходимый для его выполнения на компьютере узла, поэтому эта разница соответствует размеру кода приложения.

