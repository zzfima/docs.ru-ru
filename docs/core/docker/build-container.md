---
title: Руководство "Контейнеризация приложений с помощью Docker"
description: Из этого руководства вы узнаете, как контейнеризировать приложение .NET Core с помощью Docker.
ms.date: 01/09/2020
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 8be12792e4a9e8511dba87e657f700cc4ec97a16
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546579"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="4c1d9-103">Учебник. Контейнеризация приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="4c1d9-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="4c1d9-104">В этом руководстве показано, как создать образ Docker, содержащий приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="4c1d9-105">Этот образ можно использовать для создания контейнеров в вашей локальной среде разработки, частном или общедоступном облаке.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="4c1d9-106">Вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-106">You'll learn to:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="4c1d9-107">создать и опубликовать простое приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="4c1d9-107">Create and publish a simple .NET Core app</span></span>
> - <span data-ttu-id="4c1d9-108">создать и настроить Dockerfile для .NET Core;</span><span class="sxs-lookup"><span data-stu-id="4c1d9-108">Create and configure a Dockerfile for .NET Core</span></span>
> - <span data-ttu-id="4c1d9-109">Создание образа Docker</span><span class="sxs-lookup"><span data-stu-id="4c1d9-109">Build a Docker image</span></span>
> - <span data-ttu-id="4c1d9-110">создать и запустить контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-110">Create and run a Docker container</span></span>

<span data-ttu-id="4c1d9-111">Вы также узнаете о задачах сборки и развертывания контейнера Docker для приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="4c1d9-112">*Платформа Docker* использует *модуль Docker* для быстрой сборки и упаковки приложений в качестве *образов Docker*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="4c1d9-113">Эти образы имеют формат *Dockerfile* и предназначены для развертывания и запуска в многоуровневом контейнере.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

> [!WARNING]
> <span data-ttu-id="4c1d9-114">**Это руководство не относится к приложениям ASP.NET Core.**</span><span class="sxs-lookup"><span data-stu-id="4c1d9-114">**This tutorial isn't for ASP.NET Core apps.**</span></span> <span data-ttu-id="4c1d9-115">Если вы используете ASP.NET Core, см. руководство по [контейнеризации приложений ASP.NET Core](/aspnet/core/host-and-deploy/docker/building-net-docker-images).</span><span class="sxs-lookup"><span data-stu-id="4c1d9-115">If you're using ASP.NET Core, read the [Learn how to containerize an ASP.NET Core application](/aspnet/core/host-and-deploy/docker/building-net-docker-images) tutorial.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4c1d9-116">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4c1d9-116">Prerequisites</span></span>

<span data-ttu-id="4c1d9-117">Установите следующие необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-117">Install the following prerequisites:</span></span>

- <span data-ttu-id="4c1d9-118">[Пакет SDK для .NET Core 3.1](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="4c1d9-118">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download)</span></span>\
<span data-ttu-id="4c1d9-119">Если у вас установлена платформа .NET Core, воспользуйтесь командой `dotnet --info`, чтобы определить версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-119">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- <span data-ttu-id="4c1d9-120">[Docker Community Edition](https://www.docker.com/products/docker-desktop).</span><span class="sxs-lookup"><span data-stu-id="4c1d9-120">[Docker Community Edition](https://www.docker.com/products/docker-desktop)</span></span>

- <span data-ttu-id="4c1d9-121">Временная рабочая папка для *Dockerfile* и примера приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-121">A temporary working folder for the *Dockerfile* and .NET Core example app.</span></span> <span data-ttu-id="4c1d9-122">В этом руководстве в качестве рабочей папки используется имя *docker-working*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-122">In this tutorial, the name *docker-working* is used as the working folder.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="4c1d9-123">Создание приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="4c1d9-123">Create .NET Core app</span></span>

<span data-ttu-id="4c1d9-124">Вам нужно создать приложение .NET Core для выполнения контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-124">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="4c1d9-125">Откройте терминал, создайте рабочую папку, если вы еще этого не сделали, и войдите в нее.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-125">Open your terminal, create a working folder if you haven't already, and enter it.</span></span> <span data-ttu-id="4c1d9-126">Выполните следующую команду в рабочей папке, чтобы создать проект во вложенной папке с именем *app*:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-126">In the working folder, run the following command to create a new project in a subdirectory named *app*:</span></span>

```dotnetcli
dotnet new console -o app -n myapp
```

<span data-ttu-id="4c1d9-127">Дерево папок будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-127">Your folder tree will look like the following:</span></span>

```
docker-working
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    └───obj
            myapp.csproj.nuget.cache
            myapp.csproj.nuget.dgspec.json
            myapp.csproj.nuget.g.props
            myapp.csproj.nuget.g.targets
            project.assets.json
```

<span data-ttu-id="4c1d9-128">Команда `dotnet new` создает папку с именем *app* и приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-128">The `dotnet new` command creates a new folder named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="4c1d9-129">Войдите в папку *app* и выполните команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-129">Enter the *app* folder and run the command `dotnet run`.</span></span> <span data-ttu-id="4c1d9-130">Вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-130">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="4c1d9-131">Шаблон по умолчанию создает приложение, которое выводит текст в терминал и затем завершает работу.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-131">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="4c1d9-132">В этом руководстве описано, как использовать приложение с бесконечным циклом выполнения.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-132">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="4c1d9-133">Откройте файл *Program.cs* в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-133">Open the *Program.cs* file in a text editor.</span></span> <span data-ttu-id="4c1d9-134">Файл должен содержать следующий код:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-134">It should currently look like the following code:</span></span>

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

<span data-ttu-id="4c1d9-135">Замените его кодом, который считает числа каждую секунду:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-135">Replace the file with the following code that counts numbers every second:</span></span>

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

<span data-ttu-id="4c1d9-136">Сохраните файл и протестируйте программу еще раз с помощью команды `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-136">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="4c1d9-137">Помните, что это приложение выполняется бесконечно.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-137">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="4c1d9-138">Остановите его с помощью команды отмены, нажав клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-138">Use the cancel command <kbd>CTRL</kbd>+<kbd>C</kbd> to stop it.</span></span> <span data-ttu-id="4c1d9-139">Вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-139">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="4c1d9-140">Если приложению передать число в командной строке, оно досчитает до такого числа и завершит работу.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-140">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="4c1d9-141">Введите команду `dotnet run -- 5`, чтобы приложение досчитало до пяти.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-141">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="4c1d9-142">Все параметры после `--` не передаются команде `dotnet run`, а передаются в приложение.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-142">Any parameters after `--` are not passed to the `dotnet run` command and instead are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="4c1d9-143">Публикация приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="4c1d9-143">Publish .NET Core app</span></span>

<span data-ttu-id="4c1d9-144">Прежде чем добавить приложение .NET Core в образ Docker, опубликуйте его.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-144">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="4c1d9-145">Убедитесь, что выполняемый контейнер запускает опубликованную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-145">You want to make sure that the container runs the published version of the app when it's started.</span></span>

<span data-ttu-id="4c1d9-146">Из рабочей папки перейдите в папку *app* с примером исходного кода и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-146">From the working folder, enter the *app* folder with the example source code and run the following command:</span></span>

```dotnetcli
dotnet publish -c Release
```

<span data-ttu-id="4c1d9-147">Эта команда компилирует приложение и помещает результат в папку *publish*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-147">This command compiles your app to the *publish* folder.</span></span> <span data-ttu-id="4c1d9-148">Путь к папке *publish* из рабочей папки должен быть таким: `.\app\bin\Release\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="4c1d9-148">The path to the *publish* folder from the working folder should be `.\app\bin\Release\netcoreapp3.1\publish\`</span></span>

<span data-ttu-id="4c1d9-149">Получите список файлов для папки publish из папки *приложения*, чтобы убедится, что файл *myapp.dll* создан.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-149">From the *app* folder, get a directory listing of the publish folder to verify that the *myapp.dll* file was created.</span></span>

```console
> dir bin\Release\netcoreapp3.1\publish

    Directory:  C:\docker-working\app\bin\Release\netcoreapp3.1\publish

01/09/2020  11:41 AM    <DIR>          .
01/09/2020  11:41 AM    <DIR>          ..
01/09/2020  11:41 AM               407 myapp.deps.json
01/09/2020  12:15 PM             4,608 myapp.dll
01/09/2020  12:15 PM           169,984 myapp.exe
01/09/2020  12:15 PM               736 myapp.pdb
01/09/2020  11:41 AM               154 myapp.runtimeconfig.json
```

<span data-ttu-id="4c1d9-150">Если вы используете Linux или macOS, воспользуйтесь командой `ls`, чтобы получить список каталога и проверить, был ли создан файл *myapp.dl*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-150">If you're using Linux or macOS, use the `ls` command to get a directory listing and verify that the *myapp.dll* file was created.</span></span>

```bash
me@DESKTOP:/docker-working/app$ ls bin/Release/netcoreapp3.1/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

## <a name="create-the-dockerfile"></a><span data-ttu-id="4c1d9-151">Создание файла Dockerfile</span><span class="sxs-lookup"><span data-stu-id="4c1d9-151">Create the Dockerfile</span></span>

<span data-ttu-id="4c1d9-152">Файл *Dockerfile* используется командой `docker build` для создания образа контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-152">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="4c1d9-153">Это текстовый файл с именем *Dockerfile*, не имеющий расширения.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-153">This file is a text file named *Dockerfile* that doesn't have an extension.</span></span>

<span data-ttu-id="4c1d9-154">В окне терминала перейдите к каталогу на один уровень выше рабочей папки, созданной ранее.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-154">In your terminal, navigate up a directory to the working folder you created at the start.</span></span> <span data-ttu-id="4c1d9-155">Создайте файл с именем *Dockerfile* в рабочей папке и откройте его в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-155">Create a file named *Dockerfile* in your working folder and open it in a text editor.</span></span> <span data-ttu-id="4c1d9-156">В зависимости от типа приложения, которое вы собираетесь контейнеризировать, вы выберите среду выполнения ASP.NET Core или .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-156">Depending on the type of application you're going to containerize, you'll choose either the ASP.NET Core runtime or the .NET Core runtime.</span></span> <span data-ttu-id="4c1d9-157">Если сомневаетесь, выберите среду выполнения ASP.NET Core, которая включает среду выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-157">When in doubt, choose the ASP.NET Core runtime, which includes the .NET Core runtime.</span></span> <span data-ttu-id="4c1d9-158">В этом учебнике будет использоваться образ среды выполнения ASP.NET Core, однако приложение, созданное в предыдущих разделах, является приложением .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-158">This tutorial will use the ASP.NET Core runtime image, but the application created in the previous sections is an .NET Core application.</span></span>

- <span data-ttu-id="4c1d9-159">Среда выполнения ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4c1d9-159">ASP.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
  ```

- <span data-ttu-id="4c1d9-160">Среда выполнения .NET Core</span><span class="sxs-lookup"><span data-stu-id="4c1d9-160">.NET Core runtime</span></span>

  ```dockerfile
  FROM mcr.microsoft.com/dotnet/core/runtime:3.1
  ```

<span data-ttu-id="4c1d9-161">Команда `FROM` указывает Docker вызвать образ с тегом **3.1** из определенного репозитория.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-161">The `FROM` command tells Docker to pull down the image tagged **3.1** from the specified repository.</span></span> <span data-ttu-id="4c1d9-162">Убедитесь, что вызываете версию среды выполнения, которая соответствует версии среды выполнения, с которой работает пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-162">Make sure that you pull the runtime version that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="4c1d9-163">Например, приложение, созданное в предыдущем разделе, использовало пакет SDK для .NET Core 3.1, а базовый образ, указанный в *Dockerfile*, помечен **3.1.** .</span><span class="sxs-lookup"><span data-stu-id="4c1d9-163">For example, the app created in the previous section used the .NET Core 3.1 SDK and the base image referred to in the *Dockerfile* is tagged with **3.1**.</span></span>

<span data-ttu-id="4c1d9-164">Сохраните файл *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-164">Save the *Dockerfile* file.</span></span> <span data-ttu-id="4c1d9-165">Структура каталогов рабочей папки должна выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-165">The directory structure of the working folder should look like the following.</span></span> <span data-ttu-id="4c1d9-166">Некоторые файлы и папки на более глубоком уровне были вырезаны для экономии места в статье:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-166">Some of the deeper-level files and folders have been cut to save space in the article:</span></span>

```
docker-working
│   Dockerfile
│
└───app
    │   myapp.csproj
    │   Program.cs
    │
    ├───bin
    │   └───Release
    │       └───netcoreapp3.1
    │           └───publish
    │                   myapp.deps.json
    │                   myapp.exe
    │                   myapp.dll
    │                   myapp.pdb
    │                   myapp.runtimeconfig.json
    │
    └───obj
```

<span data-ttu-id="4c1d9-167">В терминале выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-167">From your terminal, run the following command:</span></span>

```console
docker build -t myimage -f Dockerfile .
```

<span data-ttu-id="4c1d9-168">Docker обработает все строки файла *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-168">Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="4c1d9-169">Символ `.` в команде `docker build` используется, чтобы выполнить с помощью Docker поиск файла *Dockerfile* в текущей папке.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-169">The `.` in the `docker build` command tells Docker to use the current folder to find a *Dockerfile*.</span></span> <span data-ttu-id="4c1d9-170">Эта команда создает образ и локальный репозиторий с именем **myimage**, который указывает на такой образ.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-170">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="4c1d9-171">После завершения работы этой команды выполните команду `docker images`, чтобы просмотреть список установленных образов:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-171">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              38db0eb8f648        4 weeks ago         346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="4c1d9-172">Обратите внимание, что два образа имеют одинаковое значение **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-172">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="4c1d9-173">Это связано с тем, что единственная команда в файле *Dockerfile* создает новый образ на основе существующего.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-173">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="4c1d9-174">Добавим в файл *Dockerfile* еще две команды.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-174">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="4c1d9-175">Каждая команда создает новый уровень образа, а последняя команда представляет образ, на который указывает запись в репозитории **myimage**.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-175">Each command creates a new image layer with the final command representing the image the **myimage** repository entry points to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp3.1/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="4c1d9-176">Команда `COPY` предписывает Docker скопировать указанную папку на вашем компьютере в папку в контейнере.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-176">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="4c1d9-177">В этом примере папка *publish* копируется в папку с именем *app* в контейнере.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-177">In this example, the *publish* folder is copied to a folder named *app* in the container.</span></span>

<span data-ttu-id="4c1d9-178">Следующая команда `ENTRYPOINT` используется, чтобы настроить с помощью Docker контейнер для запуска в качестве исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-178">The next command, `ENTRYPOINT`, tells Docker to configure the container to run as an executable.</span></span> <span data-ttu-id="4c1d9-179">При запуске контейнера выполняется команда `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-179">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="4c1d9-180">После выполнения команды контейнер автоматически остановится.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-180">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="4c1d9-181">В окне терминала выполните команду `docker build -t myimage -f Dockerfile .`, а после ее выполнения — команду `docker images`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-181">From your terminal, run `docker build -t myimage -f Dockerfile .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage -f Dockerfile .
Sending build context to Docker daemon  1.624MB
Step 1/3 : FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
 ---> 38db0eb8f648
Step 2/3 : COPY app/bin/Release/netcoreapp3.1/publish/ app/
 ---> 37873673e468
Step 3/3 : ENTRYPOINT ["dotnet", "app/myapp.dll"]
 ---> Running in d8deb7b3aa9e
Removing intermediate container d8deb7b3aa9e
 ---> 0d602ca35c1d
Successfully built 0d602ca35c1d
Successfully tagged myimage:latest

> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
myimage                                 latest              0d602ca35c1d        4 seconds ago       346MB
mcr.microsoft.com/dotnet/core/aspnet    3.1                 38db0eb8f648        4 weeks ago         346MB
```

<span data-ttu-id="4c1d9-182">Каждая команда в файле *Dockerfile* создает уровень и экземпляр **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-182">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="4c1d9-183">Последний экземпляр **IMAGE ID** (ваш идентификатор будет отличаться) имеет значение **ddcc6646461b**. Теперь вы создадите контейнер на основе этого образа.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-183">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="4c1d9-184">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="4c1d9-184">Create a container</span></span>

<span data-ttu-id="4c1d9-185">Теперь, когда у вас есть образ, содержащий приложение, вы можете создать контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-185">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="4c1d9-186">Контейнер можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-186">You can create a container in two ways.</span></span> <span data-ttu-id="4c1d9-187">Сначала создайте остановленный контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-187">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
ceda87b219a4e55e9ad5d833ee1a7ea4da21b5ea7ce5a7d08f3051152e784944
```

<span data-ttu-id="4c1d9-188">Команда `docker create` выше создает контейнер на основе образа **myimage**.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-188">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="4c1d9-189">В выходных данных этой команды присутствует **CONTAINER ID** (ваш идентификатор будет отличаться) созданного контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-189">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="4c1d9-190">Чтобы просмотреть список *всех* контейнеров, воспользуйтесь командой `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-190">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               gallant_lehmann
```

### <a name="manage-the-container"></a><span data-ttu-id="4c1d9-191">Управление контейнером</span><span class="sxs-lookup"><span data-stu-id="4c1d9-191">Manage the container</span></span>

<span data-ttu-id="4c1d9-192">Каждому контейнеру присваивается случайное имя, с помощью которого можно обращаться к этому экземпляру контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-192">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="4c1d9-193">Например, созданный автоматически контейнер получил имя **gallant_lehmann** (имя вашего контейнера будет отличаться), которое можно использовать для запуска контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-193">For example, the container that was created automatically chose the name **gallant_lehmann** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="4c1d9-194">Чтобы переопределить автоматически созданное имя и указать другое, используйте параметр `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-194">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="4c1d9-195">В следующем примере используется команда `docker start` для запуска контейнера, а затем — команда `docker ps` для отображения только запущенных контейнеров:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-195">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           gallant_lehmann
```

<span data-ttu-id="4c1d9-196">Аналогично, команда `docker stop` останавливает контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-196">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="4c1d9-197">В следующем примере используется команда `docker stop` для остановки контейнера, а затем — команда `docker ps` для подтверждения того, что контейнеры не запущены:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-197">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running:</span></span>

```console
> docker stop gallant_lehmann
gallant_lehmann

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="4c1d9-198">Подключение к контейнеру</span><span class="sxs-lookup"><span data-stu-id="4c1d9-198">Connect to a container</span></span>

<span data-ttu-id="4c1d9-199">После запуска контейнера вы можете подключиться к нему, чтобы просмотреть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-199">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="4c1d9-200">С помощью команд `docker start` и `docker attach` запустите контейнер и просмотрите поток вывода.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-200">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="4c1d9-201">В этом примере команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, используется для отключения от запущенного контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-201">In this example, the <kbd>CTRL + C</kbd> keystroke is used to detach from the running container.</span></span> <span data-ttu-id="4c1d9-202">Нажатие этих клавиш может привести к завершению процесса в контейнере и его последующей остановке.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-202">This keystroke may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="4c1d9-203">Параметр `--sig-proxy=false` гарантирует, что команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, не остановит процесс в контейнере.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-203">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> won't stop the process in the container.</span></span>

<span data-ttu-id="4c1d9-204">После отключения от контейнера снова подключитесь к нему, чтобы убедиться в том, что он продолжает работать и считать числа.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-204">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

```console
> docker start gallant_lehmann
gallant_lehmann

> docker attach --sig-proxy=false gallant_lehmann
Counter: 7
Counter: 8
Counter: 9
^C

> docker attach --sig-proxy=false gallant_lehmann
Counter: 17
Counter: 18
Counter: 19
^C
```

### <a name="delete-a-container"></a><span data-ttu-id="4c1d9-205">Удаление контейнера</span><span class="sxs-lookup"><span data-stu-id="4c1d9-205">Delete a container</span></span>

<span data-ttu-id="4c1d9-206">В рамках этого руководства предполагается, что вам не нужны контейнеры, которые запущены, но не выполняют полезные действия.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-206">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="4c1d9-207">Удалите созданный ранее контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-207">Delete the container you previously created.</span></span> <span data-ttu-id="4c1d9-208">Если контейнер запущен, остановите его.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-208">If the container is running, stop it.</span></span>

```console
> docker stop gallant_lehmann
```

<span data-ttu-id="4c1d9-209">В примере ниже выводится список всех контейнеров,</span><span class="sxs-lookup"><span data-stu-id="4c1d9-209">The following example lists all containers.</span></span> <span data-ttu-id="4c1d9-210">а затем используется команда `docker rm` для удаления контейнера. После этого выполняется повторная проверка наличия запущенных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-210">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
ceda87b219a4        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             gallant_lehmann

> docker rm gallant_lehmann
gallant_lehmann

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="4c1d9-211">Однократный запуск</span><span class="sxs-lookup"><span data-stu-id="4c1d9-211">Single run</span></span>

<span data-ttu-id="4c1d9-212">Docker предоставляет единую команду `docker run` для создания и запуска контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-212">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="4c1d9-213">Она исключает необходимость в поочередном выполнении команд `docker create` и `docker start`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-213">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="4c1d9-214">Вы также можете настроить ее для автоматического удаления контейнера при его остановке.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-214">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="4c1d9-215">Например, команда `docker run -it --rm` выполняет две операции. Сначала она автоматически подключается к контейнеру с помощью текущего терминала, а потом, после завершения работы контейнера, удаляет его:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-215">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```console
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="4c1d9-216">Во время выполнения `docker run -it` команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, остановит процесс, запущенный в контейнере. А это в свою очередь приведет к остановке контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-216">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="4c1d9-217">Так как в команде указан параметр `--rm`, контейнер автоматически удалится после остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-217">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="4c1d9-218">Убедитесь, что он больше не существует:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-218">Verify that it doesn't exist:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="4c1d9-219">Изменение команды ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="4c1d9-219">Change the ENTRYPOINT</span></span>

<span data-ttu-id="4c1d9-220">Команда `docker run` также позволяет изменить команду `ENTRYPOINT` из файла *Dockerfile* для запуска другой программы, но только для соответствующего контейнера.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-220">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="4c1d9-221">Например, воспользуйтесь указанной ниже командой, чтобы запустить `bash` или `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-221">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="4c1d9-222">При необходимости измените команду.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-222">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="4c1d9-223">Windows</span><span class="sxs-lookup"><span data-stu-id="4c1d9-223">Windows</span></span>

<span data-ttu-id="4c1d9-224">В этом примере команда `ENTRYPOINT` изменена на `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-224">In this example, `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="4c1d9-225">Нажав клавиши <kbd>CTRL</kbd>+<kbd>C</kbd>, вы можете завершить процесс и остановить контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-225"><kbd>CTRL</kbd>+<kbd>C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="4c1d9-226">Linux</span><span class="sxs-lookup"><span data-stu-id="4c1d9-226">Linux</span></span>

<span data-ttu-id="4c1d9-227">В этом примере команда `ENTRYPOINT` изменена на `bash`.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-227">In this example, `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="4c1d9-228">Команда `quit` позволяет завершить процесс и остановить контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-228">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="4c1d9-229">Основные команды</span><span class="sxs-lookup"><span data-stu-id="4c1d9-229">Essential commands</span></span>

<span data-ttu-id="4c1d9-230">Docker предоставляет множество команд для операций с контейнером и образами.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-230">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="4c1d9-231">Для управления контейнерами в основном используются такие команды Docker:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-231">These Docker commands are essential to managing your containers:</span></span>

- [<span data-ttu-id="4c1d9-232">docker build</span><span class="sxs-lookup"><span data-stu-id="4c1d9-232">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
- [<span data-ttu-id="4c1d9-233">docker run</span><span class="sxs-lookup"><span data-stu-id="4c1d9-233">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
- [<span data-ttu-id="4c1d9-234">docker ps</span><span class="sxs-lookup"><span data-stu-id="4c1d9-234">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
- [<span data-ttu-id="4c1d9-235">docker stop</span><span class="sxs-lookup"><span data-stu-id="4c1d9-235">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
- [<span data-ttu-id="4c1d9-236">docker rm</span><span class="sxs-lookup"><span data-stu-id="4c1d9-236">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
- [<span data-ttu-id="4c1d9-237">docker rmi</span><span class="sxs-lookup"><span data-stu-id="4c1d9-237">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
- [<span data-ttu-id="4c1d9-238">docker image</span><span class="sxs-lookup"><span data-stu-id="4c1d9-238">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="4c1d9-239">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="4c1d9-239">Clean up resources</span></span>

<span data-ttu-id="4c1d9-240">В этом учебнике описано, как создать контейнеры и образы.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-240">During this tutorial, you created containers and images.</span></span> <span data-ttu-id="4c1d9-241">При желании эти ресурсы можно удалить.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-241">If you want, delete these resources.</span></span> <span data-ttu-id="4c1d9-242">Ниже представлены команды, которые позволяют сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="4c1d9-242">Use the following commands to</span></span>

01. <span data-ttu-id="4c1d9-243">Вывести список всех контейнеров.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-243">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="4c1d9-244">Остановить запущенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-244">Stop containers that are running.</span></span> <span data-ttu-id="4c1d9-245">`CONTAINER_NAME` представляет имя, автоматически назначаемое контейнеру.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-245">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="4c1d9-246">Удалить контейнер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-246">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="4c1d9-247">Затем удалите все ненужные образы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-247">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="4c1d9-248">Удалите образ, созданный с помощью файла *Dockerfile*, а затем удалите образ .NET Core, на основе которого был создан файл *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-248">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="4c1d9-249">Вы можете использовать значение **IMAGE ID** или строку в формате **РЕПОЗИТОРИЙ:МЕТКА**.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-249">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/aspnet:3.1
```

<span data-ttu-id="4c1d9-250">С помощью команды `docker images` просмотрите список установленных образов.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-250">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="4c1d9-251">Файлы образов могут иметь большой размер.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-251">Image files can be large.</span></span> <span data-ttu-id="4c1d9-252">Как правило, удаляются временные контейнеры, созданные в ходе тестирования и разработки приложения.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-252">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="4c1d9-253">При этом рекомендуется оставить базовые образы с установленной средой выполнения, если на ее основе вы планируете создавать другие образы.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-253">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c1d9-254">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="4c1d9-254">Next steps</span></span>

- [<span data-ttu-id="4c1d9-255">Узнайте, как упаковать в контейнер приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-255">Learn how to containerize an ASP.NET Core application.</span></span>](/aspnet/core/host-and-deploy/docker/building-net-docker-images)
- [<span data-ttu-id="4c1d9-256">Изучите руководство по микрослужбам ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-256">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
- [<span data-ttu-id="4c1d9-257">Узнайте больше о службах Azure, которые поддерживают контейнеры.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-257">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/overview/containers/)
- [<span data-ttu-id="4c1d9-258">Ознакомьтесь с командами Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="4c1d9-258">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
- [<span data-ttu-id="4c1d9-259">Изучите инструменты Visual Studio для контейнеров</span><span class="sxs-lookup"><span data-stu-id="4c1d9-259">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)
