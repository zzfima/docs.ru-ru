---
title: "Запуск консольных приложений в Docker"
description: "Узнайте, как запускать существующее консольное приложение .NET Framework в контейнере Windows Docker/"
author: spboyer
keywords: ".NET, контейнер, консольный, приложения"
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.openlocfilehash: 2fdce1e131eaa0d6952b2910f73105f097487711
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="running-console-applications-in-windows-containers"></a>Запуск консольных приложений в контейнерах Windows

Консольные приложения используются во многих целях: от простых запросов состояния до затратных по времени задач по обработке изображений документов. В любом случае возможность запуска и масштабирования этих приложений сопряжена с определенными ограничениями, связанными с необходимым оборудованием, временем запуска или запуском нескольких экземпляров.

Перевод консольных приложений в контейнеры Docker и Windows Server обеспечивает запуск приложений в чистом состоянии, что позволяет им выполнять заданные операции и чисто завершать работу. В этом разделе показаны действия, которые нужно выполнить для перемещения консольного приложения в контейнер Windows и его запуска с помощью скрипта PowerShell.

Используемый пример — это простое консольное приложение, которое принимает аргумент (в данном случае вопрос) и возвращает случайный ответ. Оно может принимать идентификатор клиента `customer_id` и обрабатывать его налоги или создавать эскиз для аргумента `image_url`.

Помимо самого ответа к нему было добавлено имя `Environment.MachineName`, чтобы продемонстрировать разницу между запуском приложения в локальной среде и в контейнере Windows. При запуске приложения в локальной среде должно возвращаться имя вашего локального компьютера, а при запуске в контейнере Windows — идентификатор сеанса контейнера.

[Полный пример](https://github.com/dotnet/docs/tree/master/samples/framework/docker/ConsoleRandomAnswerGenerator) доступен в репозитории dotnet/docs в службе GitHub. Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Перед началом перемещения приложения в контейнер необходимо знать некоторые термины Docker.

> *Образ Docker* — это шаблон только для чтения, который определяет среду для запуска контейнера, включая операционную систему (ОС), системные компоненты и приложения.

Одной из важных особенностей образов Docker является то, что они формируются из базового образа. Каждый новый образ включает небольшой набор компонентов в дополнение к существующему образу. 

> *Контейнер Docker* — это запущенный экземпляр образа. 

Масштабирование приложения осуществляется путем запуска одного образа в нескольких контейнерах.
По существу, это похоже на запуск одного приложения на нескольких узлах.

Дополнительные сведения об архитектуре Docker можно найти в [Обзоре Docker](https://docs.docker.com/engine/understanding-docker/) на сайте Docker. 

Перемещение консольного приложения происходит буквально за пару действий.

1. [Сборка приложения](#building-the-application)
1. [Создание Dockerfile для образа](#creating-the-dockerfile)
1. [Сборка и запуск контейнера Docker](#creating-the-image)

## <a name="prerequisites"></a>Предварительные требования
Контейнеры Windows поддерживаются в [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) и [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).

> [!NOTE]
>При использовании Windows Server 2016 контейнеры необходимо включить вручную, так как установщик Docker для Windows этот компонент не включает. Убедитесь, что в операционной системе применены все обновления, и выполните инструкции из статьи [Развертывание узла контейнера](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment), чтобы установить контейнеры и компоненты Docker.

Контейнеры Windows поддерживаются в Docker для Windows 1.12 Beta 26 или более поздней версии. По умолчанию Docker включает контейнеры Linux. Переключитесь на контейнеры Windows. Для этого щелкните правой кнопкой мыши значок Docker в панели задач и выберите **Переключиться на контейнеры Windows**. Docker запустит процесс изменения и, возможно, потребуется перезагрузить компьютер.

![Контейнеры Windows](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a>Построение приложения
Обычно консольные приложения распространяются с помощью установщика, через FTP или в рамках развертывания через общую папку. При развертывании в контейнер необходимо скомпилировать ресурсы и поместить их в промежуточное расположение, которое можно будет использовать при создании образа Docker.

В скрипте *build.ps1* приложение компилируется с помощью [MSBuild](https://msdn.microsoft.com/library/dd393574.aspx), чем завершается этап сборки ресурсов. Для окончательного включения нужных ресурсов в MSBuild передаются некоторые параметры. Имя файла компилируемого проекта или решения, расположение выходных данных и, наконец, конфигурация (окончательная или отладочная).

В вызове `Invoke-MSBuild` `OutputPath` имеет значение **publish**, а `Configuration` — значение **Release**. 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj /p:OutputPath=.\publish /p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a>Создание Dockerfile
Базовым образом, который используется для консольного приложения .NET Framework, является `microsoft/windowsservercore`, доступный в [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/). Базовый образ содержит минимальную установку Windows Server 2016 .NET Framework 4.6.2 и выступает в роли основного образа операционной системы для контейнеров Windows.

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
В первой строке Dockerfile с помощью инструкции [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) определяется базовый образ. Следующая инструкция файла, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add), копирует ресурсы приложения из папки **publish** в корневую папку контейнера, и, наконец, параметр [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) образа объявляет, что этот образ является командой или приложением, которое будет запускаться при запуске контейнера. 

## <a name="creating-the-image"></a>Создание образа
Чтобы создать образ Docker, в скрипт *build.ps1* добавляется следующий код. При запуске скрипта создается образ `console-random-answer-generator` с использованием ресурсов, скомпилированных MSBuild (см. раздел [Построение приложения](#building-the-application)).

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

Запустите скрипт, выполнив команду `.\build.ps1` в командной строке PowerShell.

По завершении построения выполните команду `docker images` в командной строке или в командной строке PowerShell. Вы увидите, что образ создан и готов к запуску.

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a>Запуск контейнера
Контейнер можно запустить из командной строки с помощью команд Docker.

```
docker run console-random-answer-generator "Are you a square container?"
```

Выходные данные:

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

При запуске команды `docker ps -a` в PowerShell видно, что контейнер по-прежнему существует.

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

В столбце STATUS указывается, что приложение завершило работу "About a minute ago" (около минуты назад) и может быть закрыто. Если команда была выполнена сто раз, в наличии будет иметься сто статических контейнеров, не выполняющих никакую работу. В обучающем сценарии оптимальным вариантом действий является выполнение работы и завершение работы или проведение очистки. Для этого добавьте параметр `--rm` в команду `docker run`, чтобы удалить контейнер сразу же после получения сигнала `Exited`.

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

Выполните команду с этим параметром и посмотрите на выходные данные команды `docker ps -a`. Обратите внимание, что идентификатор контейнера (`Environment.MachineName`) в списке отсутствует.

### <a name="running-the-container-using-powershell"></a>Запуск контейнера с помощью PowerShell
В файлах примера проекта также есть скрипт *run.ps1*, который демонстрирует использование PowerShell для запуска приложения с указанием аргументов.

Чтобы запустить его, откройте PowerShell и выполните следующую команду:

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a>Сводка
С помощью простого добавления Dockerfile и публикации консольное приложение .NET Framework можно поместить в контейнер и запускать несколько экземпляров, выполнять чистые запуск и завершение работы и использовать многие другие возможности Windows Server 2016 без какого-либо изменения кода приложения.
