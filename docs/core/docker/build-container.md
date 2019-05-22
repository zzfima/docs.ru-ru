---
title: Руководство "Контейнеризация приложений с помощью Docker"
description: Из этого руководства вы узнаете, как контейнеризировать приложение .NET Core с помощью Docker.
ms.date: 04/10/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 7d5fd3da9170ecd33f7a1b6b6d048c174472d541
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750573"
---
# <a name="tutorial-containerize-a-net-core-app"></a><span data-ttu-id="57a7a-103">Учебник. Контейнеризация приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="57a7a-103">Tutorial: Containerize a .NET Core app</span></span>

<span data-ttu-id="57a7a-104">В этом руководстве показано, как создать образ Docker, содержащий приложение .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a7a-104">This tutorial teaches you how to build a Docker image that contains your .NET Core application.</span></span> <span data-ttu-id="57a7a-105">Этот образ можно использовать для создания контейнеров в вашей локальной среде разработки, частном или общедоступном облаке.</span><span class="sxs-lookup"><span data-stu-id="57a7a-105">The image can be used to create containers for your local development environment, private cloud, or public cloud.</span></span>

<span data-ttu-id="57a7a-106">Вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="57a7a-106">You'll learn to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="57a7a-107">создать и опубликовать простое приложение .NET Core;</span><span class="sxs-lookup"><span data-stu-id="57a7a-107">Create and publish a simple .NET Core app</span></span>
> * <span data-ttu-id="57a7a-108">создать и настроить Dockerfile для .NET Core;</span><span class="sxs-lookup"><span data-stu-id="57a7a-108">Create and configure a Dockerfile for .NET Core</span></span>
> * <span data-ttu-id="57a7a-109">Создание образа Docker</span><span class="sxs-lookup"><span data-stu-id="57a7a-109">Build a Docker image</span></span>
> * <span data-ttu-id="57a7a-110">создать и запустить контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="57a7a-110">Create and run a Docker container</span></span>

<span data-ttu-id="57a7a-111">Вы также узнаете о задачах сборки и развертывания контейнера Docker для приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a7a-111">You'll understand the Docker container build and deploy tasks for a .NET Core application.</span></span> <span data-ttu-id="57a7a-112">*Платформа Docker* использует *модуль Docker* для быстрой сборки и упаковки приложений в качестве *образов Docker*.</span><span class="sxs-lookup"><span data-stu-id="57a7a-112">The *Docker platform* uses the *Docker engine* to quickly build and package apps as *Docker images*.</span></span> <span data-ttu-id="57a7a-113">Эти образы имеют формат *Dockerfile* и предназначены для развертывания и запуска в многоуровневом контейнере.</span><span class="sxs-lookup"><span data-stu-id="57a7a-113">These images are written in the *Dockerfile* format to be deployed and run in a layered container.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57a7a-114">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="57a7a-114">Prerequisites</span></span>

<span data-ttu-id="57a7a-115">Установите следующие необходимые компоненты:</span><span class="sxs-lookup"><span data-stu-id="57a7a-115">Install the following prerequisites:</span></span>

- <span data-ttu-id="57a7a-116">[Пакет .NET для Core версии 2.2](https://dotnet.microsoft.com/download)\.</span><span class="sxs-lookup"><span data-stu-id="57a7a-116">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)\\</span></span>
<span data-ttu-id="57a7a-117">Если у вас установлена платформа .NET Core, воспользуйтесь командой `dotnet --info`, чтобы определить версию пакета SDK.</span><span class="sxs-lookup"><span data-stu-id="57a7a-117">If you have .NET Core installed, use the `dotnet --info` command to determine which SDK you're using.</span></span>

- <span data-ttu-id="57a7a-118">[Docker Community Edition](https://www.docker.com/products/docker-desktop).</span><span class="sxs-lookup"><span data-stu-id="57a7a-118">[Docker Community Edition](https://www.docker.com/products/docker-desktop)</span></span>

- <span data-ttu-id="57a7a-119">Временная рабочая папка для *Dockerfile* и примера приложения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a7a-119">A temporary working directory for the *Dockerfile* and .NET Core example app.</span></span>

### <a name="use-sdk-version-22"></a><span data-ttu-id="57a7a-120">Использование пакета SDK версии 2.2</span><span class="sxs-lookup"><span data-stu-id="57a7a-120">Use SDK version 2.2</span></span>

<span data-ttu-id="57a7a-121">Если вы работаете с пакетом SDK более новой версии (например, 3.0), убедитесь, что приложение использует версию 2.2.</span><span class="sxs-lookup"><span data-stu-id="57a7a-121">If you're using an SDK that is newer, like 3.0, make sure that your app is forced to use the 2.2 SDK.</span></span> <span data-ttu-id="57a7a-122">Создайте файл с именем `global.json` в рабочей папке и вставьте в него следующий код JSON:</span><span class="sxs-lookup"><span data-stu-id="57a7a-122">Create a file named `global.json` in your working directory and paste in the following json code:</span></span>

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

<span data-ttu-id="57a7a-123">Сохраните этот файл.</span><span class="sxs-lookup"><span data-stu-id="57a7a-123">Save this file.</span></span> <span data-ttu-id="57a7a-124">При наличии такого файла .NET Core будет использовать версию 2.2 для всех команд `dotnet`, вызванных из этого каталога и его подкаталогов.</span><span class="sxs-lookup"><span data-stu-id="57a7a-124">The presence of file will force .NET Core to use version 2.2 for any `dotnet` command called from this directory and below.</span></span>

## <a name="create-net-core-app"></a><span data-ttu-id="57a7a-125">Создание приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="57a7a-125">Create .NET Core app</span></span>

<span data-ttu-id="57a7a-126">Вам нужно создать приложение .NET Core для выполнения контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="57a7a-126">You need a .NET Core app that the Docker container will run.</span></span> <span data-ttu-id="57a7a-127">Откройте терминал, создайте рабочую папку и перейдите в нее.</span><span class="sxs-lookup"><span data-stu-id="57a7a-127">Open your terminal, create a working directory, and enter it.</span></span> <span data-ttu-id="57a7a-128">Выполните следующую команду в рабочей папке, чтобы создать проект в подпапке с именем app:</span><span class="sxs-lookup"><span data-stu-id="57a7a-128">In the working directory, run the following command to create a new project in a subdirectory named app:</span></span>

```console
dotnet new console -o app -n myapp
```

<span data-ttu-id="57a7a-129">Эта команда создает папку с именем *app* и приложение Hello World.</span><span class="sxs-lookup"><span data-stu-id="57a7a-129">That command creates a new directory named *app* and generates a "Hello World" app.</span></span> <span data-ttu-id="57a7a-130">Вы можете протестировать это приложение, чтобы понять, что оно делает.</span><span class="sxs-lookup"><span data-stu-id="57a7a-130">You can test this app to see what it does.</span></span> <span data-ttu-id="57a7a-131">Перейдите в каталог *app* и выполните команду `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-131">Enter the *app* directory and execute the command `dotnet run`.</span></span> <span data-ttu-id="57a7a-132">Вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="57a7a-132">You'll see the following output:</span></span>

```console
> dotnet run
Hello World!
```

<span data-ttu-id="57a7a-133">Шаблон по умолчанию создает приложение, которое выводит текст в терминал и затем завершает работу.</span><span class="sxs-lookup"><span data-stu-id="57a7a-133">The default template creates an app that prints to the terminal and then exits.</span></span> <span data-ttu-id="57a7a-134">В этом руководстве описано, как использовать приложение с бесконечным циклом выполнения.</span><span class="sxs-lookup"><span data-stu-id="57a7a-134">For this tutorial, you'll use an app that loops indefinitely.</span></span> <span data-ttu-id="57a7a-135">Откройте файл **Program.cs** в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="57a7a-135">Open the **Program.cs** file in a text editor.</span></span> <span data-ttu-id="57a7a-136">Файл должен содержать следующий код:</span><span class="sxs-lookup"><span data-stu-id="57a7a-136">It should currently look like the following code:</span></span>

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

<span data-ttu-id="57a7a-137">Замените его кодом, который считает числа каждую секунду:</span><span class="sxs-lookup"><span data-stu-id="57a7a-137">Replace the file with the following code that counts numbers every second:</span></span>

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
            while(max == -1 || counter < max)
            {
                counter++;
                Console.WriteLine($"Counter: {counter}");
                System.Threading.Tasks.Task.Delay(1000).Wait();
            }
        }
    }
}
```

<span data-ttu-id="57a7a-138">Сохраните файл и протестируйте программу еще раз с помощью команды `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-138">Save the file and test the program again with `dotnet run`.</span></span> <span data-ttu-id="57a7a-139">Помните, что это приложение выполняется бесконечно.</span><span class="sxs-lookup"><span data-stu-id="57a7a-139">Remember that this app runs indefinitely.</span></span> <span data-ttu-id="57a7a-140">Остановите его с помощью команды отмены, нажав клавиши <kbd>CTRL+C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="57a7a-140">Use the cancel command <kbd>CTRL + C</kbd> to stop it.</span></span> <span data-ttu-id="57a7a-141">Вы увидите следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="57a7a-141">You'll see the following output:</span></span>

```console
> dotnet run
Counter: 1
Counter: 2
Counter: 3
Counter: 4
^C
```

<span data-ttu-id="57a7a-142">Если приложению передать число в командной строке, оно досчитает до такого числа и завершит работу.</span><span class="sxs-lookup"><span data-stu-id="57a7a-142">If you pass a number on the command line to the app, it will only count up to that amount and then exit.</span></span> <span data-ttu-id="57a7a-143">Введите команду `dotnet run -- 5`, чтобы приложение досчитало до пяти.</span><span class="sxs-lookup"><span data-stu-id="57a7a-143">Try it with `dotnet run -- 5` to count to five.</span></span>

> [!NOTE]
> <span data-ttu-id="57a7a-144">Все параметры после `--` передаются приложению.</span><span class="sxs-lookup"><span data-stu-id="57a7a-144">Any parameters after `--` are passed to your application.</span></span>

## <a name="publish-net-core-app"></a><span data-ttu-id="57a7a-145">Публикация приложения .NET Core</span><span class="sxs-lookup"><span data-stu-id="57a7a-145">Publish .NET Core app</span></span>

<span data-ttu-id="57a7a-146">Прежде чем добавить приложение .NET Core в образ Docker, опубликуйте его.</span><span class="sxs-lookup"><span data-stu-id="57a7a-146">Before you add your .NET Core app to the Docker image, publish it.</span></span> <span data-ttu-id="57a7a-147">Выполняемый контейнер будет запускать опубликованную версию приложения.</span><span class="sxs-lookup"><span data-stu-id="57a7a-147">The container will execute the published version of the app when it's started.</span></span>

<span data-ttu-id="57a7a-148">Из рабочей папки перейдите в каталог **app** с примером исходного кода и выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="57a7a-148">From the working directory, enter the **app** directory with the example source code and run the following command:</span></span>

```console
dotnet publish -c Release
```

<span data-ttu-id="57a7a-149">Эта команда компилирует приложение и помещает результат в папку **publish** в выходной папке приложения.</span><span class="sxs-lookup"><span data-stu-id="57a7a-149">This command compiles your app to the **publish** folder in the output folder of your app.</span></span> <span data-ttu-id="57a7a-150">Путь к папке **publish** из рабочей папки должен быть таким: `.\app\bin\Release\netcoreapp2.2\publish\`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-150">The path to the **publish** folder from the working directory should be `.\app\bin\Release\netcoreapp2.2\publish\`</span></span>

<span data-ttu-id="57a7a-151">Получите список файлов для папки publish, чтобы убедиться в наличии файла **myapp.dll**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-151">Get a directory listing of the publish folder to verify that the **myapp.dll** was created.</span></span> <span data-ttu-id="57a7a-152">Из каталога **app** выполните одну из следующих команд:</span><span class="sxs-lookup"><span data-stu-id="57a7a-152">From the **app** directory, run one of the following commands:</span></span>

```console
> dir bin\Release\netcoreapp2.2\publish
 Directory of C:\path-to-working-dir\app\bin\Release\netcoreapp2.2\publish

04/05/2019  11:00 AM    <DIR>          .
04/05/2019  11:00 AM    <DIR>          ..
04/05/2019  11:00 AM               447 myapp.deps.json
04/05/2019  11:00 AM             4,608 myapp.dll
04/05/2019  11:00 AM               448 myapp.pdb
04/05/2019  11:00 AM               154 myapp.runtimeconfig.json
```

```bash
me@DESKTOP:/path-to-working-dir/app$ ls bin/Release/netcoreapp2.2/publish
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
```

<span data-ttu-id="57a7a-153">В окне терминала перейдите на уровень выше к рабочей папке.</span><span class="sxs-lookup"><span data-stu-id="57a7a-153">In your terminal, go up a directory to the working directory.</span></span>

## <a name="create-the-dockerfile"></a><span data-ttu-id="57a7a-154">Создание файла Dockerfile</span><span class="sxs-lookup"><span data-stu-id="57a7a-154">Create the Dockerfile</span></span>

<span data-ttu-id="57a7a-155">Файл *Dockerfile* используется командой `docker build` для создания образа контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-155">The *Dockerfile* file is used by the `docker build` command to create a container image.</span></span> <span data-ttu-id="57a7a-156">Это текстовый файл с именем *Dockerfile* и без расширения.</span><span class="sxs-lookup"><span data-stu-id="57a7a-156">This file is a plaintext file named *Dockerfile* that does not have an extension.</span></span> <span data-ttu-id="57a7a-157">Создайте файл с именем *Dockerfile* в рабочей папке и откройте его в текстовом редакторе.</span><span class="sxs-lookup"><span data-stu-id="57a7a-157">Create a file named *Dockerfile* in your working directory and open it in a text editor.</span></span> <span data-ttu-id="57a7a-158">Добавьте следующую команду в первую строку файла:</span><span class="sxs-lookup"><span data-stu-id="57a7a-158">Add the following command as the first line of the file:</span></span>

```dockerfile
FROM mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="57a7a-159">Команда `FROM` указывает Docker вызвать образ с тегом **2.2** из репозитория **mcr.microsoft.com/dotnet/core/runtime**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-159">The `FROM` command tells Docker to pull down the image tagged **2.2** from the **mcr.microsoft.com/dotnet/core/runtime** repository.</span></span> <span data-ttu-id="57a7a-160">Убедитесь, что вы вызываете среду выполнения .NET Core, версия которой соответствует версии среды выполнения, с которой работает пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="57a7a-160">Make sure that you pull the .NET Core runtime that matches the runtime targeted by your SDK.</span></span> <span data-ttu-id="57a7a-161">Например, приложение, созданное в предыдущем разделе, использует пакет SDK для .NET Core версии 2.2. Также было создано приложение для .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="57a7a-161">For example, the app created in the previous section used the .NET Core 2.2 SDK and created an app that targeted .NET Core 2.2.</span></span> <span data-ttu-id="57a7a-162">Поэтому базовый образ, который указан в файле *Dockerfile*, должен иметь тег **2.2**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-162">So the base image referred to in the *Dockerfile* is tagged with **2.2**.</span></span>

<span data-ttu-id="57a7a-163">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="57a7a-163">Save the file.</span></span> <span data-ttu-id="57a7a-164">В окне терминала выполните команду `docker build -t myimage .`, и Docker обработает все строки файла *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="57a7a-164">From your terminal, run `docker build -t myimage .` and Docker will process each line in the *Dockerfile*.</span></span> <span data-ttu-id="57a7a-165">Символ `.` в команде `docker build` указывает Docker выполнить поиск файла *Dockerfile* в текущем каталоге.</span><span class="sxs-lookup"><span data-stu-id="57a7a-165">The `.` in the `docker build` command tells docker to use the current directory to find a *Dockerfile*.</span></span> <span data-ttu-id="57a7a-166">Эта команда создает образ и локальный репозиторий с именем **myimage**, который указывает на такой образ.</span><span class="sxs-lookup"><span data-stu-id="57a7a-166">This command builds the image and creates a local repository named **myimage** that points to that image.</span></span> <span data-ttu-id="57a7a-167">После завершения работы этой команды выполните команду `docker images`, чтобы просмотреть список установленных образов:</span><span class="sxs-lookup"><span data-stu-id="57a7a-167">After this command finishes, run `docker images` to see a list of images installed:</span></span>

```console
> docker images
REPOSITORY                              TAG                 IMAGE ID            CREATED             SIZE
mcr.microsoft.com/dotnet/core/runtime   2.2                 d51bb4452469        2 days ago          314MB
myimage                                 latest              d51bb4452469        2 days ago          314MB
```

<span data-ttu-id="57a7a-168">Обратите внимание, что два образа имеют одинаковое значение **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-168">Notice that the two images share the same **IMAGE ID** value.</span></span> <span data-ttu-id="57a7a-169">Это связано с тем, что единственная команда в файле *Dockerfile* создает новый образ на основе существующего.</span><span class="sxs-lookup"><span data-stu-id="57a7a-169">The value is the same between both images because the only command in the *Dockerfile* was to base the new image on an existing image.</span></span> <span data-ttu-id="57a7a-170">Добавим в файл *Dockerfile* еще две команды.</span><span class="sxs-lookup"><span data-stu-id="57a7a-170">Let's add two commands to the *Dockerfile*.</span></span> <span data-ttu-id="57a7a-171">Каждая команда создает новый уровень образа, а последняя команда представляет образ, на который будет указывать репозиторий **myimage**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-171">Each command creates a new image layer with the final command representing the image the **myimage** repository will point to.</span></span>

```dockerfile
COPY app/bin/Release/netcoreapp2.2/publish/ app/

ENTRYPOINT ["dotnet", "app/myapp.dll"]
```

<span data-ttu-id="57a7a-172">Команда `COPY` предписывает Docker скопировать указанную папку на вашем компьютере в папку в контейнере.</span><span class="sxs-lookup"><span data-stu-id="57a7a-172">The `COPY` command tells Docker to copy the specified folder on your computer to a folder in the container.</span></span> <span data-ttu-id="57a7a-173">В этом примере папка **publish** копируется в папку с именем **app** в контейнере.</span><span class="sxs-lookup"><span data-stu-id="57a7a-173">In this example, the **publish** folder is copied to a folder named **app** in the container.</span></span>

<span data-ttu-id="57a7a-174">Следующая команда, `ENTRYPOINT`, указывает Docker настроить контейнер для запуска в качестве исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="57a7a-174">The next command, `ENTRYPOINT`, tells docker to configure the container to run as an executable.</span></span> <span data-ttu-id="57a7a-175">При запуске контейнера выполняется команда `ENTRYPOINT`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-175">When the container starts, the `ENTRYPOINT` command runs.</span></span> <span data-ttu-id="57a7a-176">После выполнения команды контейнер автоматически остановится.</span><span class="sxs-lookup"><span data-stu-id="57a7a-176">When this command ends, the container will automatically stop.</span></span>

<span data-ttu-id="57a7a-177">Сохраните файл.</span><span class="sxs-lookup"><span data-stu-id="57a7a-177">Save the file.</span></span> <span data-ttu-id="57a7a-178">В окне терминала выполните команду `docker build -t myimage .`, а после ее выполнения — команду `docker images`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-178">From your terminal, run `docker build -t myimage .` and when that command finishes, run `docker images`.</span></span>

```console
> docker build -t myimage .
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

<span data-ttu-id="57a7a-179">Каждая команда в файле *Dockerfile* создает уровень и экземпляр **IMAGE ID**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-179">Each command in the *Dockerfile* generated a layer and created an **IMAGE ID**.</span></span> <span data-ttu-id="57a7a-180">Последний экземпляр **IMAGE ID** (ваш идентификатор будет отличаться) имеет значение **ddcc6646461b**. Теперь вы создадите контейнер на основе этого образа.</span><span class="sxs-lookup"><span data-stu-id="57a7a-180">The final **IMAGE ID** (yours will be different) is **ddcc6646461b** and next you'll create a container based on this image.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="57a7a-181">Создание контейнера</span><span class="sxs-lookup"><span data-stu-id="57a7a-181">Create a container</span></span>

<span data-ttu-id="57a7a-182">Теперь, когда у вас есть образ, содержащий приложение, вы можете создать контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-182">Now that you have an image that contains your app, you can create a container.</span></span> <span data-ttu-id="57a7a-183">Контейнер можно создать двумя способами.</span><span class="sxs-lookup"><span data-stu-id="57a7a-183">You can create a container in two ways.</span></span> <span data-ttu-id="57a7a-184">Сначала создайте остановленный контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-184">First, create a new container that is stopped.</span></span>

```console
> docker create myimage
0e8f3c2ca32ce773712a5cca38750f41259a4e54e04bdf0946087e230ad7066c
```

<span data-ttu-id="57a7a-185">Команда `docker create` выше создает контейнер на основе образа **myimage**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-185">The `docker create` command from above will create a container based on the **myimage** image.</span></span> <span data-ttu-id="57a7a-186">В выходных данных этой команды присутствует **CONTAINER ID** (ваш идентификатор будет отличаться) созданного контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-186">The output of that command shows you the **CONTAINER ID** (yours will be different) of the created container.</span></span> <span data-ttu-id="57a7a-187">Чтобы просмотреть список *всех* контейнеров, воспользуйтесь командой `docker ps -a`:</span><span class="sxs-lookup"><span data-stu-id="57a7a-187">To see a list of *all* containers, use the `docker ps -a` command:</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS        PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   4 seconds ago       Created               boring_matsumoto
```

### <a name="manage-the-container"></a><span data-ttu-id="57a7a-188">Управление контейнером</span><span class="sxs-lookup"><span data-stu-id="57a7a-188">Manage the container</span></span>

<span data-ttu-id="57a7a-189">Каждому контейнеру присваивается случайное имя, с помощью которого можно обращаться к этому экземпляру контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-189">Each container is assigned a random name that you can use to refer to that container instance.</span></span> <span data-ttu-id="57a7a-190">Например, созданный автоматически контейнер получил имя **boring_matsumoto** (имя вашего контейнера будет отличаться), которое можно использовать для запуска контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-190">For example, the container that was created automatically chose the name **boring_matsumoto** (yours will be different) and that name can be used to start the container.</span></span> <span data-ttu-id="57a7a-191">Чтобы переопределить автоматически созданное имя и указать другое, используйте параметр `docker create --name`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-191">You override the automatic name with a specific one by using the `docker create --name` parameter.</span></span>

<span data-ttu-id="57a7a-192">В следующем примере используется команда `docker start` для запуска контейнера, а затем — команда `docker ps` для отображения только запущенных контейнеров:</span><span class="sxs-lookup"><span data-stu-id="57a7a-192">The following example uses the `docker start` command to start the container, and then uses the `docker ps` command to only show containers that are running:</span></span>

```console
> docker start boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS         PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   7 minutes ago       Up 8 seconds           boring_matsumoto
```

<span data-ttu-id="57a7a-193">Аналогично, команда `docker stop` останавливает контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-193">Similarly, the `docker stop` command will stop the container.</span></span> <span data-ttu-id="57a7a-194">В следующем примере используется команда `docker stop` для остановки контейнера, а затем — команда `docker ps` для подтверждения того, что контейнеры не запущены:</span><span class="sxs-lookup"><span data-stu-id="57a7a-194">The following example uses the `docker stop` command to stop the container, and then uses the `docker ps` command to show that no containers are running.</span></span>

```console
> docker stop boring_matsumoto
boring_matsumoto

> docker ps
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS   NAMES
```

### <a name="connect-to-a-container"></a><span data-ttu-id="57a7a-195">Подключение к контейнеру</span><span class="sxs-lookup"><span data-stu-id="57a7a-195">Connect to a container</span></span>

<span data-ttu-id="57a7a-196">После запуска контейнера вы можете подключиться к нему, чтобы просмотреть выходные данные.</span><span class="sxs-lookup"><span data-stu-id="57a7a-196">After a container is running, you can connect to it to see the output.</span></span> <span data-ttu-id="57a7a-197">С помощью команд `docker start` и `docker attach` запустите контейнер и просмотрите поток вывода.</span><span class="sxs-lookup"><span data-stu-id="57a7a-197">Use the `docker start` and `docker attach` commands to start the container and peek at the output stream.</span></span> <span data-ttu-id="57a7a-198">В этом примере команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, используется для отключения от запущенного контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-198">In this example, the <kbd>CTRL + C</kbd> command is used to detach from the running container.</span></span> <span data-ttu-id="57a7a-199">Это может привести к завершению процесса в контейнере и его последующей остановке.</span><span class="sxs-lookup"><span data-stu-id="57a7a-199">This may actually end the process in the container, which will stop the container.</span></span> <span data-ttu-id="57a7a-200">Параметр `--sig-proxy=false` гарантирует, что команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, не остановит процесс в контейнере.</span><span class="sxs-lookup"><span data-stu-id="57a7a-200">The `--sig-proxy=false` parameter ensures that <kbd>CTRL + C</kbd> will not stop the process in the container.</span></span>

<span data-ttu-id="57a7a-201">После отключения от контейнера снова подключитесь к нему, чтобы убедиться в том, что он продолжает работать и считать числа.</span><span class="sxs-lookup"><span data-stu-id="57a7a-201">After you detach from the container, reattach to verify that it's still running and counting.</span></span>

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

### <a name="delete-a-container"></a><span data-ttu-id="57a7a-202">Удаление контейнера</span><span class="sxs-lookup"><span data-stu-id="57a7a-202">Delete a container</span></span>

<span data-ttu-id="57a7a-203">В рамках этого руководства предполагается, что вам не нужны контейнеры, которые запущены, но не выполняют полезные действия.</span><span class="sxs-lookup"><span data-stu-id="57a7a-203">For the purposes of this article you don't want containers just hanging around doing nothing.</span></span> <span data-ttu-id="57a7a-204">Удалите созданный ранее контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-204">Delete the container you previously created.</span></span> <span data-ttu-id="57a7a-205">Если контейнер запущен, остановите его.</span><span class="sxs-lookup"><span data-stu-id="57a7a-205">If the container is running, stop it.</span></span>

```console
> docker stop boring_matsumoto
```

<span data-ttu-id="57a7a-206">В примере ниже выводится список всех контейнеров,</span><span class="sxs-lookup"><span data-stu-id="57a7a-206">The following example lists all containers.</span></span> <span data-ttu-id="57a7a-207">а затем используется команда `docker rm` для удаления контейнера. После этого выполняется повторная проверка наличия запущенных контейнеров.</span><span class="sxs-lookup"><span data-stu-id="57a7a-207">It then uses the `docker rm` command to delete the container, and then checks a second time for any running containers.</span></span>

```console
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS     PORTS   NAMES
0e8f3c2ca32c        myimage             "dotnet app/myapp.dll"   19 minutes ago      Exited             boring_matsumoto

> docker rm boring_matsumoto
boring_matsumoto

> docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS     PORTS    NAMES
```

### <a name="single-run"></a><span data-ttu-id="57a7a-208">Однократный запуск</span><span class="sxs-lookup"><span data-stu-id="57a7a-208">Single run</span></span>

<span data-ttu-id="57a7a-209">Docker предоставляет единую команду `docker run` для создания и запуска контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-209">Docker provides the `docker run` command to create and run the container as a single command.</span></span> <span data-ttu-id="57a7a-210">Она исключает необходимость в поочередном выполнении команд `docker create` и `docker start`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-210">This command eliminates the need to run `docker create` and then `docker start`.</span></span> <span data-ttu-id="57a7a-211">Вы также можете настроить ее для автоматического удаления контейнера при его остановке.</span><span class="sxs-lookup"><span data-stu-id="57a7a-211">You can also set this command to automatically delete the container when the container stops.</span></span> <span data-ttu-id="57a7a-212">Например, команда `docker run -it --rm` выполняет две операции. Сначала она автоматически подключается к контейнеру с помощью текущего терминала, а потом, после завершения работы контейнера, удаляет его:</span><span class="sxs-lookup"><span data-stu-id="57a7a-212">For example, use `docker run -it --rm` to do two things, first, automatically use the current terminal to connect to the container, and then when the container finishes, remove it:</span></span>

```
> docker run -it --rm myimage
Counter: 1
Counter: 2
Counter: 3
Counter: 4
Counter: 5
^C
```

<span data-ttu-id="57a7a-213">Во время выполнения `docker run -it` команда, вызываемая нажатием клавиш <kbd>CTRL+C</kbd>, остановит процесс, запущенный в контейнере. А это в свою очередь приведет к остановке контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-213">With `docker run -it`, the <kbd>CTRL + C</kbd> command will stop process that is running in the container, which in turn, stops the container.</span></span> <span data-ttu-id="57a7a-214">Так как в команде указан параметр `--rm`, контейнер автоматически удалится после остановки процесса.</span><span class="sxs-lookup"><span data-stu-id="57a7a-214">Since the `--rm` parameter was provided, the container is automatically deleted when the process is stopped.</span></span> <span data-ttu-id="57a7a-215">Убедитесь, что он больше не существует:</span><span class="sxs-lookup"><span data-stu-id="57a7a-215">Verify that it does not exist:</span></span>

```
> docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS    PORTS   NAMES
```

### <a name="change-the-entrypoint"></a><span data-ttu-id="57a7a-216">Изменение команды ENTRYPOINT</span><span class="sxs-lookup"><span data-stu-id="57a7a-216">Change the ENTRYPOINT</span></span>

<span data-ttu-id="57a7a-217">Команда `docker run` также позволяет изменить команду `ENTRYPOINT` из файла *Dockerfile* для запуска другой программы, но только для соответствующего контейнера.</span><span class="sxs-lookup"><span data-stu-id="57a7a-217">The `docker run` command also lets you modify the `ENTRYPOINT` command from the *Dockerfile* and run something else, but only for that container.</span></span> <span data-ttu-id="57a7a-218">Например, воспользуйтесь указанной ниже командой, чтобы запустить `bash` или `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-218">For example, use the following command to run `bash` or `cmd.exe`.</span></span> <span data-ttu-id="57a7a-219">При необходимости измените команду.</span><span class="sxs-lookup"><span data-stu-id="57a7a-219">Edit the command as necessary.</span></span>

#### <a name="windows"></a><span data-ttu-id="57a7a-220">Windows</span><span class="sxs-lookup"><span data-stu-id="57a7a-220">Windows</span></span>
<span data-ttu-id="57a7a-221">В этом примере команда `ENTRYPOINT` изменена для запуска `cmd.exe`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-221">In this example the `ENTRYPOINT` is changed to `cmd.exe`.</span></span> <span data-ttu-id="57a7a-222">Нажав клавиши <kbd>CTRL+C</kbd>, вы можете завершить процесс и остановить контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-222"><kbd>CTRL + C</kbd> is pressed to end the process and stop the container.</span></span>

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

#### <a name="linux"></a><span data-ttu-id="57a7a-223">Linux</span><span class="sxs-lookup"><span data-stu-id="57a7a-223">Linux</span></span>

<span data-ttu-id="57a7a-224">В этом примере команда `ENTRYPOINT` изменена для запуска `bash`.</span><span class="sxs-lookup"><span data-stu-id="57a7a-224">In this example the `ENTRYPOINT` is changed to `bash`.</span></span> <span data-ttu-id="57a7a-225">Команда `quit` позволяет завершить процесс и остановить контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-225">The `quit` command is run which ends the process and stop the container.</span></span>

```bash
root@user:~# docker run -it --rm --entrypoint "bash" myimage
root@8515e897c893:/# ls app
myapp.deps.json  myapp.dll  myapp.pdb  myapp.runtimeconfig.json
root@8515e897c893:/# exit
exit
```

## <a name="essential-commands"></a><span data-ttu-id="57a7a-226">Основные команды</span><span class="sxs-lookup"><span data-stu-id="57a7a-226">Essential commands</span></span>

<span data-ttu-id="57a7a-227">Docker предоставляет множество команд для операций с контейнером и образами.</span><span class="sxs-lookup"><span data-stu-id="57a7a-227">Docker has many different commands that cover what you want to do with your container and images.</span></span> <span data-ttu-id="57a7a-228">Для управления контейнерами в основном используются такие команды Docker:</span><span class="sxs-lookup"><span data-stu-id="57a7a-228">These Docker commands are essential to managing your containers:</span></span>

* [<span data-ttu-id="57a7a-229">docker build</span><span class="sxs-lookup"><span data-stu-id="57a7a-229">docker build</span></span>](https://docs.docker.com/engine/reference/commandline/build/)
* [<span data-ttu-id="57a7a-230">docker run</span><span class="sxs-lookup"><span data-stu-id="57a7a-230">docker run</span></span>](https://docs.docker.com/engine/reference/commandline/run/)
* [<span data-ttu-id="57a7a-231">docker ps</span><span class="sxs-lookup"><span data-stu-id="57a7a-231">docker ps</span></span>](https://docs.docker.com/engine/reference/commandline/ps/)
* [<span data-ttu-id="57a7a-232">docker stop</span><span class="sxs-lookup"><span data-stu-id="57a7a-232">docker stop</span></span>](https://docs.docker.com/engine/reference/commandline/stop/)
* [<span data-ttu-id="57a7a-233">docker rm</span><span class="sxs-lookup"><span data-stu-id="57a7a-233">docker rm</span></span>](https://docs.docker.com/engine/reference/commandline/rm/)
* [<span data-ttu-id="57a7a-234">docker rmi</span><span class="sxs-lookup"><span data-stu-id="57a7a-234">docker rmi</span></span>](https://docs.docker.com/engine/reference/commandline/rmi/)
* [<span data-ttu-id="57a7a-235">docker image</span><span class="sxs-lookup"><span data-stu-id="57a7a-235">docker image</span></span>](https://docs.docker.com/engine/reference/commandline/image/)

## <a name="clean-up-resources"></a><span data-ttu-id="57a7a-236">Очистка ресурсов</span><span class="sxs-lookup"><span data-stu-id="57a7a-236">Clean up resources</span></span>

<span data-ttu-id="57a7a-237">В этом руководстве описано, как создать контейнеры и образы.</span><span class="sxs-lookup"><span data-stu-id="57a7a-237">During this tutorial you created containers and images.</span></span> <span data-ttu-id="57a7a-238">При желании эти ресурсы можно удалить.</span><span class="sxs-lookup"><span data-stu-id="57a7a-238">If you want, delete these resources.</span></span> <span data-ttu-id="57a7a-239">Ниже представлены команды, которые позволяют сделать следующее:</span><span class="sxs-lookup"><span data-stu-id="57a7a-239">Use the following commands to</span></span>

01. <span data-ttu-id="57a7a-240">Вывести список всех контейнеров.</span><span class="sxs-lookup"><span data-stu-id="57a7a-240">List all containers</span></span>

    ```console
    > docker ps -a
    ```

02. <span data-ttu-id="57a7a-241">Остановить запущенные контейнеры.</span><span class="sxs-lookup"><span data-stu-id="57a7a-241">Stop containers that are running.</span></span> <span data-ttu-id="57a7a-242">`CONTAINER_NAME` представляет имя, автоматически назначаемое контейнеру.</span><span class="sxs-lookup"><span data-stu-id="57a7a-242">The `CONTAINER_NAME` represents the name automatically assigned to the container.</span></span>

    ```console
    > docker stop CONTAINER_NAME
    ```

03. <span data-ttu-id="57a7a-243">Удалить контейнер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-243">Delete the container</span></span>

    ```console
    > docker rm CONTAINER_NAME
    ```

<span data-ttu-id="57a7a-244">Затем удалите все ненужные образы на компьютере.</span><span class="sxs-lookup"><span data-stu-id="57a7a-244">Next, delete any images that you no longer want on your machine.</span></span> <span data-ttu-id="57a7a-245">Удалите образ, созданный с помощью файла *Dockerfile*, а затем удалите образ .NET Core, на основе которого был создан файл *Dockerfile*.</span><span class="sxs-lookup"><span data-stu-id="57a7a-245">Delete the image created by your *Dockerfile* and then delete the .NET Core image the *Dockerfile* was based on.</span></span> <span data-ttu-id="57a7a-246">Вы можете использовать значение **IMAGE ID** или строку в формате **РЕПОЗИТОРИЙ:МЕТКА**.</span><span class="sxs-lookup"><span data-stu-id="57a7a-246">You can use the **IMAGE ID** or the **REPOSITORY:TAG** formatted string.</span></span>

```console
docker rmi myimage:latest
docker rmi mcr.microsoft.com/dotnet/core/runtime:2.2
```

<span data-ttu-id="57a7a-247">С помощью команды `docker images` просмотрите список установленных образов.</span><span class="sxs-lookup"><span data-stu-id="57a7a-247">Use the `docker images` command to see a list of images installed.</span></span>

> [!NOTE]
> <span data-ttu-id="57a7a-248">Файлы образов могут иметь большой размер.</span><span class="sxs-lookup"><span data-stu-id="57a7a-248">Image files can be large.</span></span> <span data-ttu-id="57a7a-249">Как правило, удаляются временные контейнеры, созданные в ходе тестирования и разработки приложения.</span><span class="sxs-lookup"><span data-stu-id="57a7a-249">Typically, you would remove temporary containers you created while testing and developing your app.</span></span> <span data-ttu-id="57a7a-250">При этом рекомендуется оставить базовые образы с установленной средой выполнения, если на ее основе вы планируете создавать другие образы.</span><span class="sxs-lookup"><span data-stu-id="57a7a-250">You usually keep the base images with the runtime installed if you plan on building other images based on that runtime.</span></span>

## <a name="next-steps"></a><span data-ttu-id="57a7a-251">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="57a7a-251">Next steps</span></span>

* [<span data-ttu-id="57a7a-252">Изучите руководство по микрослужбам ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="57a7a-252">Try the ASP.NET Core Microservice Tutorial.</span></span>](https://dotnet.microsoft.com/learn/web/aspnet-microservice-tutorial/intro)
* [<span data-ttu-id="57a7a-253">Узнайте больше о службах Azure, которые поддерживают контейнеры.</span><span class="sxs-lookup"><span data-stu-id="57a7a-253">Review the Azure services that support containers.</span></span>](https://azure.microsoft.com/en-us/overview/containers/)
* [<span data-ttu-id="57a7a-254">Ознакомьтесь с командами Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="57a7a-254">Read about Dockerfile commands.</span></span>](https://docs.docker.com/engine/reference/builder/)
* [<span data-ttu-id="57a7a-255">Изучите инструменты Visual Studio для контейнеров</span><span class="sxs-lookup"><span data-stu-id="57a7a-255">Explore the Container Tools for Visual Studio</span></span>](/visualstudio/containers/overview)