---
title: "Перенос приложений ASP.NET MVC в контейнеры Windows"
description: "Узнайте, как запустить существующее приложение ASP.NET MVC в контейнере Windows Docker"
keywords: "Контейнеры Windows, Docker, ASP.NET MVC"
author: BillWagner
manager: wpickett
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net-framework-4.6
ms.technology: dotnet-mvc
ms.devlang: dotnet
ms.assetid: c9f1d52c-b4bd-4b5d-b7f9-8f9ceaf778c4
translationtype: Human Translation
ms.sourcegitcommit: 15c55a87beb64f265a164db918c7721c7690fadf
ms.openlocfilehash: 3e8a8a953cbb3dde6ddf386f8c3b3a1fd4c549f1

---

# <a name="migrating-aspnet-mvc-applications-to-windows-containers"></a>Перенос приложений ASP.NET MVC в контейнеры Windows

Для запуска существующего приложения .NET Framework в контейнере Windows нужно создать образ Docker, который содержит приложение, и запустить один или несколько контейнеров, где будет выполняться этот образ. В этом разделе объясняются задачи, которые нужно выполнить для развертывания существующего [приложения ASP.NET MVC](http://www.asp.net/mvc) в контейнере Windows.

Сначала вы возьмете существующее приложение ASP.NET MVC. Затем соберете опубликованные ресурсы с помощью Visual Studio. С помощью Docker нужно будет создать образ, содержащий приложение и запускающий его после собственного запуска. По завершении в браузере можно будет подключиться к сайту, на котором запущен контейнер Windows, и убедиться в том, что приложение запущено.

Для понимания этой статьи требуется базовое знакомство с Docker. Дополнительные сведения об архитектуре Docker можно найти в [Обзоре Docker](https://docs.docker.com/engine/understanding-docker/) на сайте Docker.

Приложение, которое будет работать в контейнере, является простым веб-сайтом, который случайным образом отвечает на вопросы. Это базовое приложение MVC без проверки подлинности и хранилища базы данных. Оно позволяет сосредоточиться на перемещении веб-уровня в контейнер. В дальнейших темах показано, как перемещать постоянное хранилище и управлять им в контейнерных приложениях.

Перемещение приложения состоит из следующих действий.

1. [Создание задачи публикации для сборки ресурсов образа](#publish-script).
2. [Создание образа Docker, в котором будет запускаться приложение](#build-the-image).
3. [Запуск контейнера Docker, в котором будет запускаться образ](#start-a-container).
4. [Проверка приложения с помощью браузера](#verify-in-the-browser).

Готовое приложение находится в репозитории [dotnet/core-docs в службе GitHub](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator).

## <a name="prerequisites"></a>Предварительные требования

Компьютер, используемый для разработки, должен работать под управлением, как минимум, [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) или [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server). 

Прежде чем начать, необходимо установить [Docker для Windows](https://docs.docker.com/docker-for-windows/) 1.12 Beta 26 или более поздней версии. В настоящее время поддержка контейнеров Windows доступна только в виде бета-версии.

> [!IMPORTANT]
> При использовании Windows Server 2016 перед запуском контейнеров Docker необходимо выполнить инструкции по [развертыванию узла контейнеров в Windows Server](https://msdn.microsoft.com/en-us/virtualization/windowscontainers/deployment/deployment).

После установки и запуска Docker нужно щелкнуть правой кнопкой мыши значок на панели задач и выбрать **Переключиться на контейнеры Windows** для запуска образов Docker на базе Windows. На выполнение этой команды требуется несколько секунд:

![Контейнер Windows][windows-container]

## <a name="publish-script"></a>Публикация скрипта

Первым делом нужно собрать все ресурсы, которые требуется загрузить в образ Docker, в одном месте. К счастью, для создания профиля публикации приложения в Visual Studio есть команда **Publish** (Публикация). В этом профиле все ресурсы будут собраны в одном дереве каталогов, которое далее в этом учебнике нужно будет скопировать в свой целевой образ.

**Этапы публикации**

1. Щелкните правой кнопкой мыши веб-проект в Visual Studio и выберите **Publish** (Публикация).
2. Нажмите кнопку **Custom profile (Настраиваемый профиль), а затем выберите **File System (Файловая система)** в качестве метода.
3. Выберите каталог. По правилам загруженный образец использует `bin/PublishOutput`.

![Публикация: подключение][publish-connection]

Затем откройте раздел **File Publish Options** (Параметры публикации файла) на вкладке **Settings** (Параметры). Выберите **Precompile during publishing** (Предварительная компиляция во время публикации). Эта оптимизация означает, что представления не будут компилироваться в контейнере Docker, вместо этого будут копироваться предварительно скомпилированные представления.

![Публикация: параметры][publish-settings]

Нажмите кнопку **Publish** (Публикация), и Visual Studio скопирует все необходимые ресурсы в целевую папку. 

## <a name="build-the-image"></a>Сборка образа

Образ Docker определяется в файле Dockerfile, который содержит инструкции для базового образа, все дополнительные компоненты, приложение, которое должно запускаться, и другой образ настройки.  Dockerfile содержит входные параметры для команды `docker build`, которая создает образ.

Вы создадите образ на основе образа `microsft/aspnet`, расположенного на [Docker Hub](https://hub.docker.com/r/microsoft/aspnet/).
Базовый образ `microsoft/aspnet` — это образ Windows Server. В дополнение к Windows Server Core в нем установлены и включены служба IIS и ASP.NET 4.6.2. При запуске этого образа в контейнере он автоматически запускает IIS, и все установленные веб-сайты становятся активными.

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

Далее нужно выполнить в Docker команду build для создания образа, в котором будет запускаться приложение ASP.NET. Для этого откройте окно PowerShell и введите следующую команду в каталоге решения:

```
docker build -t mvcrandomanswers .
```

Эта команда создаст новый образ в соответствии с инструкциями в Dockerfile. Это может включать получение базового образа из [Docker Hub](http://hub.docker.com). После этого в образ будет добавлено приложение.

После выполнения этой команды можно выполнить команду `docker images` для просмотра сведений о новом образе:

```
REPOSITORY                    TAG                 IMAGE ID            CREATED             SIZE
mvcrandomanswers              latest              86838648aab6        2 minutes ago       8.104 GB
```

Идентификатор IMAGE ID на вашем компьютере будет другим. Теперь давайте запустим приложение.

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
> В текущем выпуске использовать `http://localhost` для перехода на свой сайт нельзя. Это связано с известным поведением в WinNAT. В будущем проблема будет устранена. А пока этого не произошло, необходимо использовать IP-адрес контейнера.

После запуска контейнера необходимо найти его IP-адрес, чтобы вы могли подключиться к своему запущенному контейнеру из браузера:

```
docker inspect -f "{{ .NetworkSettings.Networks.nat.IPAddress }}" randomanswers
172.31.194.61
```

Подключиться к запущенному контейнеру можно, указав IPv4-адрес и настроенный порт (8000), `http://172.31.194.61:8000` (см. пример). Введите этот URL-адрес в адресной строке браузера, и вы увидите работающий сайт.

> [!NOTE]
> Некоторые программы VPN или прокси-серверы могут препятствовать переходу на ваш узел.
> Их можно временно отключить, чтобы убедиться, что контейнер работает.

Каталог образцов на GitHub содержит [Сценарий PowerShell](https://github.com/dotnet/docs/tree/master/samples/framework/docker/MVCRandomAnswerGenerator/run.ps1), который выполняет эти команды за вас. Откройте окно PowerShell, перейдите в каталог решения и введите команду:

```
./run.ps1
```

Она создает образ, отображает список образов на компьютере, запускает контейнер и отображает IP-адрес для этого контейнера. 

Когда вы закончите и захотите остановить контейнер, выполните команду `docker
stop`:

```
docker stop randomanswers
```

Чтобы удалить контейнер, выполните команду `docker rm`:

```
docker rm randomanswers
```

## <a name="summary"></a>Сводка

В этом разделе вы научились переводить существующее приложение ASP.NET MVC в контейнер Windows Server и запускать его. Для запуска существующего приложения в него не требуется вносить какие-либо изменения. Для публикации приложения нужно запустить задачи, создать образ Docker и запустить этот образ в новом контейнере. Использование контейнеров Windows Server — это простейший способ переноса существующих приложений в эту среду.

[windows-container]: media/aspnetmvc/SwitchContainer.png "Переход на контейнер Windows"
[publish-connection]: media/aspnetmvc/PublishConnection.png "Публикация в файловой системе"
[publish-settings]: media/aspnetmvc/PublishSettings.png "Параметры публикации"



<!--HONumber=Nov16_HO3-->


