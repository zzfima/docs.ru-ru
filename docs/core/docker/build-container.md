---
title: Руководство "Контейнеризация приложений с помощью Docker"
description: Из этого руководства вы узнаете, как контейнеризировать приложение .NET Core с помощью Docker.
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: b344731c7d356f3705d9909b6901234f91ec7d6d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "72521886"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="372ba-103">Учебник. Контейнеризация приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="372ba-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="372ba-104">В этом руководстве показано, как создать образ Docker, содержащий приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="372ba-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="372ba-105">Этот образ можно использовать для создания контейнеров в вашей локальной среде разработки, частном или общедоступном облаке.</span><span class="sxs-lookup"><span data-stu-id="372ba-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="372ba-106">Вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="372ba-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="372ba-107">создать и опубликовать простое приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="372ba-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="372ba-108">создать и настроить Dockerfile для .NET Core;</span><span class="sxs-lookup"><span data-stu-id="372ba-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="372ba-109">Создание образа Docker</span><span class="sxs-lookup"><span data-stu-id="372ba-109">Build a Docker image</span></span>
> - <span data-ttu-id="372ba-110">создать и запустить контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="372ba-110">Create and run a Docker container</span></span>

<span data-ttu-id="372ba-111">Вы также узнаете о задачах сборки и развертывания контейнера Docker для приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="372ba-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="372ba-112">*Платформа Docker* использует *модуль Docker* для быстрой сборки и упаковки приложений в качестве *образов Docker*.</span><span class="sxs-lookup"><span data-stu-id="372ba-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="372ba-113">Эти образы имеют формат *Dockerfile* и предназначены для развертывания и запуска в многоуровневом контейнере.</span><span class="sxs-lookup"><span data-stu-id="372ba-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="372ba-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="372ba-114">Prerequisites</span></span>

<span data-ttu-id="372ba-115">Установите следующие необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="372ba-115">Install the following prerequisites:</span></span>

- <span data-ttu-id="372ba-116">[Пакет .NET для Core версии 2.2](https://dotnet.microsoft.com/download)\.</span><span class="sxs-lookup"><span data-stu-id="372ba-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\</span></span>
<span data-ttu-id="372ba-117">Если у вас установлена платформа .NET Core, воспользуйтесь командой `dotnet --info`, чтобы определить версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="372ba-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- <span data-ttu-id="372ba-118">[Docker Community Edition](https://www.docker.com/products/docker-desktop).</span><span class="sxs-lookup"><span data-stu-id="372ba-118">[Docker Community Edition](https://www.docker.com/products/docker-desktop)</span></span>

- <span data-ttu-id="372ba-119">Временная рабочая папка для *Dockerfile* и примера приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="372ba-119">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="372ba-120">В этом руководстве имя `docker-working` используется в качестве рабочей папки.</span><span class="sxs-lookup"><span data-stu-id="372ba-120">In this tutorial, the name `docker-working` is used as the working folder.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="372ba-121">Использование пакета SDK версии 2.2</span><span class="sxs-lookup"><span data-stu-id="372ba-121">Use SDK version 2.2</span></span>

<span data-ttu-id="372ba-122">Если вы работаете с пакетом SDK более новой версии (например, 3.0), убедитесь, что приложение использует версию 2.2.</span><span class="sxs-lookup"><span data-stu-id="372ba-122">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="372ba-123">Создайте файл с именем *global.json* в рабочей папке и вставьте в него следующий код JSON:</span><span class="sxs-lookup"><span data-stu-id="372ba-123">Create a file named *global.json* in your working folder and paste in the following JSON code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="372ba-124">Сохраните этот файл.</span><span class="sxs-lookup"><span data-stu-id="372ba-124">Save this file.</span></span> <span data-ttu-id="372ba-125">При наличии такого файла .NET Core будет использовать версию 2.2 для всех команд `dotnet`, вызванных из этого каталога и его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="372ba-125">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this folder and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="372ba-126">Создание приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="372ba-126">Create .NET Core app</span></span>

<span data-ttu-id="372ba-127">Вам нужно создать приложение .NET Core для выполнения контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="372ba-127">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="372ba-128">Откройте терминал, создайте рабочую папку, если вы еще этого не сделали, и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="372ba-128">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="372ba-129">Выполните следующую команду в рабочей папке, чтобы создать проект во вложенной папке с именем *app*:</span><span class="sxs-lookup"><span data-stu-id="372ba-129">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="372ba-130">Дерево папок будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="372ba-130">Your folder tree will look like the following:</span></span>

```
docker-working
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="372ba-131">Команда `dotnet new` создает папку с именем *app* и приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="372ba-131">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="372ba-132">Войдите в папку *app* и выполните команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="372ba-132">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="372ba-133">Вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="372ba-133">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="372ba-134">Шаблон по умолчанию создает приложение, которое выводит текст в терминал и затем завершает работу.</span><span class="sxs-lookup"><span data-stu-id="372ba-134">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="372ba-135">В этом руководстве описано, как использовать приложение с бесконечным циклом выполнения.</span><span class="sxs-lookup"><span data-stu-id="372ba-135">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="372ba-136">Откройте файл *Program.cs* в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="372ba-136">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="372ba-137">Файл должен содержать следующий код:</span><span class="sxs-lookup"><span data-stu-id="372ba-137">It should currently look like the following code:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="372ba-138">Замените его кодом, который считает числа каждую секунду:</span><span class="sxs-lookup"><span data-stu-id="372ba-138">Replace the file with the following code that counts numbers every second:</span></span>

```csharp
using System;

namespace myapp
{
    class Program
    {
        static void Main(string[] args)
        {
            var counter = 0;
            var max = args.Length != 0 ? Convert.ToInt32(args[0]) : -1;
            while (max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="372ba-139">Сохраните файл и протестируйте программу еще раз с помощью команды `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="372ba-139">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="372ba-140">Помните, что это приложение выполняется бесконечно.</span><span class="sxs-lookup"><span data-stu-id="372ba-140">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="372ba-141">Остановите его с помощью команды отмены, нажав клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="372ba-141">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="372ba-142">Вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="372ba-142">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="372ba-143">Если приложению передать число в командной строке, оно досчитает до такого числа и завершит работу.</span><span class="sxs-lookup"><span data-stu-id="372ba-143">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="372ba-144">Введите команду `dotnet run -- 5`, чтобы приложение досчитало до пяти.</span><span class="sxs-lookup"><span data-stu-id="372ba-144">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="372ba-145">Все параметры после `--` не передаются команде `dotnet run`, а передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="372ba-145">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="372ba-146">Публикация приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="372ba-146">Publish .NET Core app</span></span>

<span data-ttu-id="372ba-147">Прежде чем добавить приложение .NET Core в образ Docker, опубликуйте его.</span><span class="sxs-lookup"><span data-stu-id="372ba-147">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="372ba-148">Убедитесь, что выполняемый контейнер запускает опубликованную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="372ba-148">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="372ba-149">Из рабочей папки перейдите в папку *app* с примером исходного кода и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="372ba-149">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="372ba-150">Эта команда компилирует приложение и помещает результат в папку *publish*.</span><span class="sxs-lookup"><span data-stu-id="372ba-150">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="372ba-151">Путь к папке *publish* из рабочей папки должен быть таким: `.\app\bin\Release\netcoreapp2.2\publish\`</span><span class="sxs-lookup"><span data-stu-id="372ba-151">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="372ba-152">Получите список файлов для папки publish, чтобы убедиться в наличии файла *myapp.dll*.</span><span class="sxs-lookup"><span data-stu-id="372ba-152">Get a directory listing of the publish folder to verify that the *myapp.dll* was created.</span></span> <span data-ttu-id="372ba-153">Из папки *app* выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="372ba-153">From the *app* folder, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\docker-working\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="372ba-154">Создание файла Dockerfile</span><span class="sxs-lookup"><span data-stu-id="372ba-154">Create the Dockerfile</span></span>

<span data-ttu-id="372ba-155">Файл *Dockerfile* используется командой `docker build` для создания образа контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="372ba-156">Это текстовый файл с именем *Dockerfile* и без расширения.</span><span class="sxs-lookup"><span data-stu-id="372ba-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span>

<span data-ttu-id="372ba-157">В окне терминала перейдите к каталогу на один уровень выше рабочей папки, созданной ранее.</span><span class="sxs-lookup"><span data-stu-id="372ba-157">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="372ba-158">Создайте файл с именем *Dockerfile* в рабочей папке и откройте его в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="372ba-158">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="372ba-159">Добавьте следующую команду в первую строку файла:</span><span class="sxs-lookup"><span data-stu-id="372ba-159">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="372ba-160">Команда `FROM` указывает Docker вызвать образ с тегом **2.2** из репозитория **mcr.microsoft.com/dotnet/core/runtime**.</span><span class="sxs-lookup"><span data-stu-id="372ba-160">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="372ba-161">Убедитесь, что вы вызываете среду выполнения .NET Core, версия которой соответствует версии среды выполнения, с которой работает пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="372ba-161">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="372ba-162">Например, приложение, созданное в предыдущем разделе, использует пакет SDK для .NET Core версии 2.2. Также было создано приложение для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="372ba-162">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="372ba-163">Поэтому базовый образ, который указан в файле *Dockerfile*, должен иметь тег **2.2**.</span><span class="sxs-lookup"><span data-stu-id="372ba-163">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="372ba-164">Сохраните файл *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="372ba-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="372ba-165">Структура каталогов рабочей папки должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="372ba-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="372ba-166">Некоторые файлы и папки на более глубоком уровне были вырезаны для экономии места в статье:</span><span class="sxs-lookup"><span data-stu-id="372ba-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│   global.json
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp2.2
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="372ba-167">В терминале выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="372ba-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="372ba-168">Docker обработает все строки файла *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="372ba-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="372ba-169">Символ `.` в команде `docker build` используется, чтобы выполнить с помощью Docker поиск файла *Dockerfile* в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="372ba-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="372ba-170">Эта команда создает образ и локальный репозиторий с именем **myimage**, который указывает на такой образ.</span><span class="sxs-lookup"><span data-stu-id="372ba-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="372ba-171">После завершения работы этой команды выполните команду `docker images`, чтобы просмотреть список установленных образов:</span><span class="sxs-lookup"><span data-stu-id="372ba-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="372ba-172">Обратите внимание, что два образа имеют одинаковое значение **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="372ba-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="372ba-173">Это связано с тем, что единственная команда в файле *Dockerfile* создает новый образ на основе существующего.</span><span class="sxs-lookup"><span data-stu-id="372ba-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="372ba-174">Добавим в файл *Dockerfile* еще две команды.</span><span class="sxs-lookup"><span data-stu-id="372ba-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="372ba-175">Каждая команда создает новый уровень образа, а последняя команда представляет образ, на который будет указывать репозиторий **myimage**.</span><span class="sxs-lookup"><span data-stu-id="372ba-175">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="372ba-176">Команда `COPY` предписывает Docker скопировать указанную папку на вашем компьютере в папку в контейнере.</span><span class="sxs-lookup"><span data-stu-id="372ba-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="372ba-177">В этом примере папка *publish* копируется в папку с именем *app* в контейнере.</span><span class="sxs-lookup"><span data-stu-id="372ba-177">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="372ba-178">Следующая команда `ENTRYPOINT` используется, чтобы настроить с помощью Docker контейнер для запуска в качестве исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="372ba-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="372ba-179">При запуске контейнера выполняется команда `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="372ba-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="372ba-180">После выполнения команды контейнер автоматически остановится.</span><span class="sxs-lookup"><span data-stu-id="372ba-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="372ba-181">В окне терминала выполните команду `docker build -t myimage -f Dockerfile .`, а после ее выполнения — команду `docker images`.</span><span class="sxs-lookup"><span data-stu-id="372ba-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  819.7kB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/runtime:2.2
 ---> d51bb4452469
Step 2/3 : COPY app/bin/Release/netcoreapp2.2/publish/ app/
 ---> a1e98ac62017
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in f34da5c18e7c
Removing intermediate container f34da5c18e7c
 ---> ddcc6646461b
Successfully built ddcc6646461b
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              ddcc6646461b        10 seconds ago      314MB
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="372ba-182">Каждая команда в файле *Dockerfile* создает уровень и экземпляр **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="372ba-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="372ba-183">Последний экземпляр **IMAGE ID** (ваш идентификатор будет отличаться) имеет значение **ddcc6646461b**. Теперь вы создадите контейнер на основе этого образа.</span><span class="sxs-lookup"><span data-stu-id="372ba-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="372ba-184">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="372ba-184">Create a container</span></span>

<span data-ttu-id="372ba-185">Теперь, когда у вас есть образ, содержащий приложение, вы можете создать контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="372ba-186">Контейнер можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="372ba-186">You can create a container in two ways.</span></span> <span data-ttu-id="372ba-187">Сначала создайте остановленный контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="372ba-188">Команда `docker create` выше создает контейнер на основе образа **myimage**.</span><span class="sxs-lookup"><span data-stu-id="372ba-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="372ba-189">В выходных данных этой команды присутствует **CONTAINER ID** (ваш идентификатор будет отличаться) созданного контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="372ba-190">Чтобы просмотреть список *всех* контейнеров, воспользуйтесь командой `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="372ba-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="372ba-191">Управление контейнером</span><span class="sxs-lookup"><span data-stu-id="372ba-191">Manage the container</span></span>

<span data-ttu-id="372ba-192">Каждому контейнеру присваивается случайное имя, с помощью которого можно обращаться к этому экземпляру контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="372ba-193">Например, созданный автоматически контейнер получил имя **boring_matsumoto** (имя вашего контейнера будет отличаться), которое можно использовать для запуска контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-193">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="372ba-194">Чтобы переопределить автоматически созданное имя и указать другое, используйте параметр `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="372ba-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="372ba-195">В следующем примере используется команда `docker start` для запуска контейнера, а затем — команда `docker ps` для отображения только запущенных контейнеров:</span><span class="sxs-lookup"><span data-stu-id="372ba-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="372ba-196">Аналогично, команда `docker stop` останавливает контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="372ba-197">В следующем примере используется команда `docker stop` для остановки контейнера, а затем — команда `docker ps` для подтверждения того, что контейнеры не запущены:</span><span class="sxs-lookup"><span data-stu-id="372ba-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="372ba-198">Подключение к контейнеру</span><span class="sxs-lookup"><span data-stu-id="372ba-198">Connect to a container</span></span>

<span data-ttu-id="372ba-199">После запуска контейнера вы можете подключиться к нему, чтобы просмотреть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="372ba-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="372ba-200">С помощью команд `docker start` и `docker attach` запустите контейнер и просмотрите поток вывода.</span><span class="sxs-lookup"><span data-stu-id="372ba-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="372ba-201">В этом примере команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, используется для отключения от запущенного контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-201">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="372ba-202">Это может привести к завершению процесса в контейнере и его последующей остановке.</span><span class="sxs-lookup"><span data-stu-id="372ba-202">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="372ba-203">Параметр `--sig-proxy=false` гарантирует, что команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, не остановит процесс в контейнере.</span><span class="sxs-lookup"><span data-stu-id="372ba-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="372ba-204">После отключения от контейнера снова подключитесь к нему, чтобы убедиться в том, что он продолжает работать и считать числа.</span><span class="sxs-lookup"><span data-stu-id="372ba-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker attach --sig-proxy=false boring_matsumoto
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false boring_matsumoto
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="372ba-205">Удаление контейнера</span><span class="sxs-lookup"><span data-stu-id="372ba-205">Delete a container</span></span>

<span data-ttu-id="372ba-206">В рамках этого руководства предполагается, что вам не нужны контейнеры, которые запущены, но не выполняют полезные действия.</span><span class="sxs-lookup"><span data-stu-id="372ba-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="372ba-207">Удалите созданный ранее контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-207">Delete the container you previously created.</span></span> <span data-ttu-id="372ba-208">Если контейнер запущен, остановите его.</span><span class="sxs-lookup"><span data-stu-id="372ba-208">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="372ba-209">В примере ниже выводится список всех контейнеров,</span><span class="sxs-lookup"><span data-stu-id="372ba-209">The following example lists all containers.</span></span> <span data-ttu-id="372ba-210">а затем используется команда `docker rm` для удаления контейнера. После этого выполняется повторная проверка наличия запущенных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="372ba-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="372ba-211">Однократный запуск</span><span class="sxs-lookup"><span data-stu-id="372ba-211">Single run</span></span>

<span data-ttu-id="372ba-212">Docker предоставляет единую команду `docker run` для создания и запуска контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="372ba-213">Она исключает необходимость в поочередном выполнении команд `docker create` и `docker start`.</span><span class="sxs-lookup"><span data-stu-id="372ba-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="372ba-214">Вы также можете настроить ее для автоматического удаления контейнера при его остановке.</span><span class="sxs-lookup"><span data-stu-id="372ba-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="372ba-215">Например, команда `docker run -it --rm` выполняет две операции. Сначала она автоматически подключается к контейнеру с помощью текущего терминала, а потом, после завершения работы контейнера, удаляет его:</span><span class="sxs-lookup"><span data-stu-id="372ba-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="372ba-216">Во время выполнения `docker run -it` команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, остановит процесс, запущенный в контейнере. А это в свою очередь приведет к остановке контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="372ba-217">Так как в команде указан параметр `--rm`, контейнер автоматически удалится после остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="372ba-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="372ba-218">Убедитесь, что он больше не существует:</span><span class="sxs-lookup"><span data-stu-id="372ba-218">Verify that it does not exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="372ba-219">Изменение команды ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="372ba-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="372ba-220">Команда `docker run` также позволяет изменить команду `ENTRYPOINT` из файла *Dockerfile* для запуска другой программы, но только для соответствующего контейнера.</span><span class="sxs-lookup"><span data-stu-id="372ba-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="372ba-221">Например, воспользуйтесь указанной ниже командой, чтобы запустить `bash` или `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="372ba-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="372ba-222">При необходимости измените команду.</span><span class="sxs-lookup"><span data-stu-id="372ba-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="372ba-223">Windows</span><span class="sxs-lookup"><span data-stu-id="372ba-223">Windows</span></span>

<span data-ttu-id="372ba-224">В этом примере команда `ENTRYPOINT` изменена на `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="372ba-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="372ba-225">Нажав клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>, вы можете завершить процесс и остановить контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-225"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

```console
> docker run -it --rm --entrypoint "cmd.exe" myimage

Microsoft Windows [Version 10.0.17763.379]
(c) 2018 Microsoft Corporation. All rights reserved.

C:\>dir
 Volume in drive C has no label.
 Volume Serial Number is 3005-1E84

 Directory of C:\

04/09/2019  08:46 AM    <DIR>          app
03/07/2019  10:25 AM             5,510 License.txt
04/02/2019  01:35 PM    <DIR>          Program Files
04/09/2019  01:06 PM    <DIR>          Users
04/02/2019  01:35 PM    <DIR>          Windows
               1 File(s)          5,510 bytes
               4 Dir(s)  21,246,517,248 bytes free

C:\>^C
```

#### <a name="linux"></a><span data-ttu-id="372ba-226">Linux</span><span class="sxs-lookup"><span data-stu-id="372ba-226">Linux</span></span>

<span data-ttu-id="372ba-227">В этом примере команда `ENTRYPOINT` изменена на `bash`.</span><span class="sxs-lookup"><span data-stu-id="372ba-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="372ba-228">Команда `quit` позволяет завершить процесс и остановить контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="372ba-229">Основные команды</span><span class="sxs-lookup"><span data-stu-id="372ba-229">Essential commands</span></span>

<span data-ttu-id="372ba-230">Docker предоставляет множество команд для операций с контейнером и образами.</span><span class="sxs-lookup"><span data-stu-id="372ba-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="372ba-231">Для управления контейнерами в основном используются такие команды Docker:</span><span class="sxs-lookup"><span data-stu-id="372ba-231">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="372ba-232">docker build</span><span class="sxs-lookup"><span data-stu-id="372ba-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="372ba-233">docker run</span><span class="sxs-lookup"><span data-stu-id="372ba-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="372ba-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="372ba-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="372ba-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="372ba-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="372ba-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="372ba-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="372ba-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="372ba-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="372ba-238">docker image</span><span class="sxs-lookup"><span data-stu-id="372ba-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="372ba-239">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="372ba-239">Clean up resources</span></span>

<span data-ttu-id="372ba-240">В этом руководстве описано, как создать контейнеры и образы.</span><span class="sxs-lookup"><span data-stu-id="372ba-240">During this tutorial you created containers and images.</span></span> <span data-ttu-id="372ba-241">При желании эти ресурсы можно удалить.</span><span class="sxs-lookup"><span data-stu-id="372ba-241">If you want, delete these resources.</span></span> <span data-ttu-id="372ba-242">Ниже представлены команды, которые позволяют сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="372ba-242">Use the following commands to</span></span>

01. <span data-ttu-id="372ba-243">Вывести список всех контейнеров.</span><span class="sxs-lookup"><span data-stu-id="372ba-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="372ba-244">Остановить запущенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="372ba-244">Stop containers that are running.</span></span> <span data-ttu-id="372ba-245">`CONTAINER_NAME` представляет имя, автоматически назначаемое контейнеру.</span><span class="sxs-lookup"><span data-stu-id="372ba-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="372ba-246">Удалить контейнер.</span><span class="sxs-lookup"><span data-stu-id="372ba-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="372ba-247">Затем удалите все ненужные образы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="372ba-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="372ba-248">Удалите образ, созданный с помощью файла *Dockerfile*, а затем удалите образ .NET Core, на основе которого был создан файл *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="372ba-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="372ba-249">Вы можете использовать значение **IMAGE ID** или строку в формате **РЕПОЗИТОРИЙ:МЕТКА**.</span><span class="sxs-lookup"><span data-stu-id="372ba-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="372ba-250">С помощью команды `docker images` просмотрите список установленных образов.</span><span class="sxs-lookup"><span data-stu-id="372ba-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="372ba-251">Файлы образов могут иметь большой размер.</span><span class="sxs-lookup"><span data-stu-id="372ba-251">Image files can be large.</span></span> <span data-ttu-id="372ba-252">Как правило, удаляются временные контейнеры, созданные в ходе тестирования и разработки приложения.</span><span class="sxs-lookup"><span data-stu-id="372ba-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="372ba-253">При этом рекомендуется оставить базовые образы с установленной средой выполнения, если на ее основе вы планируете создавать другие образы.</span><span class="sxs-lookup"><span data-stu-id="372ba-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="372ba-254">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="372ba-254">Next steps</span></span>

- [<span data-ttu-id="372ba-255">Изучите руководство по микрослужбам ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="372ba-255">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="372ba-256">Узнайте больше о службах Azure, которые поддерживают контейнеры.</span><span class="sxs-lookup"><span data-stu-id="372ba-256">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="372ba-257">Ознакомьтесь с командами Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="372ba-257">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="372ba-258">Изучите инструменты Visual Studio для контейнеров</span><span class="sxs-lookup"><span data-stu-id="372ba-258">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
