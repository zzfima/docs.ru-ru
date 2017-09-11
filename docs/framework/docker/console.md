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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fdce1e131eaa0d6952b2910f73105f097487711
ms.contentlocale: ru-ru
ms.lasthandoff: 08/11/2017

---

# <a name="running-console-applications-in-windows-containers"></a><span data-ttu-id="d7fc2-104">Запуск консольных приложений в контейнерах Windows</span><span class="sxs-lookup"><span data-stu-id="d7fc2-104">Running console applications in Windows containers</span></span>

<span data-ttu-id="d7fc2-105">Консольные приложения используются во многих целях: от простых запросов состояния до затратных по времени задач по обработке изображений документов.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-105">Console applications are used for many purposes; from simple querying of a status to long running document image processing tasks.</span></span> <span data-ttu-id="d7fc2-106">В любом случае возможность запуска и масштабирования этих приложений сопряжена с определенными ограничениями, связанными с необходимым оборудованием, временем запуска или запуском нескольких экземпляров.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-106">In any case, the ability to start up and scale these applications are met with limitations of hardware acquisitions, startup times or running multiple instances.</span></span>

<span data-ttu-id="d7fc2-107">Перевод консольных приложений в контейнеры Docker и Windows Server обеспечивает запуск приложений в чистом состоянии, что позволяет им выполнять заданные операции и чисто завершать работу.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-107">Moving your console applications to use Docker and Windows Server containers allows for starting these applications from a clean state, enabling them to perform the operation and then shutdown cleanly.</span></span> <span data-ttu-id="d7fc2-108">В этом разделе показаны действия, которые нужно выполнить для перемещения консольного приложения в контейнер Windows и его запуска с помощью скрипта PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-108">This topic will show the steps needed to move a console application to a Windows based container and start it using a PowerShell script.</span></span>

<span data-ttu-id="d7fc2-109">Используемый пример — это простое консольное приложение, которое принимает аргумент (в данном случае вопрос) и возвращает случайный ответ.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-109">The sample console application is a simple example which takes an argument, a question in this case, and returns a random answer.</span></span> <span data-ttu-id="d7fc2-110">Оно может принимать идентификатор клиента `customer_id` и обрабатывать его налоги или создавать эскиз для аргумента `image_url`.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-110">This could take a `customer_id` and process their taxes, or create a thumbnail for an `image_url` argument.</span></span>

<span data-ttu-id="d7fc2-111">Помимо самого ответа к нему было добавлено имя `Environment.MachineName`, чтобы продемонстрировать разницу между запуском приложения в локальной среде и в контейнере Windows.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-111">In addition to the answer, the `Environment.MachineName` has been added to the response to show the difference between running the application locally and in a Windows container.</span></span> <span data-ttu-id="d7fc2-112">При запуске приложения в локальной среде должно возвращаться имя вашего локального компьютера, а при запуске в контейнере Windows — идентификатор сеанса контейнера.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-112">When running the application locally, your local machine name should be returned and when running in a Windows Container; the container session id is returned.</span></span>

<span data-ttu-id="d7fc2-113">[Полный пример](https://github.com/dotnet/docs/tree/master/samples/framework/docker/ConsoleRandomAnswerGenerator) доступен в репозитории dotnet/docs в службе GitHub.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-113">The [complete example](https://github.com/dotnet/docs/tree/master/samples/framework/docker/ConsoleRandomAnswerGenerator) is available in the dotnet/docs repository on GitHub.</span></span> <span data-ttu-id="d7fc2-114">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="d7fc2-114">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="d7fc2-115">Перед началом перемещения приложения в контейнер необходимо знать некоторые термины Docker.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-115">You need to be familiar with some Docker terms before you begin working on moving your application to a container.</span></span>

> <span data-ttu-id="d7fc2-116">*Образ Docker* — это шаблон только для чтения, который определяет среду для запуска контейнера, включая операционную систему (ОС), системные компоненты и приложения.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-116">A *Docker image* is a read-only template that defines the environment for a running container, including the operating system (OS), system components, and application(s).</span></span>

<span data-ttu-id="d7fc2-117">Одной из важных особенностей образов Docker является то, что они формируются из базового образа.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-117">One important feature of Docker images is that images are composed from a base image.</span></span> <span data-ttu-id="d7fc2-118">Каждый новый образ включает небольшой набор компонентов в дополнение к существующему образу.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-118">Each new image adds a small set of features to an existing image.</span></span> 

> <span data-ttu-id="d7fc2-119">*Контейнер Docker* — это запущенный экземпляр образа.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-119">A *Docker container* is a running instance of an image.</span></span> 

<span data-ttu-id="d7fc2-120">Масштабирование приложения осуществляется путем запуска одного образа в нескольких контейнерах.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-120">You scale an application by running the same image in many containers.</span></span>
<span data-ttu-id="d7fc2-121">По существу, это похоже на запуск одного приложения на нескольких узлах.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-121">Conceptually, this is similar to running the same application in multiple hosts.</span></span>

<span data-ttu-id="d7fc2-122">Дополнительные сведения об архитектуре Docker можно найти в [Обзоре Docker](https://docs.docker.com/engine/understanding-docker/) на сайте Docker.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-122">You can learn more about the Docker architecture by reading the [Docker Overview](https://docs.docker.com/engine/understanding-docker/) on the Docker site.</span></span> 

<span data-ttu-id="d7fc2-123">Перемещение консольного приложения происходит буквально за пару действий.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-123">Moving your console application is a matter of a few steps.</span></span>

1. [<span data-ttu-id="d7fc2-124">Сборка приложения</span><span class="sxs-lookup"><span data-stu-id="d7fc2-124">Build the application</span></span>](#building-the-application)
1. [<span data-ttu-id="d7fc2-125">Создание Dockerfile для образа</span><span class="sxs-lookup"><span data-stu-id="d7fc2-125">Creating a Dockerfile for the image</span></span>](#creating-the-dockerfile)
1. [<span data-ttu-id="d7fc2-126">Сборка и запуск контейнера Docker</span><span class="sxs-lookup"><span data-stu-id="d7fc2-126">Process to build and run the Docker container</span></span>](#creating-the-image)

## <a name="prerequisites"></a><span data-ttu-id="d7fc2-127">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="d7fc2-127">Prerequisites</span></span>
<span data-ttu-id="d7fc2-128">Контейнеры Windows поддерживаются в [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) и [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span><span class="sxs-lookup"><span data-stu-id="d7fc2-128">Windows containers are supported on [Windows 10 Anniversary Update](https://www.microsoft.com/en-us/software-download/windows10/) or [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).</span></span>

> [!NOTE]
><span data-ttu-id="d7fc2-129">При использовании Windows Server 2016 контейнеры необходимо включить вручную, так как установщик Docker для Windows этот компонент не включает.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-129">If you are using Windows Server 2016, you must enable containers manually since the Docker for Windows installer will not enable the feature.</span></span> <span data-ttu-id="d7fc2-130">Убедитесь, что в операционной системе применены все обновления, и выполните инструкции из статьи [Развертывание узла контейнера](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment), чтобы установить контейнеры и компоненты Docker.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-130">Make sure all updates have run for the OS and then follow the instructions from the [Container Host Deployment](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment) article to install the containers and Docker features.</span></span>

<span data-ttu-id="d7fc2-131">Контейнеры Windows поддерживаются в Docker для Windows 1.12 Beta 26 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-131">You need to have Docker for Windows, version 1.12 Beta 26 or higher to support Windows containers.</span></span> <span data-ttu-id="d7fc2-132">По умолчанию Docker включает контейнеры Linux. Переключитесь на контейнеры Windows. Для этого щелкните правой кнопкой мыши значок Docker в панели задач и выберите **Переключиться на контейнеры Windows**.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-132">By default, Docker enables Linux based containers; switch to Windows containers by right clicking the Docker icon in the system tray and select **Switch to Windows containers**.</span></span> <span data-ttu-id="d7fc2-133">Docker запустит процесс изменения и, возможно, потребуется перезагрузить компьютер.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-133">Docker will run the process to change and a restart may be required.</span></span>

![Контейнеры Windows](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a><span data-ttu-id="d7fc2-135">Построение приложения</span><span class="sxs-lookup"><span data-stu-id="d7fc2-135">Building the application</span></span>
<span data-ttu-id="d7fc2-136">Обычно консольные приложения распространяются с помощью установщика, через FTP или в рамках развертывания через общую папку.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-136">Typically console applications are distributed through an installer, FTP, or File Share deployment.</span></span> <span data-ttu-id="d7fc2-137">При развертывании в контейнер необходимо скомпилировать ресурсы и поместить их в промежуточное расположение, которое можно будет использовать при создании образа Docker.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-137">When deploying to a container, the assets need to be compiled and staged to a location that can be used when the Docker image is created.</span></span>

<span data-ttu-id="d7fc2-138">В скрипте *build.ps1* приложение компилируется с помощью [MSBuild](https://msdn.microsoft.com/library/dd393574.aspx), чем завершается этап сборки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-138">In *build.ps1*, the script uses [MSBuild](https://msdn.microsoft.com/library/dd393574.aspx) to compile the application to complete the task of building the assets.</span></span> <span data-ttu-id="d7fc2-139">Для окончательного включения нужных ресурсов в MSBuild передаются некоторые параметры.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-139">There are a few parameters passed to MSBuild to finalize the needed assets.</span></span> <span data-ttu-id="d7fc2-140">Имя файла компилируемого проекта или решения, расположение выходных данных и, наконец, конфигурация (окончательная или отладочная).</span><span class="sxs-lookup"><span data-stu-id="d7fc2-140">The name of the project file or solution to be compiled, the location for the output and finally the configuration (Release or Debug).</span></span>

<span data-ttu-id="d7fc2-141">В вызове `Invoke-MSBuild` `OutputPath` имеет значение **publish**, а `Configuration` — значение **Release**.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-141">In the call to `Invoke-MSBuild` the `OutputPath` is set to **publish** and  `Configuration` set to **Release**.</span></span> 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj /p:OutputPath=.\publish /p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a><span data-ttu-id="d7fc2-142">Создание Dockerfile</span><span class="sxs-lookup"><span data-stu-id="d7fc2-142">Creating the Dockerfile</span></span>
<span data-ttu-id="d7fc2-143">Базовым образом, который используется для консольного приложения .NET Framework, является `microsoft/windowsservercore`, доступный в [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span><span class="sxs-lookup"><span data-stu-id="d7fc2-143">The base image used for a console .NET Framework application is `microsoft/windowsservercore`, publicly available on [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/).</span></span> <span data-ttu-id="d7fc2-144">Базовый образ содержит минимальную установку Windows Server 2016 .NET Framework 4.6.2 и выступает в роли основного образа операционной системы для контейнеров Windows.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-144">The base image contains a minimal installation of Windows Server 2016, .NET Framework 4.6.2 and serves as the base OS image for Windows Containers.</span></span>

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
<span data-ttu-id="d7fc2-145">В первой строке Dockerfile с помощью инструкции [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) определяется базовый образ.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-145">The first line in the Dockerfile designates the base image using the [`FROM`](https://docs.docker.com/engine/reference/builder/#/from) instruction.</span></span> <span data-ttu-id="d7fc2-146">Следующая инструкция файла, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add), копирует ресурсы приложения из папки **publish** в корневую папку контейнера, и, наконец, параметр [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) образа объявляет, что этот образ является командой или приложением, которое будет запускаться при запуске контейнера.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-146">Next, [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) in the file copies the application assets from the **publish** folder to root folder of the container and last; setting the [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) of the image states that this is the command or application that will run when the container starts.</span></span> 

## <a name="creating-the-image"></a><span data-ttu-id="d7fc2-147">Создание образа</span><span class="sxs-lookup"><span data-stu-id="d7fc2-147">Creating the image</span></span>
<span data-ttu-id="d7fc2-148">Чтобы создать образ Docker, в скрипт *build.ps1* добавляется следующий код.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-148">In order to create the Docker image, the following code is added to the *build.ps1* script.</span></span> <span data-ttu-id="d7fc2-149">При запуске скрипта создается образ `console-random-answer-generator` с использованием ресурсов, скомпилированных MSBuild (см. раздел [Построение приложения](#building-the-application)).</span><span class="sxs-lookup"><span data-stu-id="d7fc2-149">When the script is run, the `console-random-answer-generator` image is created using the assets compiled from MSBuild defined in the [Building the application](#building-the-application) section.</span></span>

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

<span data-ttu-id="d7fc2-150">Запустите скрипт, выполнив команду `.\build.ps1` в командной строке PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-150">Run the script using `.\build.ps1` from the PowerShell command prompt.</span></span>

<span data-ttu-id="d7fc2-151">По завершении построения выполните команду `docker images` в командной строке или в командной строке PowerShell. Вы увидите, что образ создан и готов к запуску.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-151">When the build is complete, using the `docker images` command from a command line or PowerShell prompt; you'll see that the image is created and ready to be run.</span></span>

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a><span data-ttu-id="d7fc2-152">Запуск контейнера</span><span class="sxs-lookup"><span data-stu-id="d7fc2-152">Running the container</span></span>
<span data-ttu-id="d7fc2-153">Контейнер можно запустить из командной строки с помощью команд Docker.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-153">You can start the container from the command line using the Docker commands.</span></span>

```
docker run console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="d7fc2-154">Выходные данные:</span><span class="sxs-lookup"><span data-stu-id="d7fc2-154">The output is</span></span>

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

<span data-ttu-id="d7fc2-155">При запуске команды `docker ps -a` в PowerShell видно, что контейнер по-прежнему существует.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-155">If you run the `docker ps -a` command from PowerShell, you can see that the container still exists.</span></span>

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

<span data-ttu-id="d7fc2-156">В столбце STATUS указывается, что приложение завершило работу "About a minute ago" (около минуты назад) и может быть закрыто.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-156">The STATUS column shows at "About a minute ago", the application was complete and could be shut down.</span></span> <span data-ttu-id="d7fc2-157">Если команда была выполнена сто раз, в наличии будет иметься сто статических контейнеров, не выполняющих никакую работу.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-157">If the command was run a hundred times, there would be a hundred containers left static with no work to do.</span></span> <span data-ttu-id="d7fc2-158">В обучающем сценарии оптимальным вариантом действий является выполнение работы и завершение работы или проведение очистки.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-158">In the beginning scenario the ideal operation was to do the work and shutdown or cleanup.</span></span> <span data-ttu-id="d7fc2-159">Для этого добавьте параметр `--rm` в команду `docker run`, чтобы удалить контейнер сразу же после получения сигнала `Exited`.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-159">To accomplish that workflow, adding the `--rm` option to the `docker run` command will remove the container as soon as the `Exited` signal is received.</span></span>

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

<span data-ttu-id="d7fc2-160">Выполните команду с этим параметром и посмотрите на выходные данные команды `docker ps -a`. Обратите внимание, что идентификатор контейнера (`Environment.MachineName`) в списке отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-160">Running the command with this option and then looking at the output of `docker ps -a` command; notice that the container id (the `Environment.MachineName`) is not in the list.</span></span>

### <a name="running-the-container-using-powershell"></a><span data-ttu-id="d7fc2-161">Запуск контейнера с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="d7fc2-161">Running the container using PowerShell</span></span>
<span data-ttu-id="d7fc2-162">В файлах примера проекта также есть скрипт *run.ps1*, который демонстрирует использование PowerShell для запуска приложения с указанием аргументов.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-162">In the sample project files there is also a *run.ps1* which is an example of how to use PowerShell to run the application accepting the arguments.</span></span>

<span data-ttu-id="d7fc2-163">Чтобы запустить его, откройте PowerShell и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d7fc2-163">To run, open PowerShell and use the following command:</span></span>

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a><span data-ttu-id="d7fc2-164">Сводка</span><span class="sxs-lookup"><span data-stu-id="d7fc2-164">Summary</span></span>
<span data-ttu-id="d7fc2-165">С помощью простого добавления Dockerfile и публикации консольное приложение .NET Framework можно поместить в контейнер и запускать несколько экземпляров, выполнять чистые запуск и завершение работы и использовать многие другие возможности Windows Server 2016 без какого-либо изменения кода приложения.</span><span class="sxs-lookup"><span data-stu-id="d7fc2-165">Just by adding a Dockerfile and publishing the application, you can containerize your .NET Framework console applications and now take the advantage of running multiple instances, clean start and stop and more Windows Server 2016 capabilities without making any changes to the application code at all.</span></span>

