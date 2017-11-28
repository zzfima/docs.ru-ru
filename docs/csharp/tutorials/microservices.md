---
title: "Микрослужбы, размещенные в Docker. Язык C#"
description: "Узнайте, как создать службы ASP.NET Core, выполняемые в контейнерах Docker"
keywords: ".NET, .NET Core, Docker, C#, ASP.NET, микрослужба"
author: BillWagner
ms.author: wiwagn
ms.date: 02/03/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-docker
ms.devlang: csharp
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 6cdc4eb0d0fea93b5210532210ad0c928e35a7a5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="c2b94-104">Микрослужбы, размещенные в Docker</span><span class="sxs-lookup"><span data-stu-id="c2b94-104">Microservices hosted in Docker</span></span>

## <a name="introduction"></a><span data-ttu-id="c2b94-105">Вступление</span><span class="sxs-lookup"><span data-stu-id="c2b94-105">Introduction</span></span>

<span data-ttu-id="c2b94-106">В этом руководстве описан процесс построения и развертывания микрослужбы ASP.NET Core в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-106">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="c2b94-107">В ходе работы с этим руководством вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="c2b94-107">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="c2b94-108">как создать приложение ASP.NET Core с помощью Yeoman;</span><span class="sxs-lookup"><span data-stu-id="c2b94-108">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="c2b94-109">как создать среду разработки Docker;</span><span class="sxs-lookup"><span data-stu-id="c2b94-109">How to create a development Docker environment</span></span>
* <span data-ttu-id="c2b94-110">как создать образ Docker на основе существующего образа;</span><span class="sxs-lookup"><span data-stu-id="c2b94-110">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="c2b94-111">как развертывать службы в контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-111">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="c2b94-112">Одновременно с этим вы увидите примеры использования некоторых возможностей языка C#:</span><span class="sxs-lookup"><span data-stu-id="c2b94-112">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="c2b94-113">как преобразовать объекты C# в полезные данные JSON;</span><span class="sxs-lookup"><span data-stu-id="c2b94-113">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="c2b94-114">как создать неизменяемые объекты передачи данных;</span><span class="sxs-lookup"><span data-stu-id="c2b94-114">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="c2b94-115">как обрабатывать входящие запросы HTTP и формировать HTTP-ответы;</span><span class="sxs-lookup"><span data-stu-id="c2b94-115">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="c2b94-116">как использовать типы значений, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="c2b94-116">How to work with nullable value types</span></span>

<span data-ttu-id="c2b94-117">Вы можете [просмотреть или скачать пример приложения](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c2b94-117">You can [view or download the sample app](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="c2b94-118">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="c2b94-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="c2b94-119">Преимущества Docker</span><span class="sxs-lookup"><span data-stu-id="c2b94-119">Why Docker?</span></span>

<span data-ttu-id="c2b94-120">Docker позволяет легко создавать стандартные образы виртуальной машины для размещения служб в центре обработки данных или в общедоступном облаке.</span><span class="sxs-lookup"><span data-stu-id="c2b94-120">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="c2b94-121">Docker позволяет настраивать образ и реплицировать его по мере необходимости для масштабирования приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-121">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="c2b94-122">Весь код, представленный в этом руководстве, будет работать в любой среде .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-122">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="c2b94-123">Дополнительные задачи по установке Docker совместимы с приложением ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-123">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="c2b94-124">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c2b94-124">Prerequisites</span></span>
<span data-ttu-id="c2b94-125">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-125">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="c2b94-126">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="c2b94-126">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="c2b94-127">Это приложение можно запустить в ОС Windows, Ubuntu Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-127">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="c2b94-128">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="c2b94-128">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="c2b94-129">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="c2b94-129">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="c2b94-130">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="c2b94-130">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="c2b94-131">Также необходимо установить подсистему Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-131">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="c2b94-132">На [странице установки Docker](http://www.docker.com/products/docker) вы найдете инструкции для вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="c2b94-132">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="c2b94-133">Docker можно установить на многих дистрибутивах Linux, macOS или Windows.</span><span class="sxs-lookup"><span data-stu-id="c2b94-133">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="c2b94-134">Указанная выше страница содержит разделы для каждой из доступных установок.</span><span class="sxs-lookup"><span data-stu-id="c2b94-134">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="c2b94-135">Установка основной части компонентов выполняется диспетчером пакетов.</span><span class="sxs-lookup"><span data-stu-id="c2b94-135">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="c2b94-136">Если у вас установлен диспетчер пакетов node.js `npm`, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="c2b94-136">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="c2b94-137">В противном случае установите последнюю версию NodeJs с сайта [nodejs.org](https://nodejs.org), которая содержит диспетчер пакетов npm.</span><span class="sxs-lookup"><span data-stu-id="c2b94-137">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="c2b94-138">На этом этапе нужно установить несколько средств командной строки, поддерживающих разработку для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-138">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="c2b94-139">Шаблоны командной строки используют Yeoman, Bower, Grunt и Gulp.</span><span class="sxs-lookup"><span data-stu-id="c2b94-139">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="c2b94-140">Возможно, они у вас уже установлены. Если же нет, введите следующий текст в любой оболочке командной строки:</span><span class="sxs-lookup"><span data-stu-id="c2b94-140">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="c2b94-141">Параметр `-g` указывает, что установка выполняется глобально, то есть эти средства будут доступны во всей системе.</span><span class="sxs-lookup"><span data-stu-id="c2b94-141">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="c2b94-142">(При локальной установке пакеты будут доступны только в одном проекте.)</span><span class="sxs-lookup"><span data-stu-id="c2b94-142">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="c2b94-143">Когда вы закончите установку этих средств, установите еще и генераторы шаблонов yeoman asp.net:</span><span class="sxs-lookup"><span data-stu-id="c2b94-143">Once you've installed those core tools, you need to install the yeoman asp.net template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="c2b94-144">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="c2b94-144">Create the Application</span></span>

<span data-ttu-id="c2b94-145">Теперь, когда вы установили все нужные средства, создайте новое приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-145">Now that you've installed all the tools, create a new asp.net core application.</span></span> <span data-ttu-id="c2b94-146">Чтобы использовать генератор из командной строки, выполните следующую команду yeoman в любой оболочке:</span><span class="sxs-lookup"><span data-stu-id="c2b94-146">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="c2b94-147">Эта команда предложит выбрать тип создаваемого приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-147">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="c2b94-148">Для нашего примера микрослужбы выберите самый простой и самый легкий вариант веб-приложения: "Пустое веб-приложение".</span><span class="sxs-lookup"><span data-stu-id="c2b94-148">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="c2b94-149">Шаблон предложит ввести для него имя.</span><span class="sxs-lookup"><span data-stu-id="c2b94-149">The template will prompt you for a name.</span></span> <span data-ttu-id="c2b94-150">Введите строку WeatherMicroservice.</span><span class="sxs-lookup"><span data-stu-id="c2b94-150">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="c2b94-151">Шаблон создает восемь файлов.</span><span class="sxs-lookup"><span data-stu-id="c2b94-151">The template creates eight files for you:</span></span>

* <span data-ttu-id="c2b94-152">Файл .gitignore, настроенный для приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-152">A .gitignore, customized for asp.net core applications.</span></span>
* <span data-ttu-id="c2b94-153">Файл Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="c2b94-153">A Startup.cs file.</span></span> <span data-ttu-id="c2b94-154">Этот файл содержит основу для приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-154">This contains the basis of the application.</span></span>
* <span data-ttu-id="c2b94-155">Файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="c2b94-155">A Program.cs file.</span></span> <span data-ttu-id="c2b94-156">Этот файл содержит точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-156">This contains the entry point of the application.</span></span>
* <span data-ttu-id="c2b94-157">Файл WeatherMicroservice.csproj.</span><span class="sxs-lookup"><span data-stu-id="c2b94-157">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="c2b94-158">Это файл сборки для нашего приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-158">This is the build file for the application.</span></span>
* <span data-ttu-id="c2b94-159">Файл Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="c2b94-159">A Dockerfile.</span></span> <span data-ttu-id="c2b94-160">Это скрипт, который создает образ Docker для приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-160">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="c2b94-161">Файл README.md.</span><span class="sxs-lookup"><span data-stu-id="c2b94-161">A README.md.</span></span> <span data-ttu-id="c2b94-162">Этот файл содержит ссылки на другие ресурсы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-162">This contains links to other asp.net core resources.</span></span>
* <span data-ttu-id="c2b94-163">Файл web.config.</span><span class="sxs-lookup"><span data-stu-id="c2b94-163">A web.config file.</span></span> <span data-ttu-id="c2b94-164">Этот файл содержит информацию о базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c2b94-164">This contains basic configuration information.</span></span>
* <span data-ttu-id="c2b94-165">Файл runtimeconfig.template.json.</span><span class="sxs-lookup"><span data-stu-id="c2b94-165">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="c2b94-166">Этот файл содержит параметры отладки, используемые интегрированными средами разработки.</span><span class="sxs-lookup"><span data-stu-id="c2b94-166">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="c2b94-167">Теперь можно запустить приложение, созданное на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="c2b94-167">Now you can run the template generated application.</span></span> <span data-ttu-id="c2b94-168">В этом вам помогут несколько средств командной строки.</span><span class="sxs-lookup"><span data-stu-id="c2b94-168">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="c2b94-169">Команда `dotnet` запускает средства, необходимые для разработки в среде .NET.</span><span class="sxs-lookup"><span data-stu-id="c2b94-169">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="c2b94-170">Каждая команда соответствует определенному средству.</span><span class="sxs-lookup"><span data-stu-id="c2b94-170">Each verb executes a different command</span></span>

<span data-ttu-id="c2b94-171">Сначала нужно восстановить все зависимости:</span><span class="sxs-lookup"><span data-stu-id="c2b94-171">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="c2b94-172">Команда dotnet restore устанавливает все необходимые пакеты в каталог приложения с помощью диспетчера пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-172">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="c2b94-173">Она также создает файл project.json.lock.</span><span class="sxs-lookup"><span data-stu-id="c2b94-173">It also generates a project.json.lock file.</span></span> <span data-ttu-id="c2b94-174">Этот файл содержит сведения о каждом пакета, на который имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="c2b94-174">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="c2b94-175">После восстановления всех зависимостей выполните сборку приложения:</span><span class="sxs-lookup"><span data-stu-id="c2b94-175">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c2b94-176">Когда сборка завершится, приложение можно запустить из командной строки:</span><span class="sxs-lookup"><span data-stu-id="c2b94-176">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="c2b94-177">В конфигурации по умолчанию приложение прослушивает адрес http://localhost: 5000.</span><span class="sxs-lookup"><span data-stu-id="c2b94-177">The default configuration listens to http://localhost:5000.</span></span> <span data-ttu-id="c2b94-178">Откройте браузер и перейдите на эту страницу. Вы должны увидеть приветствие Hello World</span><span class="sxs-lookup"><span data-stu-id="c2b94-178">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="c2b94-179">!".</span><span class="sxs-lookup"><span data-stu-id="c2b94-179">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="c2b94-180">Анатомия приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c2b94-180">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="c2b94-181">Теперь у вас есть готовое приложение. Давайте на его примере рассмотрим реализацию функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="c2b94-181">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="c2b94-182">Из созданных файлов приложения нам пока наиболее интересны вот эти два: project.json и Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="c2b94-182">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="c2b94-183">Project.json содержит сведения о проекте.</span><span class="sxs-lookup"><span data-stu-id="c2b94-183">Project.json contains information about the project.</span></span> <span data-ttu-id="c2b94-184">Вы будете часто иметь дело с двумя узлами: dependencies (зависимости) и frameworks (платформы).</span><span class="sxs-lookup"><span data-stu-id="c2b94-184">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="c2b94-185">Узел зависимостей перечисляет все пакеты, которые необходимы для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-185">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="c2b94-186">Пока наш узел совсем мал, и ему требуются только те пакеты, которые обязательны для работы веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="c2b94-186">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="c2b94-187">Узел платформ описывает версии и конфигурации платформы .NET framework, на которых будет выполняться это приложение.</span><span class="sxs-lookup"><span data-stu-id="c2b94-187">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="c2b94-188">Само приложение реализовано в файле Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="c2b94-188">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="c2b94-189">Этот файл содержит класс Startup.</span><span class="sxs-lookup"><span data-stu-id="c2b94-189">This file contains the startup class.</span></span>

<span data-ttu-id="c2b94-190">Инфраструктура ASP.NET Core вызывает два метода этого класса для настройки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-190">The two methods are called by the asp.net core infrastructure to configure and run the application.</span></span> <span data-ttu-id="c2b94-191">Метод `ConfigureServices` описывает службы, которые необходимы для приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-191">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="c2b94-192">Наша служба не использует никакие ресурсы, и для нее не нужны никакие зависимости.</span><span class="sxs-lookup"><span data-stu-id="c2b94-192">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="c2b94-193">Метод `Configure` настраивает обработчики для входящих HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="c2b94-193">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="c2b94-194">Шаблон создает простой обработчик, который в ответ на любой запрос возвращает текст "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="c2b94-194">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="c2b94-195">Сборка микрослужбы</span><span class="sxs-lookup"><span data-stu-id="c2b94-195">Build a microservice</span></span>

<span data-ttu-id="c2b94-196">Служба, которую вы разрабатываете, будет доставлять сведения о погоде в любой точке земного шара.</span><span class="sxs-lookup"><span data-stu-id="c2b94-196">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="c2b94-197">В рабочем приложении вы будете обращаться к реальным службам для получения данных о погоде.</span><span class="sxs-lookup"><span data-stu-id="c2b94-197">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="c2b94-198">Но для этого примера нам достаточно создать случайный прогноз погоды.</span><span class="sxs-lookup"><span data-stu-id="c2b94-198">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="c2b94-199">Чтобы получить его, мы выполним несколько задач:</span><span class="sxs-lookup"><span data-stu-id="c2b94-199">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="c2b94-200">синтаксический анализ входящего запроса для получения широты и долготы;</span><span class="sxs-lookup"><span data-stu-id="c2b94-200">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="c2b94-201">создание случайных данных для прогноза;</span><span class="sxs-lookup"><span data-stu-id="c2b94-201">Generate some random forecast data.</span></span>
* <span data-ttu-id="c2b94-202">преобразование случайных данных прогноза из объектов C# в пакеты JSON;</span><span class="sxs-lookup"><span data-stu-id="c2b94-202">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="c2b94-203">установка заголовка ответа, который будет обозначать отправку данных в формате JSON;</span><span class="sxs-lookup"><span data-stu-id="c2b94-203">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="c2b94-204">создание текста ответа.</span><span class="sxs-lookup"><span data-stu-id="c2b94-204">Write the response.</span></span>

<span data-ttu-id="c2b94-205">В следующем разделе описаны шаги для выполнения каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="c2b94-205">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="c2b94-206">Синтаксический анализ входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="c2b94-206">Parsing the Query String.</span></span>

<span data-ttu-id="c2b94-207">Прежде всего нужно выполнить синтаксический анализ строки запроса.</span><span class="sxs-lookup"><span data-stu-id="c2b94-207">You'll begin by parsing the query string.</span></span> <span data-ttu-id="c2b94-208">Служба будет принимать в строке запроса аргументы lat и long в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="c2b94-208">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="c2b94-209">Все изменения, которые нужно выполнить, относятся к лямбда-выражению, которое определено в классе запуска в качестве аргумента для метода `app.Run`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-209">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="c2b94-210">В лямбда-выражении нас интересует аргумент `HttpContext`, представляющий запрос.</span><span class="sxs-lookup"><span data-stu-id="c2b94-210">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="c2b94-211">Одним из его свойств является объект `Request`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-211">One of its properties is the `Request` object.</span></span> <span data-ttu-id="c2b94-212">Объект `Request` имеет свойство `Query`, которое содержит словарь всех значений, переданных в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="c2b94-212">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="c2b94-213">Сначала добавьте строки для поиска значений широты и долготы:</span><span class="sxs-lookup"><span data-stu-id="c2b94-213">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="c2b94-214">Значения в словаре запроса имеют тип `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-214">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="c2b94-215">Этот тип может содержать коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="c2b94-215">That type can contain a collection of strings.</span></span> <span data-ttu-id="c2b94-216">Для нашей службы погоды каждое значение должно содержать одну строку.</span><span class="sxs-lookup"><span data-stu-id="c2b94-216">For your weather service, each value is a single string.</span></span> <span data-ttu-id="c2b94-217">Поэтому в приведенном выше коде мы вызываем метод `FirstOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-217">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="c2b94-218">Теперь нам нужно преобразовать эти строки в тип Double.</span><span class="sxs-lookup"><span data-stu-id="c2b94-218">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="c2b94-219">Для преобразования строки в значение типа double мы используем метод `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="c2b94-219">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="c2b94-220">Этот метод использует параметры вывода C#, чтобы определить возможность преобразования входной строки к типу double.</span><span class="sxs-lookup"><span data-stu-id="c2b94-220">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="c2b94-221">Если строка содержит допустимое представление для типа double, метод возвращает значение true, а аргумент `result` содержит преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="c2b94-221">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="c2b94-222">Если строка не представляет допустимого представления для типа double, метод возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="c2b94-222">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="c2b94-223">Этот API можно дополнить *методом расширения*, который возвращает *тип double, допускающий значение NULL*.</span><span class="sxs-lookup"><span data-stu-id="c2b94-223">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="c2b94-224">*Тип, допускающий значение NULL*, может содержать значения некоторого типа или значение NULL, которое обозначает отсутствие значения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-224">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="c2b94-225">Чтобы использовать тип, допускающий значения NULL, добавьте к объявлению типа символ `?`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-225">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="c2b94-226">Методы расширения представляют собой методы, которые определяются как обычные статические методы, но с модификатором `this` для первого параметра. Такие методы можно вызывать так, как будто они являются членами этого класса.</span><span class="sxs-lookup"><span data-stu-id="c2b94-226">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="c2b94-227">Методы расширения можно определять только в статических классах.</span><span class="sxs-lookup"><span data-stu-id="c2b94-227">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="c2b94-228">Вот пример определения класса с методом расширения для синтаксического анализа:</span><span class="sxs-lookup"><span data-stu-id="c2b94-228">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="c2b94-229">Выражение `default(double?)` возвращает значение по умолчанию для типа `double?`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-229">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="c2b94-230">По умолчанию значение для него отсутствует (возвращается NULL).</span><span class="sxs-lookup"><span data-stu-id="c2b94-230">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="c2b94-231">Этот метод расширения можно использовать для преобразования аргументов строки запроса в тип double:</span><span class="sxs-lookup"><span data-stu-id="c2b94-231">You can use this extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="c2b94-232">Чтобы быстро проверить работу кода для синтаксического анализа, включите значения аргументов в возвращаемый ответ:</span><span class="sxs-lookup"><span data-stu-id="c2b94-232">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="c2b94-233">На этом этапе можно запустить веб-приложение и убедиться, работает ли код для синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="c2b94-233">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="c2b94-234">В строке запроса браузера добавьте какие-либо значения, обновите страницу и убедитесь, что они правильно возвращаются.</span><span class="sxs-lookup"><span data-stu-id="c2b94-234">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="c2b94-235">Создание случайного прогноза погоды</span><span class="sxs-lookup"><span data-stu-id="c2b94-235">Build a random weather forecast</span></span>

<span data-ttu-id="c2b94-236">Теперь мы переходим к созданию случайного прогноза погоды.</span><span class="sxs-lookup"><span data-stu-id="c2b94-236">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="c2b94-237">Для этого нам в первую очередь нужен контейнер, который содержит значения для прогноза погоды:</span><span class="sxs-lookup"><span data-stu-id="c2b94-237">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions = new string[]
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HiTemperature { get; }
    public int LoTemperature { get; }
    public int AverageWindSpeed { get; }
    public string Conditions { get; }
}
```

<span data-ttu-id="c2b94-238">Теперь создайте конструктор, который задает эти значения случайным образом.</span><span class="sxs-lookup"><span data-stu-id="c2b94-238">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="c2b94-239">Этот конструктор использует значения широты и долготы в качестве начального значения для генератора случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="c2b94-239">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="c2b94-240">Это означает, что для каждого набора координат всегда будет возвращаться одинаковый прогноз.</span><span class="sxs-lookup"><span data-stu-id="c2b94-240">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="c2b94-241">Если вы измените значения для аргументов широты и долготы, вы получите другой прогноз (поскольку начальное значение для генератора случайных чисел будет другим).</span><span class="sxs-lookup"><span data-stu-id="c2b94-241">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="c2b94-242">Создайте в методе ответа прогноз на 5 дней:</span><span class="sxs-lookup"><span data-stu-id="c2b94-242">You can now generate the 5-day forecast in your response method:</span></span>

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a><span data-ttu-id="c2b94-243">Оформление ответа в формате JSON</span><span class="sxs-lookup"><span data-stu-id="c2b94-243">Build the JSON response.</span></span>

<span data-ttu-id="c2b94-244">Последней задачей, которую выполняет код на сервере, будет преобразование массива WeatherReport в пакет JSON и отправка этого пакета клиенту.</span><span class="sxs-lookup"><span data-stu-id="c2b94-244">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="c2b94-245">Здесь нам нужно сначала создать пакет JSON.</span><span class="sxs-lookup"><span data-stu-id="c2b94-245">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="c2b94-246">В список зависимостей добавьте сериализатор NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="c2b94-246">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="c2b94-247">Для этого можно использовать команду `dotnet` CLI:</span><span class="sxs-lookup"><span data-stu-id="c2b94-247">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="c2b94-248">Теперь примените класс `JsonConvert`, чтобы преобразовать наш объект в строку:</span><span class="sxs-lookup"><span data-stu-id="c2b94-248">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="c2b94-249">Приведенный выше код преобразует объект прогноза (список объектов `WeatherForecast`) в пакет JSON.</span><span class="sxs-lookup"><span data-stu-id="c2b94-249">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="c2b94-250">Когда пакет с ответом будет готов, укажите для него тип содержимого `application/json` и возвратите строку.</span><span class="sxs-lookup"><span data-stu-id="c2b94-250">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="c2b94-251">Теперь наше приложение создает и возвращает случайные прогнозы погоды.</span><span class="sxs-lookup"><span data-stu-id="c2b94-251">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="c2b94-252">Создание образа Docker</span><span class="sxs-lookup"><span data-stu-id="c2b94-252">Build a Docker image</span></span>

<span data-ttu-id="c2b94-253">Последней задачей в этой статье будет запуск приложения в Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-253">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="c2b94-254">Мы создадим контейнер Docker, который выполняет образ Docker с созданным ранее приложением.</span><span class="sxs-lookup"><span data-stu-id="c2b94-254">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="c2b94-255">Объект ***образа Docker*** — это файл, который определяет среду для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-255">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="c2b94-256">***Контейнер Docker*** представляет запущенный экземпляр образа Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-256">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="c2b94-257">Для упрощения понимания вы можете представить *образ Docker* как *класс*, а *контейнер Docker* — как объект или экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="c2b94-257">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="c2b94-258">Для этой задачи мы применим файл Dockerfile, созданным с помощью шаблона ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c2b94-258">The Dockerfile created by the asp.net template will serve for our purposes.</span></span> <span data-ttu-id="c2b94-259">Давайте изучим его содержимое.</span><span class="sxs-lookup"><span data-stu-id="c2b94-259">Let's go over its contents.</span></span>

<span data-ttu-id="c2b94-260">Первая строка задает исходный образ:</span><span class="sxs-lookup"><span data-stu-id="c2b94-260">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="c2b94-261">Docker позволяет настроить образ компьютера на основе исходного шаблона.</span><span class="sxs-lookup"><span data-stu-id="c2b94-261">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="c2b94-262">Это значит, что при запуске вам не придется указывать все параметры компьютера. Достаточно указать лишь изменения параметров, если они потребуются.</span><span class="sxs-lookup"><span data-stu-id="c2b94-262">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="c2b94-263">Здесь таким изменением станет запуск нашего приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-263">The changes here will be to include our application.</span></span>

<span data-ttu-id="c2b94-264">В первом примере мы будем использовать версию `1.1-sdk-msbuild` образа dotnet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-264">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="c2b94-265">Это самый простой способ создать рабочую среду Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-265">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="c2b94-266">Этот образ включает базовую среду выполнения DotNet и пакет SDK DotNet.</span><span class="sxs-lookup"><span data-stu-id="c2b94-266">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="c2b94-267">Это позволяет быстрее начать разработку и сборку, но увеличивает размер образа.</span><span class="sxs-lookup"><span data-stu-id="c2b94-267">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="c2b94-268">Следующие пять строк выполняют настройку и сборку приложения:</span><span class="sxs-lookup"><span data-stu-id="c2b94-268">The next five lines setup and build your application:</span></span>

```
WORKDIR /app

# copy csproj and restore as distinct layers

COPY WeatherMicroservice.csproj .
RUN dotnet restore 

# copy and build everything else

COPY . .

# RUN dotnet restore
RUN dotnet publish -c Release -o out
```

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="c2b94-269">Здесь файл проекта копируется из текущего каталога на виртуальную машину Docker, а также восстанавливаются все пакеты.</span><span class="sxs-lookup"><span data-stu-id="c2b94-269">This will copy the project file from the  current directory to the docker VM, and restore all the packages.</span></span> <span data-ttu-id="c2b94-270">Мы используем Dotnet CLI, а значит образ Docker должен включать пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c2b94-270">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="c2b94-271">После этого копируется остальная часть приложения, а команда dotnet publish выполняет сборку и упаковку приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-271">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="c2b94-272">Последняя строка этого файла запускает наше приложение:</span><span class="sxs-lookup"><span data-stu-id="c2b94-272">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="c2b94-273">Настроенный здесь порт используется в аргументе `--server.urls` команды `dotnet`, которая находится в последней строке файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="c2b94-273">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="c2b94-274">Команда `ENTRYPOINT` сообщает Docker, какие команды и параметры командной строки нужно использовать для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="c2b94-274">The `ENTRYPOINT` command informs Docker  what command and command line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="c2b94-275">Сборка и выполнение образа в контейнере.</span><span class="sxs-lookup"><span data-stu-id="c2b94-275">Building and running the image in a container.</span></span>

<span data-ttu-id="c2b94-276">Теперь мы создадим образ и запустим службу в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="c2b94-276">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="c2b94-277">Вам не нужно, чтобы в образ копировались все файлы из локального каталога.</span><span class="sxs-lookup"><span data-stu-id="c2b94-277">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="c2b94-278">Поэтому приложение следует собирать в контейнере.</span><span class="sxs-lookup"><span data-stu-id="c2b94-278">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="c2b94-279">Для этого создайте файл `.dockerignore` и перечислите в нем каталоги, которые не нужно копировать в образ.</span><span class="sxs-lookup"><span data-stu-id="c2b94-279">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="c2b94-280">Например, вам не нужно, чтобы копировались активы сборки.</span><span class="sxs-lookup"><span data-stu-id="c2b94-280">You don't want any of the build assets copied.</span></span> <span data-ttu-id="c2b94-281">Укажите каталоги для сборки и публикации в файле `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="c2b94-281">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="c2b94-282">Для сборки образа используется команда docker build.</span><span class="sxs-lookup"><span data-stu-id="c2b94-282">You build the image using the docker build command.</span></span> <span data-ttu-id="c2b94-283">Выполните следующую команду из каталога, содержащего код приложения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-283">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="c2b94-284">Эта команда собирает контейнер изображения, используя информацию из файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="c2b94-284">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="c2b94-285">Аргумент `-t` содержит тег (имя) для создаваемого образа контейнера.</span><span class="sxs-lookup"><span data-stu-id="c2b94-285">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="c2b94-286">В приведенной выше командной строке для контейнера Docker указан тег `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-286">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="c2b94-287">Когда завершится выполнение этой команды, у вас будет готовый контейнер для запуска новой службы.</span><span class="sxs-lookup"><span data-stu-id="c2b94-287">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="c2b94-288">Выполните следующую команду, чтобы запустить созданный контейнер и соответствующую службу:</span><span class="sxs-lookup"><span data-stu-id="c2b94-288">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="c2b94-289">Параметр `-d` указывает, что контейнер следует отсоединить от текущего терминала.</span><span class="sxs-lookup"><span data-stu-id="c2b94-289">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="c2b94-290">Это означает, что вы не увидите выходные данные команды в окне терминала.</span><span class="sxs-lookup"><span data-stu-id="c2b94-290">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="c2b94-291">Параметр `-p` настраивает сопоставление портов между службой и узлом.</span><span class="sxs-lookup"><span data-stu-id="c2b94-291">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="c2b94-292">В этом примере все входящие запросы на порт 80 будут перенаправляться на порт контейнера 5000.</span><span class="sxs-lookup"><span data-stu-id="c2b94-292">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="c2b94-293">Значение 5000 совпадает с тем значением параметра командной строки, который мы указали выше в файле Dockerfile. Именно этот порт прослушивает ваша служба.</span><span class="sxs-lookup"><span data-stu-id="c2b94-293">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="c2b94-294">Аргумент `--name` задает имя для выполняемого контейнера.</span><span class="sxs-lookup"><span data-stu-id="c2b94-294">The `--name` argument names your running container.</span></span> <span data-ttu-id="c2b94-295">Здесь вы можете указать любое удобное для вас имя, которое упростит работу с этим контейнером.</span><span class="sxs-lookup"><span data-stu-id="c2b94-295">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="c2b94-296">С помощью следующей команды вы можете проверить, выполняется ли образ:</span><span class="sxs-lookup"><span data-stu-id="c2b94-296">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="c2b94-297">Если контейнер работает, вы увидите строку с его именем в списке запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="c2b94-297">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="c2b94-298">(Возможно, это будет единственная строка в этом списке.)</span><span class="sxs-lookup"><span data-stu-id="c2b94-298">(It may be the only one).</span></span>

<span data-ttu-id="c2b94-299">Вы можете проверить работу вашей службы, открыв локальный адрес localhost в окне браузера и введя значения для широты и долготы:</span><span class="sxs-lookup"><span data-stu-id="c2b94-299">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="c2b94-300">Присоединение к работающему контейнеру</span><span class="sxs-lookup"><span data-stu-id="c2b94-300">Attaching to a running container</span></span>

<span data-ttu-id="c2b94-301">Когда вы запускали службу в командном окне, для каждого запроса вы получали диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="c2b94-301">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="c2b94-302">Теперь, когда контейнер работает в отсоединенном режиме, вы больше не видите эту информацию.</span><span class="sxs-lookup"><span data-stu-id="c2b94-302">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="c2b94-303">Команда Docker attach дает возможность присоединиться к выполняющемуся контейнеру, чтобы просмотреть данные журнала.</span><span class="sxs-lookup"><span data-stu-id="c2b94-303">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="c2b94-304">В окне командной строки выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c2b94-304">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="c2b94-305">Аргумент `--sig-proxy=false` означает, что команды `Ctrl-C` не передаются в процесс контейнера, а просто останавливают выполнение команды `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-305">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="c2b94-306">Последний аргумент обозначает имя, присвоенное контейнеру ранее, при выполнении команды `docker run`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-306">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="c2b94-307">Также для ссылки на любой контейнер вы можете использовать назначенный Docker идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="c2b94-307">You can also use the docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="c2b94-308">Если в команде `docker run` не указано имя контейнера, необходимо использовать идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="c2b94-308">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="c2b94-309">Откройте браузер и перейдите к адресу вашей службы.</span><span class="sxs-lookup"><span data-stu-id="c2b94-309">Open a browser and navigate to your service.</span></span> <span data-ttu-id="c2b94-310">В командном окне вы увидите диагностические сообщения, генерируемые присоединенным контейнером.</span><span class="sxs-lookup"><span data-stu-id="c2b94-310">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="c2b94-311">Чтобы остановить этот процесс, нажмите клавиши `Ctrl-C`.</span><span class="sxs-lookup"><span data-stu-id="c2b94-311">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="c2b94-312">Когда вы завершите работу с контейнером, его можно остановить:</span><span class="sxs-lookup"><span data-stu-id="c2b94-312">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="c2b94-313">При этом контейнер и образ останутся доступны, и их можно запустить заново.</span><span class="sxs-lookup"><span data-stu-id="c2b94-313">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="c2b94-314">Если вы хотите удалить контейнер с компьютера, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c2b94-314">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="c2b94-315">Если вы хотите удалить с компьютера все неиспользуемые контейнеры, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c2b94-315">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="c2b94-316">Заключение</span><span class="sxs-lookup"><span data-stu-id="c2b94-316">Conclusion</span></span> 

<span data-ttu-id="c2b94-317">В этом руководстве вы создали микрослужбу ASP.NET Core и добавили в нее несколько простых функций.</span><span class="sxs-lookup"><span data-stu-id="c2b94-317">In this tutorial, you built an asp.net core microservice, and added a few simple features.</span></span>

<span data-ttu-id="c2b94-318">Вы создали образ контейнера Docker для этой службы и запустили этот образ на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c2b94-318">You built a docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="c2b94-319">Также вы подключили к службе окно терминала и увидели диагностические сообщения от службы.</span><span class="sxs-lookup"><span data-stu-id="c2b94-319">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="c2b94-320">В процессе изучения вы также узнали, как используются некоторые функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="c2b94-320">Along the way, you saw several features of the C# language in action.</span></span>
