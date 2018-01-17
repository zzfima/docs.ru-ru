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
ms.openlocfilehash: d399cdce81350356b71e21d879a4f5b5079f98d8
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2018
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="a448b-104">Микрослужбы, размещенные в Docker</span><span class="sxs-lookup"><span data-stu-id="a448b-104">Microservices hosted in Docker</span></span>

<span data-ttu-id="a448b-105">В этом руководстве описан процесс построения и развертывания микрослужбы ASP.NET Core в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-105">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="a448b-106">В ходе работы с этим руководством вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="a448b-106">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="a448b-107">как создать приложение ASP.NET Core с помощью Yeoman;</span><span class="sxs-lookup"><span data-stu-id="a448b-107">How to generate an ASP.NET Core application using Yeoman</span></span>
* <span data-ttu-id="a448b-108">как создать среду разработки Docker;</span><span class="sxs-lookup"><span data-stu-id="a448b-108">How to create a development Docker environment</span></span>
* <span data-ttu-id="a448b-109">как создать образ Docker на основе существующего образа;</span><span class="sxs-lookup"><span data-stu-id="a448b-109">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="a448b-110">как развертывать службы в контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-110">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="a448b-111">Одновременно с этим вы увидите примеры использования некоторых возможностей языка C#:</span><span class="sxs-lookup"><span data-stu-id="a448b-111">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="a448b-112">как преобразовать объекты C# в полезные данные JSON;</span><span class="sxs-lookup"><span data-stu-id="a448b-112">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="a448b-113">как создать неизменяемые объекты передачи данных;</span><span class="sxs-lookup"><span data-stu-id="a448b-113">How to build immutable Data Transfer Objects</span></span>
* <span data-ttu-id="a448b-114">как обрабатывать входящие запросы HTTP и формировать HTTP-ответы;</span><span class="sxs-lookup"><span data-stu-id="a448b-114">How to process incoming HTTP Requests and generate the HTTP Response</span></span>
* <span data-ttu-id="a448b-115">как использовать типы значений, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="a448b-115">How to work with nullable value types</span></span>

<span data-ttu-id="a448b-116">Вы можете [просмотреть или скачать пример приложения](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a448b-116">You can [view or download the sample app](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="a448b-117">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="a448b-117">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

### <a name="why-docker"></a><span data-ttu-id="a448b-118">Преимущества Docker</span><span class="sxs-lookup"><span data-stu-id="a448b-118">Why Docker?</span></span>

<span data-ttu-id="a448b-119">Docker позволяет легко создавать стандартные образы виртуальной машины для размещения служб в центре обработки данных или в общедоступном облаке.</span><span class="sxs-lookup"><span data-stu-id="a448b-119">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="a448b-120">Docker позволяет настраивать образ и реплицировать его по мере необходимости для масштабирования приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-120">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="a448b-121">Весь код, представленный в этом руководстве, будет работать в любой среде .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-121">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="a448b-122">Дополнительные задачи по установке Docker совместимы с приложением ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-122">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="a448b-123">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="a448b-123">Prerequisites</span></span>
<span data-ttu-id="a448b-124">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-124">You’ll need to setup your machine to run .NET core.</span></span> <span data-ttu-id="a448b-125">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="a448b-125">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="a448b-126">Это приложение можно запустить в ОС Windows, Ubuntu Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-126">You can run this application on Windows, Ubuntu Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="a448b-127">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="a448b-127">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="a448b-128">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="a448b-128">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="a448b-129">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="a448b-129">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="a448b-130">Также необходимо установить подсистему Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-130">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="a448b-131">На [странице установки Docker](http://www.docker.com/products/docker) вы найдете инструкции для вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="a448b-131">See the [Docker Installation page](http://www.docker.com/products/docker) for instructions for your platform.</span></span>
<span data-ttu-id="a448b-132">Docker можно установить на многих дистрибутивах Linux, macOS или Windows.</span><span class="sxs-lookup"><span data-stu-id="a448b-132">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="a448b-133">Указанная выше страница содержит разделы для каждой из доступных установок.</span><span class="sxs-lookup"><span data-stu-id="a448b-133">The page referenced above contains sections to each of the available installations.</span></span>

<span data-ttu-id="a448b-134">Установка основной части компонентов выполняется диспетчером пакетов.</span><span class="sxs-lookup"><span data-stu-id="a448b-134">Most components to be installed are done by a package manager.</span></span> <span data-ttu-id="a448b-135">Если у вас установлен диспетчер пакетов node.js `npm`, этот шаг можно пропустить.</span><span class="sxs-lookup"><span data-stu-id="a448b-135">If you have node.js's package manager `npm` installed you can skip this step.</span></span> <span data-ttu-id="a448b-136">В противном случае установите последнюю версию NodeJs с сайта [nodejs.org](https://nodejs.org), которая содержит диспетчер пакетов npm.</span><span class="sxs-lookup"><span data-stu-id="a448b-136">Otherwise install the latest NodeJs from [nodejs.org](https://nodejs.org) which will install the npm package manager.</span></span> 

<span data-ttu-id="a448b-137">На этом этапе нужно установить несколько средств командной строки, поддерживающих разработку для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-137">At this point you will need to install a number of command line tools that support ASP.NET core development.</span></span> <span data-ttu-id="a448b-138">Шаблоны командной строки используют Yeoman, Bower, Grunt и Gulp.</span><span class="sxs-lookup"><span data-stu-id="a448b-138">The command line templates use Yeoman, Bower, Grunt, and Gulp.</span></span> <span data-ttu-id="a448b-139">Возможно, они у вас уже установлены. Если же нет, введите следующий текст в любой оболочке командной строки:</span><span class="sxs-lookup"><span data-stu-id="a448b-139">If you have them installed that is good, otherwise type the following into your favorite shell:</span></span>

`npm install -g yo bower grunt-cli gulp`

<span data-ttu-id="a448b-140">Параметр `-g` указывает, что установка выполняется глобально, то есть эти средства будут доступны во всей системе.</span><span class="sxs-lookup"><span data-stu-id="a448b-140">The `-g` option indicates that it is a global install, and those tools are available system wide.</span></span> <span data-ttu-id="a448b-141">(При локальной установке пакеты будут доступны только в одном проекте.)</span><span class="sxs-lookup"><span data-stu-id="a448b-141">(A local install scopes the package to a single project).</span></span> <span data-ttu-id="a448b-142">Когда вы закончите установку этих средств, установите еще и генераторы шаблонов yeoman ASP.NET:</span><span class="sxs-lookup"><span data-stu-id="a448b-142">Once you've installed those core tools, you need to install the yeoman ASP.NET template generators:</span></span>

`npm install -g generator-aspnet`

## <a name="create-the-application"></a><span data-ttu-id="a448b-143">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="a448b-143">Create the Application</span></span>

<span data-ttu-id="a448b-144">Теперь, когда вы установили все нужные средства, создайте новое приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-144">Now that you've installed all the tools, create a new ASP.NET Core application.</span></span> <span data-ttu-id="a448b-145">Чтобы использовать генератор из командной строки, выполните следующую команду yeoman в любой оболочке:</span><span class="sxs-lookup"><span data-stu-id="a448b-145">To use the command line generator, execute the following yeoman command in your favorite shell:</span></span>

`yo aspnet`

<span data-ttu-id="a448b-146">Эта команда предложит выбрать тип создаваемого приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-146">This command prompts you to select what Type of application you want to create.</span></span> <span data-ttu-id="a448b-147">Для нашего примера микрослужбы выберите самый простой и самый легкий вариант веб-приложения: "Пустое веб-приложение".</span><span class="sxs-lookup"><span data-stu-id="a448b-147">For this microservice, you want the simplest, most lightweight web application possible, so select 'Empty Web Application'.</span></span> <span data-ttu-id="a448b-148">Шаблон предложит ввести для него имя.</span><span class="sxs-lookup"><span data-stu-id="a448b-148">The template will prompt you for a name.</span></span> <span data-ttu-id="a448b-149">Введите строку WeatherMicroservice.</span><span class="sxs-lookup"><span data-stu-id="a448b-149">Select 'WeatherMicroservice'.</span></span> 

<span data-ttu-id="a448b-150">Шаблон создает восемь файлов.</span><span class="sxs-lookup"><span data-stu-id="a448b-150">The template creates eight files for you:</span></span>

* <span data-ttu-id="a448b-151">Файл GITIGNORE, настроенный для приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-151">A .gitignore, customized for ASP.NET Core applications.</span></span>
* <span data-ttu-id="a448b-152">Файл Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="a448b-152">A Startup.cs file.</span></span> <span data-ttu-id="a448b-153">Этот файл содержит основу для приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-153">This contains the basis of the application.</span></span>
* <span data-ttu-id="a448b-154">Файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="a448b-154">A Program.cs file.</span></span> <span data-ttu-id="a448b-155">Этот файл содержит точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-155">This contains the entry point of the application.</span></span>
* <span data-ttu-id="a448b-156">Файл WeatherMicroservice.csproj.</span><span class="sxs-lookup"><span data-stu-id="a448b-156">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="a448b-157">Это файл сборки для нашего приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-157">This is the build file for the application.</span></span>
* <span data-ttu-id="a448b-158">Файл Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a448b-158">A Dockerfile.</span></span> <span data-ttu-id="a448b-159">Это скрипт, который создает образ Docker для приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-159">This script creates a Docker image for the application.</span></span>
* <span data-ttu-id="a448b-160">Файл README.md.</span><span class="sxs-lookup"><span data-stu-id="a448b-160">A README.md.</span></span> <span data-ttu-id="a448b-161">Этот файл содержит ссылки на другие ресурсы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-161">This contains links to other ASP.NET Core resources.</span></span>
* <span data-ttu-id="a448b-162">Файл web.config.</span><span class="sxs-lookup"><span data-stu-id="a448b-162">A web.config file.</span></span> <span data-ttu-id="a448b-163">Этот файл содержит информацию о базовой конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a448b-163">This contains basic configuration information.</span></span>
* <span data-ttu-id="a448b-164">Файл runtimeconfig.template.json.</span><span class="sxs-lookup"><span data-stu-id="a448b-164">A runtimeconfig.template.json file.</span></span> <span data-ttu-id="a448b-165">Этот файл содержит параметры отладки, используемые интегрированными средами разработки.</span><span class="sxs-lookup"><span data-stu-id="a448b-165">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="a448b-166">Теперь можно запустить приложение, созданное на основе шаблона.</span><span class="sxs-lookup"><span data-stu-id="a448b-166">Now you can run the template generated application.</span></span> <span data-ttu-id="a448b-167">В этом вам помогут несколько средств командной строки.</span><span class="sxs-lookup"><span data-stu-id="a448b-167">That's done using a series of tools from the command line.</span></span> <span data-ttu-id="a448b-168">Команда `dotnet` запускает средства, необходимые для разработки в среде .NET.</span><span class="sxs-lookup"><span data-stu-id="a448b-168">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="a448b-169">Каждая команда соответствует определенному средству.</span><span class="sxs-lookup"><span data-stu-id="a448b-169">Each verb executes a different command</span></span>

<span data-ttu-id="a448b-170">Сначала нужно восстановить все зависимости:</span><span class="sxs-lookup"><span data-stu-id="a448b-170">The first step is to restore all the dependencies:</span></span>

```console
dotnet restore
```

<span data-ttu-id="a448b-171">Команда dotnet restore устанавливает все необходимые пакеты в каталог приложения с помощью диспетчера пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="a448b-171">Dotnet restore uses the NuGet package manager to install all the necessary packages into the application directory.</span></span> <span data-ttu-id="a448b-172">Она также создает файл project.json.lock.</span><span class="sxs-lookup"><span data-stu-id="a448b-172">It also generates a project.json.lock file.</span></span> <span data-ttu-id="a448b-173">Этот файл содержит сведения о каждом пакета, на который имеется ссылка.</span><span class="sxs-lookup"><span data-stu-id="a448b-173">This file contains information about each package that is referenced.</span></span> <span data-ttu-id="a448b-174">После восстановления всех зависимостей выполните сборку приложения:</span><span class="sxs-lookup"><span data-stu-id="a448b-174">After restoring all the dependencies, you build the application:</span></span>

```console
dotnet build
```
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

<span data-ttu-id="a448b-175">Когда сборка завершится, приложение можно запустить из командной строки:</span><span class="sxs-lookup"><span data-stu-id="a448b-175">And once you build the application, you run it from the command line:</span></span>

```console
dotnet run
```

<span data-ttu-id="a448b-176">В конфигурации по умолчанию приложение прослушивает адрес http://localhost: 5000.</span><span class="sxs-lookup"><span data-stu-id="a448b-176">The default configuration listens to http://localhost:5000.</span></span> <span data-ttu-id="a448b-177">Откройте браузер и перейдите на эту страницу. Вы должны увидеть приветствие Hello World</span><span class="sxs-lookup"><span data-stu-id="a448b-177">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="a448b-178">!".</span><span class="sxs-lookup"><span data-stu-id="a448b-178">message.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="a448b-179">Анатомия приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a448b-179">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="a448b-180">Теперь у вас есть готовое приложение. Давайте на его примере рассмотрим реализацию функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="a448b-180">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="a448b-181">Из созданных файлов приложения нам пока наиболее интересны вот эти два: project.json и Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="a448b-181">There are two of the generated files that are particularly interesting at this point: project.json and Startup.cs.</span></span> 

<span data-ttu-id="a448b-182">Project.json содержит сведения о проекте.</span><span class="sxs-lookup"><span data-stu-id="a448b-182">Project.json contains information about the project.</span></span> <span data-ttu-id="a448b-183">Вы будете часто иметь дело с двумя узлами: dependencies (зависимости) и frameworks (платформы).</span><span class="sxs-lookup"><span data-stu-id="a448b-183">The two nodes you'll often work with are 'dependencies' and 'frameworks'.</span></span> <span data-ttu-id="a448b-184">Узел зависимостей перечисляет все пакеты, которые необходимы для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-184">The dependencies node lists all the packages that are needed for this application.</span></span>
<span data-ttu-id="a448b-185">Пока наш узел совсем мал, и ему требуются только те пакеты, которые обязательны для работы веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="a448b-185">At the moment, this is a small node, needing only the packages that run the web server.</span></span>

<span data-ttu-id="a448b-186">Узел платформ описывает версии и конфигурации платформы .NET framework, на которых будет выполняться это приложение.</span><span class="sxs-lookup"><span data-stu-id="a448b-186">The 'frameworks' node specifies the versions and configurations of the .NET framework that will run this application.</span></span>

<span data-ttu-id="a448b-187">Само приложение реализовано в файле Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="a448b-187">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="a448b-188">Этот файл содержит класс Startup.</span><span class="sxs-lookup"><span data-stu-id="a448b-188">This file contains the startup class.</span></span>

<span data-ttu-id="a448b-189">Инфраструктура ASP.NET Core вызывает два метода этого класса для настройки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-189">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="a448b-190">Метод `ConfigureServices` описывает службы, которые необходимы для приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-190">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="a448b-191">Наша служба не использует никакие ресурсы, и для нее не нужны никакие зависимости.</span><span class="sxs-lookup"><span data-stu-id="a448b-191">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="a448b-192">Метод `Configure` настраивает обработчики для входящих HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="a448b-192">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="a448b-193">Шаблон создает простой обработчик, который в ответ на любой запрос возвращает текст "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="a448b-193">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="a448b-194">Сборка микрослужбы</span><span class="sxs-lookup"><span data-stu-id="a448b-194">Build a microservice</span></span>

<span data-ttu-id="a448b-195">Служба, которую вы разрабатываете, будет доставлять сведения о погоде в любой точке земного шара.</span><span class="sxs-lookup"><span data-stu-id="a448b-195">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="a448b-196">В рабочем приложении вы будете обращаться к реальным службам для получения данных о погоде.</span><span class="sxs-lookup"><span data-stu-id="a448b-196">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="a448b-197">Но для этого примера нам достаточно создать случайный прогноз погоды.</span><span class="sxs-lookup"><span data-stu-id="a448b-197">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="a448b-198">Чтобы получить его, мы выполним несколько задач:</span><span class="sxs-lookup"><span data-stu-id="a448b-198">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="a448b-199">синтаксический анализ входящего запроса для получения широты и долготы;</span><span class="sxs-lookup"><span data-stu-id="a448b-199">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="a448b-200">создание случайных данных для прогноза;</span><span class="sxs-lookup"><span data-stu-id="a448b-200">Generate some random forecast data.</span></span>
* <span data-ttu-id="a448b-201">преобразование случайных данных прогноза из объектов C# в пакеты JSON;</span><span class="sxs-lookup"><span data-stu-id="a448b-201">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="a448b-202">установка заголовка ответа, который будет обозначать отправку данных в формате JSON;</span><span class="sxs-lookup"><span data-stu-id="a448b-202">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="a448b-203">создание текста ответа.</span><span class="sxs-lookup"><span data-stu-id="a448b-203">Write the response.</span></span>

<span data-ttu-id="a448b-204">В следующем разделе описаны шаги для выполнения каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="a448b-204">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="a448b-205">Синтаксический анализ входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="a448b-205">Parsing the Query String.</span></span>

<span data-ttu-id="a448b-206">Прежде всего нужно выполнить синтаксический анализ строки запроса.</span><span class="sxs-lookup"><span data-stu-id="a448b-206">You'll begin by parsing the query string.</span></span> <span data-ttu-id="a448b-207">Служба будет принимать в строке запроса аргументы lat и long в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="a448b-207">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

`http://localhost:5000/?lat=-35.55&long=-12.35`  

<span data-ttu-id="a448b-208">Все изменения, которые нужно выполнить, относятся к лямбда-выражению, которое определено в классе запуска в качестве аргумента для метода `app.Run`.</span><span class="sxs-lookup"><span data-stu-id="a448b-208">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="a448b-209">В лямбда-выражении нас интересует аргумент `HttpContext`, представляющий запрос.</span><span class="sxs-lookup"><span data-stu-id="a448b-209">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="a448b-210">Одним из его свойств является объект `Request`.</span><span class="sxs-lookup"><span data-stu-id="a448b-210">One of its properties is the `Request` object.</span></span> <span data-ttu-id="a448b-211">Объект `Request` имеет свойство `Query`, которое содержит словарь всех значений, переданных в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="a448b-211">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="a448b-212">Сначала добавьте строки для поиска значений широты и долготы:</span><span class="sxs-lookup"><span data-stu-id="a448b-212">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="a448b-213">Значения в словаре запроса имеют тип `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="a448b-213">The Query dictionary values are `StringValue` type.</span></span> <span data-ttu-id="a448b-214">Этот тип может содержать коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="a448b-214">That type can contain a collection of strings.</span></span> <span data-ttu-id="a448b-215">Для нашей службы погоды каждое значение должно содержать одну строку.</span><span class="sxs-lookup"><span data-stu-id="a448b-215">For your weather service, each value is a single string.</span></span> <span data-ttu-id="a448b-216">Поэтому в приведенном выше коде мы вызываем метод `FirstOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="a448b-216">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="a448b-217">Теперь нам нужно преобразовать эти строки в тип Double.</span><span class="sxs-lookup"><span data-stu-id="a448b-217">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="a448b-218">Для преобразования строки в значение типа double мы используем метод `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="a448b-218">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="a448b-219">Этот метод использует параметры вывода C#, чтобы определить возможность преобразования входной строки к типу double.</span><span class="sxs-lookup"><span data-stu-id="a448b-219">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="a448b-220">Если строка содержит допустимое представление для типа double, метод возвращает значение true, а аргумент `result` содержит преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="a448b-220">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="a448b-221">Если строка не представляет допустимого представления для типа double, метод возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="a448b-221">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="a448b-222">Этот API можно дополнить *методом расширения*, который возвращает *тип double, допускающий значение NULL*.</span><span class="sxs-lookup"><span data-stu-id="a448b-222">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="a448b-223">*Тип, допускающий значение NULL*, может содержать значения некоторого типа или значение NULL, которое обозначает отсутствие значения.</span><span class="sxs-lookup"><span data-stu-id="a448b-223">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="a448b-224">Чтобы использовать тип, допускающий значения NULL, добавьте к объявлению типа символ `?`.</span><span class="sxs-lookup"><span data-stu-id="a448b-224">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="a448b-225">Методы расширения представляют собой методы, которые определяются как обычные статические методы, но с модификатором `this` для первого параметра. Такие методы можно вызывать так, как будто они являются членами этого класса.</span><span class="sxs-lookup"><span data-stu-id="a448b-225">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="a448b-226">Методы расширения можно определять только в статических классах.</span><span class="sxs-lookup"><span data-stu-id="a448b-226">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="a448b-227">Вот пример определения класса с методом расширения для синтаксического анализа:</span><span class="sxs-lookup"><span data-stu-id="a448b-227">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="a448b-228">Выражение `default(double?)` возвращает значение по умолчанию для типа `double?`.</span><span class="sxs-lookup"><span data-stu-id="a448b-228">The `default(double?)` expression returns the default value for the `double?` type.</span></span> <span data-ttu-id="a448b-229">По умолчанию значение для него отсутствует (возвращается NULL).</span><span class="sxs-lookup"><span data-stu-id="a448b-229">That default value is the null (or missing) value.</span></span>

<span data-ttu-id="a448b-230">Этот метод расширения можно использовать для преобразования аргументов строки запроса в тип double:</span><span class="sxs-lookup"><span data-stu-id="a448b-230">You can use this extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="a448b-231">Чтобы быстро проверить работу кода для синтаксического анализа, включите значения аргументов в возвращаемый ответ:</span><span class="sxs-lookup"><span data-stu-id="a448b-231">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="a448b-232">На этом этапе можно запустить веб-приложение и убедиться, работает ли код для синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="a448b-232">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="a448b-233">В строке запроса браузера добавьте какие-либо значения, обновите страницу и убедитесь, что они правильно возвращаются.</span><span class="sxs-lookup"><span data-stu-id="a448b-233">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="a448b-234">Создание случайного прогноза погоды</span><span class="sxs-lookup"><span data-stu-id="a448b-234">Build a random weather forecast</span></span>

<span data-ttu-id="a448b-235">Теперь мы переходим к созданию случайного прогноза погоды.</span><span class="sxs-lookup"><span data-stu-id="a448b-235">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="a448b-236">Для этого нам в первую очередь нужен контейнер, который содержит значения для прогноза погоды:</span><span class="sxs-lookup"><span data-stu-id="a448b-236">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

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

<span data-ttu-id="a448b-237">Теперь создайте конструктор, который задает эти значения случайным образом.</span><span class="sxs-lookup"><span data-stu-id="a448b-237">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="a448b-238">Этот конструктор использует значения широты и долготы в качестве начального значения для генератора случайных чисел.</span><span class="sxs-lookup"><span data-stu-id="a448b-238">This constructor uses the values for the latitude and longitude to seed the Random number generator.</span></span> <span data-ttu-id="a448b-239">Это означает, что для каждого набора координат всегда будет возвращаться одинаковый прогноз.</span><span class="sxs-lookup"><span data-stu-id="a448b-239">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="a448b-240">Если вы измените значения для аргументов широты и долготы, вы получите другой прогноз (поскольку начальное значение для генератора случайных чисел будет другим).</span><span class="sxs-lookup"><span data-stu-id="a448b-240">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed.)</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="a448b-241">Создайте в методе ответа прогноз на 5 дней:</span><span class="sxs-lookup"><span data-stu-id="a448b-241">You can now generate the 5-day forecast in your response method:</span></span>

[!code-csharp[GenerateRandomReport](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#GenerateRandomReport "Generate a random weather report")]

### <a name="build-the-json-response"></a><span data-ttu-id="a448b-242">Оформление ответа в формате JSON</span><span class="sxs-lookup"><span data-stu-id="a448b-242">Build the JSON response.</span></span>

<span data-ttu-id="a448b-243">Последней задачей, которую выполняет код на сервере, будет преобразование массива WeatherReport в пакет JSON и отправка этого пакета клиенту.</span><span class="sxs-lookup"><span data-stu-id="a448b-243">The final code task on the server is to convert the WeatherReport array into a JSON packet, and send that back to the client.</span></span> <span data-ttu-id="a448b-244">Здесь нам нужно сначала создать пакет JSON.</span><span class="sxs-lookup"><span data-stu-id="a448b-244">Let's start by creating the JSON packet.</span></span> <span data-ttu-id="a448b-245">В список зависимостей добавьте сериализатор NewtonSoft JSON.</span><span class="sxs-lookup"><span data-stu-id="a448b-245">You'll add the NewtonSoft JSON Serializer to the list of dependencies.</span></span> <span data-ttu-id="a448b-246">Для этого можно использовать команду `dotnet` CLI:</span><span class="sxs-lookup"><span data-stu-id="a448b-246">You can do that using the `dotnet` CLI:</span></span>

```
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="a448b-247">Теперь примените класс `JsonConvert`, чтобы преобразовать наш объект в строку:</span><span class="sxs-lookup"><span data-stu-id="a448b-247">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="a448b-248">Приведенный выше код преобразует объект прогноза (список объектов `WeatherForecast`) в пакет JSON.</span><span class="sxs-lookup"><span data-stu-id="a448b-248">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON packet.</span></span> <span data-ttu-id="a448b-249">Когда пакет с ответом будет готов, укажите для него тип содержимого `application/json` и возвратите строку.</span><span class="sxs-lookup"><span data-stu-id="a448b-249">After you've constructed the response packet, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="a448b-250">Теперь наше приложение создает и возвращает случайные прогнозы погоды.</span><span class="sxs-lookup"><span data-stu-id="a448b-250">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="a448b-251">Создание образа Docker</span><span class="sxs-lookup"><span data-stu-id="a448b-251">Build a Docker image</span></span>

<span data-ttu-id="a448b-252">Последней задачей в этой статье будет запуск приложения в Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-252">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="a448b-253">Мы создадим контейнер Docker, который выполняет образ Docker с созданным ранее приложением.</span><span class="sxs-lookup"><span data-stu-id="a448b-253">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="a448b-254">Объект ***образа Docker*** — это файл, который определяет среду для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-254">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="a448b-255">***Контейнер Docker*** представляет запущенный экземпляр образа Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-255">A ***Docker Container*** represents a running instance of a Docker image.</span></span>

<span data-ttu-id="a448b-256">Для упрощения понимания вы можете представить *образ Docker* как *класс*, а *контейнер Docker* — как объект или экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="a448b-256">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="a448b-257">Для этой задачи мы применим файл Dockerfile, созданным с помощью шаблона ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a448b-257">The Dockerfile created by the ASP.NET template will serve for our purposes.</span></span> <span data-ttu-id="a448b-258">Давайте изучим его содержимое.</span><span class="sxs-lookup"><span data-stu-id="a448b-258">Let's go over its contents.</span></span>

<span data-ttu-id="a448b-259">Первая строка задает исходный образ:</span><span class="sxs-lookup"><span data-stu-id="a448b-259">The first line specifies the source image:</span></span>

```
FROM microsoft/dotnet:1.1-sdk-msbuild
```

<span data-ttu-id="a448b-260">Docker позволяет настроить образ компьютера на основе исходного шаблона.</span><span class="sxs-lookup"><span data-stu-id="a448b-260">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="a448b-261">Это значит, что при запуске вам не придется указывать все параметры компьютера. Достаточно указать лишь изменения параметров, если они потребуются.</span><span class="sxs-lookup"><span data-stu-id="a448b-261">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="a448b-262">Здесь таким изменением станет запуск нашего приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-262">The changes here will be to include our application.</span></span>

<span data-ttu-id="a448b-263">В первом примере мы будем использовать версию `1.1-sdk-msbuild` образа dotnet.</span><span class="sxs-lookup"><span data-stu-id="a448b-263">In this first sample, we'll use the `1.1-sdk-msbuild` version of the dotnet image.</span></span> <span data-ttu-id="a448b-264">Это самый простой способ создать рабочую среду Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-264">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="a448b-265">Этот образ включает базовую среду выполнения DotNet и пакет SDK DotNet.</span><span class="sxs-lookup"><span data-stu-id="a448b-265">This image include the dotnet core runtime, and the dotnet SDK.</span></span> <span data-ttu-id="a448b-266">Это позволяет быстрее начать разработку и сборку, но увеличивает размер образа.</span><span class="sxs-lookup"><span data-stu-id="a448b-266">That makes it easier to get started and build, but does create a larger image.</span></span>

<span data-ttu-id="a448b-267">Следующие пять строк выполняют настройку и сборку приложения:</span><span class="sxs-lookup"><span data-stu-id="a448b-267">The next five lines setup and build your application:</span></span>

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

<span data-ttu-id="a448b-268">Здесь файл проекта копируется из текущего каталога на виртуальную машину Docker, а также восстанавливаются все пакеты.</span><span class="sxs-lookup"><span data-stu-id="a448b-268">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="a448b-269">Мы используем Dotnet CLI, а значит образ Docker должен включать пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a448b-269">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="a448b-270">После этого копируется остальная часть приложения, а команда dotnet publish выполняет сборку и упаковку приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-270">After that, the rest of your application gets copied, and the dotnet publish command builds and packages your application.</span></span>

<span data-ttu-id="a448b-271">Последняя строка этого файла запускает наше приложение:</span><span class="sxs-lookup"><span data-stu-id="a448b-271">The final line of the file runs the application:</span></span>

```
ENTRYPOINT ["dotnet", "out/WeatherMicroservice.dll", "--server.urls", "http://0.0.0.0:5000"]
```

<span data-ttu-id="a448b-272">Настроенный здесь порт используется в аргументе `--server.urls` команды `dotnet`, которая находится в последней строке файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a448b-272">This configured port is referenced in the `--server.urls` argument to `dotnet` on the last  line of the Dockerfile.</span></span> <span data-ttu-id="a448b-273">Команда `ENTRYPOINT` сообщает Docker, какие команды и параметры командной строки нужно использовать для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="a448b-273">The `ENTRYPOINT` command informs Docker what command and command-line options start the service.</span></span> 

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="a448b-274">Сборка и выполнение образа в контейнере.</span><span class="sxs-lookup"><span data-stu-id="a448b-274">Building and running the image in a container.</span></span>

<span data-ttu-id="a448b-275">Теперь мы создадим образ и запустим службу в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="a448b-275">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="a448b-276">Вам не нужно, чтобы в образ копировались все файлы из локального каталога.</span><span class="sxs-lookup"><span data-stu-id="a448b-276">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="a448b-277">Поэтому приложение следует собирать в контейнере.</span><span class="sxs-lookup"><span data-stu-id="a448b-277">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="a448b-278">Для этого создайте файл `.dockerignore` и перечислите в нем каталоги, которые не нужно копировать в образ.</span><span class="sxs-lookup"><span data-stu-id="a448b-278">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="a448b-279">Например, вам не нужно, чтобы копировались активы сборки.</span><span class="sxs-lookup"><span data-stu-id="a448b-279">You don't want any of the build assets copied.</span></span> <span data-ttu-id="a448b-280">Укажите каталоги для сборки и публикации в файле `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="a448b-280">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="a448b-281">Для сборки образа используется команда `docker build`.</span><span class="sxs-lookup"><span data-stu-id="a448b-281">You build the image using the `docker build` command.</span></span> <span data-ttu-id="a448b-282">Выполните следующую команду из каталога, содержащего код приложения.</span><span class="sxs-lookup"><span data-stu-id="a448b-282">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="a448b-283">Эта команда собирает контейнер изображения, используя информацию из файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="a448b-283">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="a448b-284">Аргумент `-t` содержит тег (имя) для создаваемого образа контейнера.</span><span class="sxs-lookup"><span data-stu-id="a448b-284">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="a448b-285">В приведенной выше командной строке для контейнера Docker указан тег `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="a448b-285">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="a448b-286">Когда завершится выполнение этой команды, у вас будет готовый контейнер для запуска новой службы.</span><span class="sxs-lookup"><span data-stu-id="a448b-286">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="a448b-287">Выполните следующую команду, чтобы запустить созданный контейнер и соответствующую службу:</span><span class="sxs-lookup"><span data-stu-id="a448b-287">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:5000 --name hello-docker weather-microservice
```

<span data-ttu-id="a448b-288">Параметр `-d` указывает, что контейнер следует отсоединить от текущего терминала.</span><span class="sxs-lookup"><span data-stu-id="a448b-288">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="a448b-289">Это означает, что вы не увидите выходные данные команды в окне терминала.</span><span class="sxs-lookup"><span data-stu-id="a448b-289">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="a448b-290">Параметр `-p` настраивает сопоставление портов между службой и узлом.</span><span class="sxs-lookup"><span data-stu-id="a448b-290">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="a448b-291">В этом примере все входящие запросы на порт 80 будут перенаправляться на порт контейнера 5000.</span><span class="sxs-lookup"><span data-stu-id="a448b-291">Here it says that any incoming request on port 80 should be forwarded to port 5000 on the container.</span></span> <span data-ttu-id="a448b-292">Значение 5000 совпадает с тем значением параметра командной строки, который мы указали выше в файле Dockerfile. Именно этот порт прослушивает ваша служба.</span><span class="sxs-lookup"><span data-stu-id="a448b-292">Using 5000 matches the port your service is listening on from the command line arguments specified in the Dockerfile above.</span></span> <span data-ttu-id="a448b-293">Аргумент `--name` задает имя для выполняемого контейнера.</span><span class="sxs-lookup"><span data-stu-id="a448b-293">The `--name` argument names your running container.</span></span> <span data-ttu-id="a448b-294">Здесь вы можете указать любое удобное для вас имя, которое упростит работу с этим контейнером.</span><span class="sxs-lookup"><span data-stu-id="a448b-294">It's a convenient name you can use to work with that container.</span></span> 

<span data-ttu-id="a448b-295">С помощью следующей команды вы можете проверить, выполняется ли образ:</span><span class="sxs-lookup"><span data-stu-id="a448b-295">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="a448b-296">Если контейнер работает, вы увидите строку с его именем в списке запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="a448b-296">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="a448b-297">(Возможно, это будет единственная строка в этом списке.)</span><span class="sxs-lookup"><span data-stu-id="a448b-297">(It may be the only one).</span></span>

<span data-ttu-id="a448b-298">Вы можете проверить работу вашей службы, открыв локальный адрес localhost в окне браузера и введя значения для широты и долготы:</span><span class="sxs-lookup"><span data-stu-id="a448b-298">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="a448b-299">Присоединение к работающему контейнеру</span><span class="sxs-lookup"><span data-stu-id="a448b-299">Attaching to a running container</span></span>

<span data-ttu-id="a448b-300">Когда вы запускали службу в командном окне, для каждого запроса вы получали диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="a448b-300">When you ran your sevice in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="a448b-301">Теперь, когда контейнер работает в отсоединенном режиме, вы больше не видите эту информацию.</span><span class="sxs-lookup"><span data-stu-id="a448b-301">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="a448b-302">Команда Docker attach дает возможность присоединиться к выполняющемуся контейнеру, чтобы просмотреть данные журнала.</span><span class="sxs-lookup"><span data-stu-id="a448b-302">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="a448b-303">В окне командной строки выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a448b-303">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="a448b-304">Аргумент `--sig-proxy=false` означает, что команды `Ctrl-C` не передаются в процесс контейнера, а просто останавливают выполнение команды `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="a448b-304">The `--sig-proxy=false` argument means that `Ctrl-C` commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="a448b-305">Последний аргумент обозначает имя, присвоенное контейнеру ранее, при выполнении команды `docker run`.</span><span class="sxs-lookup"><span data-stu-id="a448b-305">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="a448b-306">Также для ссылки на любой контейнер вы можете использовать назначенный Docker идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="a448b-306">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="a448b-307">Если в команде `docker run` не указано имя контейнера, необходимо использовать идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="a448b-307">If you didn't specify a name for your container in `docker run` you must use the container id.</span></span>

<span data-ttu-id="a448b-308">Откройте браузер и перейдите к адресу вашей службы.</span><span class="sxs-lookup"><span data-stu-id="a448b-308">Open a browser and navigate to your service.</span></span> <span data-ttu-id="a448b-309">В командном окне вы увидите диагностические сообщения, генерируемые присоединенным контейнером.</span><span class="sxs-lookup"><span data-stu-id="a448b-309">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="a448b-310">Чтобы остановить этот процесс, нажмите клавиши `Ctrl-C`.</span><span class="sxs-lookup"><span data-stu-id="a448b-310">Press `Ctrl-C` to stop the attach process.</span></span>

<span data-ttu-id="a448b-311">Когда вы завершите работу с контейнером, его можно остановить:</span><span class="sxs-lookup"><span data-stu-id="a448b-311">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="a448b-312">При этом контейнер и образ останутся доступны, и их можно запустить заново.</span><span class="sxs-lookup"><span data-stu-id="a448b-312">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="a448b-313">Если вы хотите удалить контейнер с компьютера, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a448b-313">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="a448b-314">Если вы хотите удалить с компьютера все неиспользуемые контейнеры, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="a448b-314">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="a448b-315">Заключение</span><span class="sxs-lookup"><span data-stu-id="a448b-315">Conclusion</span></span> 

<span data-ttu-id="a448b-316">В этом руководстве вы создали микрослужбу ASP.NET Core и добавили в нее несколько простых функций.</span><span class="sxs-lookup"><span data-stu-id="a448b-316">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="a448b-317">Вы создали образ контейнера Docker для этой службы и запустили его на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a448b-317">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="a448b-318">Также вы подключили к службе окно терминала и увидели диагностические сообщения от службы.</span><span class="sxs-lookup"><span data-stu-id="a448b-318">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="a448b-319">В процессе изучения вы также узнали, как используются некоторые функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="a448b-319">Along the way, you saw several features of the C# language in action.</span></span>
