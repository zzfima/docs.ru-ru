---
title: "Перенос приложений ASP.NET MVC в контейнеры Windows"
description: "Узнайте, как запустить существующее приложение ASP.NET MVC в контейнере Windows Docker"
keywords: "Контейнеры Windows, Docker, ASP.NET MVC"
author: BillWagner
ms.author: wiwagn
ms.date: 02/01/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: dotnet-mvc
ms.devlang: dotnet
ms.assetid: c9f1d52c-b4bd-4b5d-b7f9-8f9ceaf778c4
translationtype: Human Translation
ms.sourcegitcommit: fcfd1053cdb161b3ebe1ae61b84c90e68b94a26b
ms.openlocfilehash: 6534435823e32aa5c61802ccc587c2761a3fe893

---

# <a name="migrating-aspnet-mvc-applications-to-windows-containers"></a>Перенос приложений ASP.NET MVC в контейнеры Windows

При запуске существующего приложения на основе .NET Framework в контейнере Windows не требуется вносить изменения в приложение. Чтобы запустить приложение в контейнере Windows, создайте образ Docker с приложением и запустите контейнер. В этом разделе показано, как получить существующее [приложение ASP.NET MVC](http://www.asp.net/mvc) и развернуть его в контейнере Windows.

Начните с существующего приложения ASP.NET MVC и выполните сборку опубликованных ресурсов с помощью Visual Studio. Docker используется для создания образа, который содержит и запускает ваше приложение. Вы перейдете на сайт, запущенный в контейнере Windows, и проверите, работает ли приложение.

Для понимания этой статьи требуется базовое знакомство с Docker. Сведения о Docker см. в разделе [Общие сведения о Docker](https://docs.docker.com/engine/understanding-docker/).

Приложение, которое будет работать в контейнере — это простой веб-сайт, который случайным образом отвечает на вопросы. Это базовое приложение MVC без проверки подлинности и хранилища базы данных. Оно позволяет сосредоточиться на перемещении веб-уровня в контейнер. В дальнейших темах показано, как перемещать постоянное хранилище и управлять им в контейнерных приложениях.

Перемещение приложения состоит из следующих действий.

1. [Создание задачи публикации для сборки ресурсов образа](#publish-script).
2. [Создание образа Docker, в котором будет запускаться приложение](#build-the-image).
3. [Запуск контейнера Docker, в котором будет запускаться образ](#start-a-container).
4. [Проверка приложения с помощью браузера](#verify-in-the-browser).

[Готовое приложение](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator) находится на GitHub.

## <a name="prerequisites"></a>Предварительные требования

Компьютер разработки должен быть запущен
- [Юбилейное обновление Windows 10](https://www.microsoft.com/en-us/software-download/windows10/) (или выше) либо [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server) (или выше). 
- [Docker для Windows](https://docs.docker.com/docker-for-windows/) — версия Stable 1.13.0 или 1.12 Beta 26 (или более поздние)
- [Visual Studio 2015](https://www.visualstudio.com/en-us/visual-studio-homepage-vs.aspx).

> [!IMPORTANT]
> При использовании Windows Server 2016 выполните инструкции по [развертыванию узла контейнеров в Windows Server](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment).

После установки и запуска Docker щелкните правой кнопкой мыши значок на панели задач и выберите **Переключиться на контейнеры Windows**. Это нужно для запуска образов Docker на основе Windows. На выполнение этой команды требуется несколько секунд:

![Контейнер Windows][windows-container]

## <a name="publish-script"></a>Публикация скрипта

Соберите вместе все ресурсы, которые нужно загрузить в образ Docker. Для создания профиля публикации приложения в Visual Studio есть команда **Опубликовать**. В этом профиле все ресурсы будут собраны в одном дереве каталогов, которое далее в этом учебнике вам нужно будет скопировать в свой целевой образ.

**Этапы публикации**

1. Щелкните правой кнопкой мыши веб-проект в Visual Studio и выберите **Publish** (Публикация).
2. Нажмите кнопку **Пользовательский профиль**, а затем выберите **Файловая система** в качестве метода.
3. Выберите каталог. По правилам загруженный образец использует `bin/PublishOutput`.

![Публикация: подключение][publish-connection]

Откройте раздел **Параметры публикации файла** на вкладке **Параметры**. Выберите **Precompile during publishing** (Предварительная компиляция во время публикации). Эта оптимизация означает, что представления не будут компилироваться в контейнере Docker, вместо этого будут копироваться предварительно скомпилированные представления.

![Публикация: параметры][publish-settings]

Нажмите кнопку **Publish** (Публикация), и Visual Studio скопирует все необходимые ресурсы в целевую папку. 

## <a name="build-the-image"></a>Сборка образа

Определение образа Docker в Dockerfile. Dockerfile содержит инструкции для базового образа, дополнительные компоненты, приложение, которое нужно запустить, и другие образы конфигурации.  Dockerfile содержит входные параметры для команды `docker build`, которая создает образ.

Вы создадите образ на основе образа `microsft/aspnet`, расположенного на [Docker Hub](https://hub.docker.com/r/microsoft/aspnet/).
Базовый образ `microsoft/aspnet` — это образ Windows Server. Он содержит Windows Server Core, IIS и ASP.NET 4.6.2. При запуске этого образа в контейнере он автоматически использует IIS и установленные веб-сайты.

Dockerfile, который создает образ, выглядит следующим образом:

```
# The `FROM` instruction specifies the base image. You are
# extending the `microsoft/aspnet` image.

FROM microsoft/aspnet

# Next, this Dockerfile creates a directory for your application
RUN mkdir C:\randomanswers

# configure the new site in IIS.
RUN powershell -NoProfile -Command \
    Import-module IISAdministration; \
    New-IISSite -Name "ASPNET" -PhysicalPath C:\randomanswers -BindingInformation "*:8000:"

# This instruction tells the container to listen on port 8000. 
EXPOSE 8000

# The final instruction copies the site you published earlier into the container.
ADD containerImage/ /randomanswers
```

В Dockerfile нет команды `ENTRYPOINT`. Она не нужна.
Базовый образ гарантирует, что служба IIS запускается при запуске контейнера. 

Выполните команду сборки Docker, чтобы создать образ, который запускает приложение ASP.NET. Для этого откройте окно PowerShell и введите следующую команду в каталоге решения:

```
docker build -t mvcrandomanswers .
```

Эта команда создаст новый образ в соответствии с инструкциями в Dockerfile. Это может включать получение базового образа из [Docker Hub](http://hub.docker.com). После этого в образ будет добавлено приложение.

После выполнения этой команды можно выполнить команду `docker images` для просмотра сведений о новом образе:

```
REPOSITORY                    TAG                 IMAGE ID            CREATED             SIZE
mvcrandomanswers              latest              86838648aab6        2 minutes ago       8.104 GB
```

Идентификатор IMAGE ID на вашем компьютере будет другим. Теперь запустим приложение.

## <a name="start-a-container"></a>Запуск контейнера

Чтобы запустить контейнер, нужно выполнить следующую команду `docker run`:

```
docker run -d -p 8000:8000 --name randomanswers mvcrandomanswers
```

Аргумент `-d` предписывает Docker запустить образ в отсоединенном режиме. Это значит, что образ Docker запускается в отрыве от текущей оболочки.

Аргумент `-p 8000:8000` указывает Docker, как сопоставить порты входящего трафика. В этом примере мы используем порт 8000 на узле и в контейнере.

Аргумент `--name randomanswers` содержит имя запущенного контейнера. Это имя можно использовать вместо идентификатора контейнера в большинстве команд.

`mvcrandomanswers` — это имя запускаемого образа.

## <a name="verify-in-the-browser"></a>Проверка в браузере

> [!NOTE]
> В текущем выпуске невозможно перейти на `http://localhost`.
> Это связано с известным поведением в WinNAT. В будущем проблема будет устранена. А пока этого не произошло, необходимо использовать IP-адрес контейнера.

После запуска контейнера найдите его IP-адрес. В этом случае вы сможете подключиться к запущенному контейнеру из браузера:

```
docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" randomanswers
172.31.194.61
```

Подключитесь к запущенному контейнеру, указав IPv4-адрес и настроенный порт (8000), `http://172.31.194.61:8000` (см. пример). Введите этот URL-адрес в адресной строке браузера, и вы увидите работающий сайт.

> [!NOTE]
> Некоторые программы VPN или прокси-серверы могут препятствовать переходу на ваш узел.
> Их можно временно отключить, чтобы убедиться, что контейнер работает.

Каталог образцов на GitHub содержит [Сценарий PowerShell](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator/run.ps1), который выполняет эти команды за вас. Откройте окно PowerShell, перейдите в каталог решения и введите команду:

```
./run.ps1
```

Она создает образ, отображает список образов на компьютере, запускает контейнер и отображает IP-адрес для этого контейнера. 

Чтобы остановить контейнер, выполните команду `docker
stop`:

```
docker stop randomanswers
```

Чтобы удалить контейнер, выполните команду `docker rm`:

```
docker rm randomanswers
```

[windows-container]: media/aspnetmvc/SwitchContainer.png "Переключение на контейнер Windows"
[publish-connection]: media/aspnetmvc/PublishConnection.png "Публикация в файловой системе"
[publish-settings]: media/aspnetmvc/PublishSettings.png "Публикация: параметры"



<!--HONumber=Feb17_HO3-->


