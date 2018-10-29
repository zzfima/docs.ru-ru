---
title: Микрослужбы, размещенные в Docker. Язык C#
description: Узнайте, как создать службы ASP.NET Core, выполняемые в контейнерах Docker
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: b1f7159a222ab4d68715844e9997ca922676bc80
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454490"
---
# <a name="microservices-hosted-in-docker"></a><span data-ttu-id="955ca-103">Микрослужбы, размещенные в Docker</span><span class="sxs-lookup"><span data-stu-id="955ca-103">Microservices hosted in Docker</span></span>

<span data-ttu-id="955ca-104">В этом руководстве описан процесс построения и развертывания микрослужбы ASP.NET Core в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-104">This tutorial details the tasks necessary to build and deploy an ASP.NET Core microservice in a Docker container.</span></span> <span data-ttu-id="955ca-105">В ходе работы с этим руководством вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="955ca-105">During the course of this tutorial, you'll learn:</span></span>

* <span data-ttu-id="955ca-106">как создать приложение ASP.NET Core;</span><span class="sxs-lookup"><span data-stu-id="955ca-106">How to generate an ASP.NET Core application.</span></span>
* <span data-ttu-id="955ca-107">как создать среду разработки Docker;</span><span class="sxs-lookup"><span data-stu-id="955ca-107">How to create a development Docker environment.</span></span>
* <span data-ttu-id="955ca-108">как создать образ Docker на основе существующего образа;</span><span class="sxs-lookup"><span data-stu-id="955ca-108">How to build a Docker image based on an existing image.</span></span>
* <span data-ttu-id="955ca-109">как развертывать службы в контейнер Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-109">How to deploy your service into a Docker container.</span></span>

<span data-ttu-id="955ca-110">Одновременно с этим вы увидите примеры использования некоторых возможностей языка C#:</span><span class="sxs-lookup"><span data-stu-id="955ca-110">Along the way, you'll also see some C# language features:</span></span>

* <span data-ttu-id="955ca-111">как преобразовать объекты C# в полезные данные JSON;</span><span class="sxs-lookup"><span data-stu-id="955ca-111">How to convert C# objects into JSON payloads.</span></span>
* <span data-ttu-id="955ca-112">как создать неизменяемые объекты передачи данных;</span><span class="sxs-lookup"><span data-stu-id="955ca-112">How to build immutable Data Transfer Objects.</span></span>
* <span data-ttu-id="955ca-113">как обрабатывать входящие запросы HTTP и формировать HTTP-ответы;</span><span class="sxs-lookup"><span data-stu-id="955ca-113">How to process incoming HTTP Requests and generate the HTTP Response.</span></span>
* <span data-ttu-id="955ca-114">как использовать типы значений, допускающих значение NULL.</span><span class="sxs-lookup"><span data-stu-id="955ca-114">How to work with nullable value types.</span></span>

<span data-ttu-id="955ca-115">Вы можете [просмотреть или скачать пример приложения](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) для этого раздела.</span><span class="sxs-lookup"><span data-stu-id="955ca-115">You can [view or download the sample app](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice) for this topic.</span></span> <span data-ttu-id="955ca-116">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="955ca-116">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="why-docker"></a><span data-ttu-id="955ca-117">Преимущества Docker</span><span class="sxs-lookup"><span data-stu-id="955ca-117">Why Docker?</span></span>

<span data-ttu-id="955ca-118">Docker позволяет легко создавать стандартные образы виртуальной машины для размещения служб в центре обработки данных или в общедоступном облаке.</span><span class="sxs-lookup"><span data-stu-id="955ca-118">Docker makes it easy to create standard machine images to host your services in a data center, or the public cloud.</span></span> <span data-ttu-id="955ca-119">Docker позволяет настраивать образ и реплицировать его по мере необходимости для масштабирования приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-119">Docker enables you to configure the image, and replicate it as needed to scale the installation of your application.</span></span>

<span data-ttu-id="955ca-120">Весь код, представленный в этом руководстве, будет работать в любой среде .NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-120">All the code in this tutorial will work in any .NET Core environment.</span></span>
<span data-ttu-id="955ca-121">Дополнительные задачи по установке Docker совместимы с приложением ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-121">The additional tasks for a Docker installation will work for an ASP.NET Core application.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="955ca-122">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="955ca-122">Prerequisites</span></span>

<span data-ttu-id="955ca-123">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-123">You’ll need to setup your machine to run .NET Core.</span></span> <span data-ttu-id="955ca-124">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="955ca-124">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span>
<span data-ttu-id="955ca-125">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-125">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="955ca-126">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="955ca-126">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="955ca-127">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="955ca-127">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/) which is an open source, cross platform editor.</span></span> <span data-ttu-id="955ca-128">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="955ca-128">However, you can use whatever tools you are comfortable with.</span></span>

<span data-ttu-id="955ca-129">Также необходимо установить подсистему Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-129">You'll also need to install the Docker engine.</span></span> <span data-ttu-id="955ca-130">На [странице установки Docker](https://docs.docker.com/install/overview/) вы найдете инструкции для вашей платформы.</span><span class="sxs-lookup"><span data-stu-id="955ca-130">See the [Docker Installation page](https://docs.docker.com/install/overview/) for instructions for your platform.</span></span>
<span data-ttu-id="955ca-131">Docker можно установить на многих дистрибутивах Linux, macOS или Windows.</span><span class="sxs-lookup"><span data-stu-id="955ca-131">Docker can be installed in many Linux distributions, macOS, or Windows.</span></span> <span data-ttu-id="955ca-132">Указанная выше страница содержит разделы для каждой из доступных установок.</span><span class="sxs-lookup"><span data-stu-id="955ca-132">The page referenced above contains sections to each of the available installations.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="955ca-133">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="955ca-133">Create the Application</span></span>

<span data-ttu-id="955ca-134">После установки всех средств создайте новое приложение ASP.NET Core в каталоге "WeatherMicroservice", выполнив следующую команду в предпочитаемой оболочке:</span><span class="sxs-lookup"><span data-stu-id="955ca-134">Now that you've installed all the tools, create a new ASP.NET Core application in a directory called "WeatherMicroservice" by executing the following command in your favorite shell:</span></span>

```console
dotnet new web -o WeatherMicroservice
```

<span data-ttu-id="955ca-135">Команда `dotnet` запускает средства, необходимые для разработки в среде .NET.</span><span class="sxs-lookup"><span data-stu-id="955ca-135">The `dotnet` command runs the tools necessary for .NET development.</span></span> <span data-ttu-id="955ca-136">Каждая команда соответствует определенному средству.</span><span class="sxs-lookup"><span data-stu-id="955ca-136">Each verb executes a different command.</span></span>

<span data-ttu-id="955ca-137">Команда `dotnet new` используется для создания проектов .Net Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-137">The `dotnet new` command is used to create .Net Core projects.</span></span>

<span data-ttu-id="955ca-138">Параметр `-o WeatherMicroservice` после команды `dotnet new` указывает расположение, в котором будет создано приложение ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-138">The `-o WeatherMicroservice` option after the `dotnet new` command is used to give the location to create the ASP.NET Core application.</span></span>

<span data-ttu-id="955ca-139">Для этой микрослужбы нам нужно как можно более простое и легкое веб-приложение, поэтому мы использовали шаблон "ASP.NET Core Empty", указав его краткое имя `web`.</span><span class="sxs-lookup"><span data-stu-id="955ca-139">For this microservice, we want the simplest, most lightweight web application possible, so we used the "ASP.NET Core Empty" template, by specifying its short name, `web`.</span></span>

<span data-ttu-id="955ca-140">Шаблон создает четыре файла:</span><span class="sxs-lookup"><span data-stu-id="955ca-140">The template creates four files for you:</span></span>

* <span data-ttu-id="955ca-141">Файл Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="955ca-141">A Startup.cs file.</span></span> <span data-ttu-id="955ca-142">Этот файл содержит основу для приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-142">This contains the basis of the application.</span></span>
* <span data-ttu-id="955ca-143">Файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="955ca-143">A Program.cs file.</span></span> <span data-ttu-id="955ca-144">Этот файл содержит точку входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-144">This contains the entry point of the application.</span></span>
* <span data-ttu-id="955ca-145">Файл WeatherMicroservice.csproj.</span><span class="sxs-lookup"><span data-stu-id="955ca-145">A WeatherMicroservice.csproj file.</span></span> <span data-ttu-id="955ca-146">Это файл сборки для нашего приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-146">This is the build file for the application.</span></span>
* <span data-ttu-id="955ca-147">Файл Properties/launchSettings.json.</span><span class="sxs-lookup"><span data-stu-id="955ca-147">A Properties/launchSettings.json file.</span></span> <span data-ttu-id="955ca-148">Этот файл содержит параметры отладки, используемые интегрированными средами разработки.</span><span class="sxs-lookup"><span data-stu-id="955ca-148">This contains debugging settings used by IDEs.</span></span>

<span data-ttu-id="955ca-149">Теперь можно запустить приложение, созданное на основе шаблона:</span><span class="sxs-lookup"><span data-stu-id="955ca-149">Now you can run the template generated application:</span></span>

```console
dotnet run
```

<span data-ttu-id="955ca-150">Эта команда сначала восстановит зависимости, необходимые для сборки приложения, а затем соберет приложение.</span><span class="sxs-lookup"><span data-stu-id="955ca-150">This command will first restore dependencies required to build the application and then it will build the application.</span></span>

<span data-ttu-id="955ca-151">В конфигурации по умолчанию приложение прослушивает адрес `http://localhost:5000`.</span><span class="sxs-lookup"><span data-stu-id="955ca-151">The default configuration listens to `http://localhost:5000`.</span></span> <span data-ttu-id="955ca-152">Откройте браузер и перейдите на эту страницу. Вы должны увидеть приветствие Hello World</span><span class="sxs-lookup"><span data-stu-id="955ca-152">You can open a browser and navigate to that page and see a "Hello World!"</span></span> <span data-ttu-id="955ca-153">!".</span><span class="sxs-lookup"><span data-stu-id="955ca-153">message.</span></span>

<span data-ttu-id="955ca-154">Когда закончите, завершите работу приложения, нажав <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="955ca-154">When you're done, you can shut down the application by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span></span>

### <a name="anatomy-of-an-aspnet-core-application"></a><span data-ttu-id="955ca-155">Анатомия приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="955ca-155">Anatomy of an ASP.NET Core application</span></span>

<span data-ttu-id="955ca-156">Теперь у вас есть готовое приложение. Давайте на его примере рассмотрим реализацию функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="955ca-156">Now that you've built the application, let's look at how this functionality is implemented.</span></span> <span data-ttu-id="955ca-157">Из созданных файлов приложения нам пока наиболее интересны вот эти два: WeatherMicroservice.csproj и Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="955ca-157">There are two of the generated files that are particularly interesting at this point: WeatherMicroservice.csproj and Startup.cs.</span></span> 

<span data-ttu-id="955ca-158">CSPROJ-файл содержит сведения о проекте.</span><span class="sxs-lookup"><span data-stu-id="955ca-158">The .csproj file contains information about the project.</span></span>
<span data-ttu-id="955ca-159">Нас интересуют два узла: `<TargetFramework>` и `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="955ca-159">The two nodes that are most interesting are `<TargetFramework>` and `<PackageReference>`.</span></span>

<span data-ttu-id="955ca-160">Узел `<TargetFramework>` определяет версию .NET, где будет выполняться это приложение.</span><span class="sxs-lookup"><span data-stu-id="955ca-160">The `<TargetFramework>` node specifies the version of .NET that will run this application.</span></span>

<span data-ttu-id="955ca-161">Каждый узел `<PackageReference>` используется для указания пакета, который необходим для этого приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-161">Each `<PackageReference>` node is used to specify a package that is needed for this application.</span></span>

<span data-ttu-id="955ca-162">Само приложение реализовано в файле Startup.cs.</span><span class="sxs-lookup"><span data-stu-id="955ca-162">The application is implemented in Startup.cs.</span></span> <span data-ttu-id="955ca-163">Этот файл содержит класс Startup.</span><span class="sxs-lookup"><span data-stu-id="955ca-163">This file contains the startup class.</span></span>

<span data-ttu-id="955ca-164">Инфраструктура ASP.NET Core вызывает два метода этого класса для настройки и запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-164">The two methods are called by the ASP.NET Core infrastructure to configure and run the application.</span></span> <span data-ttu-id="955ca-165">Метод `ConfigureServices` описывает службы, которые необходимы для приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-165">The `ConfigureServices` method describes the services that are necessary for this application.</span></span> <span data-ttu-id="955ca-166">Наша служба не использует никакие ресурсы, и для нее не нужны никакие зависимости.</span><span class="sxs-lookup"><span data-stu-id="955ca-166">You're building a lean microservice, so it doesn't need to configure any dependencies.</span></span> <span data-ttu-id="955ca-167">Метод `Configure` настраивает обработчики для входящих HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="955ca-167">The `Configure` method configures the handlers for incoming HTTP Requests.</span></span> <span data-ttu-id="955ca-168">Шаблон создает простой обработчик, который в ответ на любой запрос возвращает текст "Hello World!".</span><span class="sxs-lookup"><span data-stu-id="955ca-168">The template generates a simple handler that responds to any request with the text 'Hello World!'.</span></span>

## <a name="build-a-microservice"></a><span data-ttu-id="955ca-169">Сборка микрослужбы</span><span class="sxs-lookup"><span data-stu-id="955ca-169">Build a microservice</span></span>

<span data-ttu-id="955ca-170">Служба, которую вы разрабатываете, будет доставлять сведения о погоде в любой точке земного шара.</span><span class="sxs-lookup"><span data-stu-id="955ca-170">The service you're going to build will deliver weather reports from anywhere around the globe.</span></span> <span data-ttu-id="955ca-171">В рабочем приложении вы будете обращаться к реальным службам для получения данных о погоде.</span><span class="sxs-lookup"><span data-stu-id="955ca-171">In a production application, you'd call some service to retrieve weather data.</span></span> <span data-ttu-id="955ca-172">Но для этого примера нам достаточно создать случайный прогноз погоды.</span><span class="sxs-lookup"><span data-stu-id="955ca-172">For our sample, we'll generate a random weather forecast.</span></span> 

<span data-ttu-id="955ca-173">Чтобы получить его, мы выполним несколько задач:</span><span class="sxs-lookup"><span data-stu-id="955ca-173">There are a number of tasks you'll need to perform in order to implement our random weather service:</span></span>

* <span data-ttu-id="955ca-174">синтаксический анализ входящего запроса для получения широты и долготы;</span><span class="sxs-lookup"><span data-stu-id="955ca-174">Parse the incoming request to read the latitude and longitude.</span></span>
* <span data-ttu-id="955ca-175">создание случайных данных для прогноза;</span><span class="sxs-lookup"><span data-stu-id="955ca-175">Generate some random forecast data.</span></span>
* <span data-ttu-id="955ca-176">преобразование случайных данных прогноза из объектов C# в пакеты JSON;</span><span class="sxs-lookup"><span data-stu-id="955ca-176">Convert that random forecast data from C# objects into JSON packets.</span></span>
* <span data-ttu-id="955ca-177">установка заголовка ответа, который будет обозначать отправку данных в формате JSON;</span><span class="sxs-lookup"><span data-stu-id="955ca-177">Set the response header to indicate that your service sends back JSON.</span></span>
* <span data-ttu-id="955ca-178">создание текста ответа.</span><span class="sxs-lookup"><span data-stu-id="955ca-178">Write the response.</span></span>

<span data-ttu-id="955ca-179">В следующем разделе описаны шаги для выполнения каждой из этих задач.</span><span class="sxs-lookup"><span data-stu-id="955ca-179">The next sections walk you through each of these steps.</span></span>

### <a name="parsing-the-query-string"></a><span data-ttu-id="955ca-180">Синтаксический анализ строки запроса</span><span class="sxs-lookup"><span data-stu-id="955ca-180">Parsing the Query String</span></span>

<span data-ttu-id="955ca-181">Прежде всего нужно выполнить синтаксический анализ строки запроса.</span><span class="sxs-lookup"><span data-stu-id="955ca-181">You'll begin by parsing the query string.</span></span> <span data-ttu-id="955ca-182">Служба будет принимать в строке запроса аргументы lat и long в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="955ca-182">The service will accept 'lat' and 'long' arguments on the query string in this form:</span></span>

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

<span data-ttu-id="955ca-183">Все изменения, которые нужно выполнить, относятся к лямбда-выражению, которое определено в классе запуска в качестве аргумента для метода `app.Run`.</span><span class="sxs-lookup"><span data-stu-id="955ca-183">All the changes you need to make are in the lambda expression defined as the argument to `app.Run` in your startup class.</span></span>

<span data-ttu-id="955ca-184">В лямбда-выражении нас интересует аргумент `HttpContext`, представляющий запрос.</span><span class="sxs-lookup"><span data-stu-id="955ca-184">The argument on the lambda expression is the `HttpContext` for the request.</span></span> <span data-ttu-id="955ca-185">Одним из его свойств является объект `Request`.</span><span class="sxs-lookup"><span data-stu-id="955ca-185">One of its properties is the `Request` object.</span></span> <span data-ttu-id="955ca-186">Объект `Request` имеет свойство `Query`, которое содержит словарь всех значений, переданных в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="955ca-186">The `Request` object has a `Query` property that contains a dictionary of all the values on the query string for the request.</span></span> <span data-ttu-id="955ca-187">Сначала добавьте строки для поиска значений широты и долготы:</span><span class="sxs-lookup"><span data-stu-id="955ca-187">The first addition is to find the latitude and longitude values:</span></span>

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

<span data-ttu-id="955ca-188">Словарные значения `Query` имеют тип `StringValue`.</span><span class="sxs-lookup"><span data-stu-id="955ca-188">The `Query` dictionary values are `StringValue` type.</span></span> <span data-ttu-id="955ca-189">Этот тип может содержать коллекцию строк.</span><span class="sxs-lookup"><span data-stu-id="955ca-189">That type can contain a collection of strings.</span></span> <span data-ttu-id="955ca-190">Для нашей службы погоды каждое значение должно содержать одну строку.</span><span class="sxs-lookup"><span data-stu-id="955ca-190">For your weather service, each value is a single string.</span></span> <span data-ttu-id="955ca-191">Поэтому в приведенном выше коде мы вызываем метод `FirstOrDefault()`.</span><span class="sxs-lookup"><span data-stu-id="955ca-191">That's why there's the call to `FirstOrDefault()` in the code above.</span></span> 

<span data-ttu-id="955ca-192">Теперь нам нужно преобразовать эти строки в тип Double.</span><span class="sxs-lookup"><span data-stu-id="955ca-192">Next, you need to convert the strings to doubles.</span></span> <span data-ttu-id="955ca-193">Для преобразования строки в значение типа double мы используем метод `double.TryParse()`:</span><span class="sxs-lookup"><span data-stu-id="955ca-193">The method you'll use to convert the string to a double is `double.TryParse()`:</span></span>

```csharp
bool TryParse(string s, out double result);
```

<span data-ttu-id="955ca-194">Этот метод использует параметры вывода C#, чтобы определить возможность преобразования входной строки к типу double.</span><span class="sxs-lookup"><span data-stu-id="955ca-194">This method leverages C# out parameters to indicate if the input string can be converted to a double.</span></span> <span data-ttu-id="955ca-195">Если строка содержит допустимое представление для типа double, метод возвращает значение true, а аргумент `result` содержит преобразованное значение.</span><span class="sxs-lookup"><span data-stu-id="955ca-195">If the string does represent a valid representation for a double, the method returns true, and the `result` argument contains the value.</span></span> <span data-ttu-id="955ca-196">Если строка не представляет допустимого представления для типа double, метод возвращает значение false.</span><span class="sxs-lookup"><span data-stu-id="955ca-196">If the string does not represent a valid double, the method returns false.</span></span>

<span data-ttu-id="955ca-197">Этот API можно дополнить *методом расширения*, который возвращает *тип double, допускающий значение NULL*.</span><span class="sxs-lookup"><span data-stu-id="955ca-197">You can adapt that API with the use of an *extension method* that returns a *nullable double*.</span></span> <span data-ttu-id="955ca-198">*Тип, допускающий значение NULL*, может содержать значения некоторого типа или значение NULL, которое обозначает отсутствие значения.</span><span class="sxs-lookup"><span data-stu-id="955ca-198">A *nullable value type* is a type that represents some value type, and can also hold a missing, or null value.</span></span> <span data-ttu-id="955ca-199">Чтобы использовать тип, допускающий значения NULL, добавьте к объявлению типа символ `?`.</span><span class="sxs-lookup"><span data-stu-id="955ca-199">A nullable type is represented by appending the `?` character to the type declaration.</span></span> 

<span data-ttu-id="955ca-200">Методы расширения представляют собой методы, которые определяются как обычные статические методы, но с модификатором `this` для первого параметра. Такие методы можно вызывать так, как будто они являются членами этого класса.</span><span class="sxs-lookup"><span data-stu-id="955ca-200">Extension methods are methods that are defined as static methods, but by adding the `this` modifier on the first parameter, can be called as though they are members of that class.</span></span> <span data-ttu-id="955ca-201">Методы расширения можно определять только в статических классах.</span><span class="sxs-lookup"><span data-stu-id="955ca-201">Extension methods may only be defined in static classes.</span></span> <span data-ttu-id="955ca-202">Вот пример определения класса с методом расширения для синтаксического анализа:</span><span class="sxs-lookup"><span data-stu-id="955ca-202">Here's the definition of the class containing the extension method for parse:</span></span>

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

<span data-ttu-id="955ca-203">Перед вызовом метода расширения выберите инвариантные язык и региональные параметры:</span><span class="sxs-lookup"><span data-stu-id="955ca-203">Before calling the extension method, change the current culture to invariant:</span></span>

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

<span data-ttu-id="955ca-204">Таким образом, ваше приложение будет одинаково анализировать числа на любом сервере независимо от языка и региональных параметров по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="955ca-204">This ensures that your application parses numbers the same on any server, regardless of its default culture.</span></span>

<span data-ttu-id="955ca-205">Теперь этот метод расширения можно использовать для преобразования аргументов строки запроса в тип double:</span><span class="sxs-lookup"><span data-stu-id="955ca-205">Now you can use the extension method to convert the query string arguments into the double type:</span></span>

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

<span data-ttu-id="955ca-206">Чтобы быстро проверить работу кода для синтаксического анализа, включите значения аргументов в возвращаемый ответ:</span><span class="sxs-lookup"><span data-stu-id="955ca-206">To easily test the parsing code, update the response to include the values of the arguments:</span></span>

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

<span data-ttu-id="955ca-207">На этом этапе можно запустить веб-приложение и убедиться, работает ли код для синтаксического анализа.</span><span class="sxs-lookup"><span data-stu-id="955ca-207">At this point, you can run the web application and see if your parsing code is working.</span></span> <span data-ttu-id="955ca-208">В строке запроса браузера добавьте какие-либо значения, обновите страницу и убедитесь, что они правильно возвращаются.</span><span class="sxs-lookup"><span data-stu-id="955ca-208">Add values to the web request in a browser, and you should see the updated results.</span></span>

### <a name="build-a-random-weather-forecast"></a><span data-ttu-id="955ca-209">Создание случайного прогноза погоды</span><span class="sxs-lookup"><span data-stu-id="955ca-209">Build a random weather forecast</span></span>

<span data-ttu-id="955ca-210">Теперь мы переходим к созданию случайного прогноза погоды.</span><span class="sxs-lookup"><span data-stu-id="955ca-210">Your next task is to build a random weather forecast.</span></span> <span data-ttu-id="955ca-211">Для этого нам в первую очередь нужен контейнер, который содержит значения для прогноза погоды:</span><span class="sxs-lookup"><span data-stu-id="955ca-211">Let's start with a data container that holds the values you'd want for a weather forecast:</span></span>

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

<span data-ttu-id="955ca-212">Теперь создайте конструктор, который задает эти значения случайным образом.</span><span class="sxs-lookup"><span data-stu-id="955ca-212">Next, build a constructor that randomly sets those values.</span></span> <span data-ttu-id="955ca-213">Этот конструктор использует значения широты и долготы в качестве начального значения для генератора чисел `Random`.</span><span class="sxs-lookup"><span data-stu-id="955ca-213">This constructor uses the values for the latitude and longitude to seed the `Random` number generator.</span></span> <span data-ttu-id="955ca-214">Это означает, что для каждого набора координат всегда будет возвращаться одинаковый прогноз.</span><span class="sxs-lookup"><span data-stu-id="955ca-214">That means the forecast for the same location is the same.</span></span> <span data-ttu-id="955ca-215">Если вы измените значения для аргументов широты и долготы, вы получите другой прогноз (поскольку начальное значение для генератора случайных чисел будет другим).</span><span class="sxs-lookup"><span data-stu-id="955ca-215">If you change the arguments for the latitude and longitude, you'll get a different forecast (because you start with a different seed).</span></span>

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

<span data-ttu-id="955ca-216">Создайте в методе ответа прогноз на 5 дней:</span><span class="sxs-lookup"><span data-stu-id="955ca-216">You can now generate the 5-day forecast in your response method:</span></span>

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a><span data-ttu-id="955ca-217">Оформление ответа в формате JSON</span><span class="sxs-lookup"><span data-stu-id="955ca-217">Build the JSON response</span></span>

<span data-ttu-id="955ca-218">Последней задачей, которую выполняет код на сервере, будет преобразование списка `WeatherReport` в документ JSON и отправка этого пакета клиенту.</span><span class="sxs-lookup"><span data-stu-id="955ca-218">The final code task on the server is to convert the `WeatherReport` list into JSON document, and send that back to the client.</span></span> <span data-ttu-id="955ca-219">Здесь нам нужно сначала создать документ JSON.</span><span class="sxs-lookup"><span data-stu-id="955ca-219">Let's start by creating the JSON document.</span></span> <span data-ttu-id="955ca-220">В список зависимостей добавьте сериализатор Newtonsoft JSON.</span><span class="sxs-lookup"><span data-stu-id="955ca-220">You'll add the Newtonsoft JSON serializer to the list of dependencies.</span></span> <span data-ttu-id="955ca-221">Для этого используйте команду `dotnet`:</span><span class="sxs-lookup"><span data-stu-id="955ca-221">You can do that using the following `dotnet` command:</span></span>

```console
dotnet add package Newtonsoft.Json
```

<span data-ttu-id="955ca-222">Теперь примените класс `JsonConvert`, чтобы преобразовать наш объект в строку:</span><span class="sxs-lookup"><span data-stu-id="955ca-222">Then, you can use the `JsonConvert` class to write the object to a string:</span></span>

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

<span data-ttu-id="955ca-223">Приведенный выше код преобразует объект прогноза (список объектов `WeatherForecast`) в документ JSON.</span><span class="sxs-lookup"><span data-stu-id="955ca-223">The code above converts the forecast object (a list of `WeatherForecast` objects) into a JSON document.</span></span> <span data-ttu-id="955ca-224">Когда документ с ответом будет готов, укажите для него тип содержимого `application/json` и возвратите строку.</span><span class="sxs-lookup"><span data-stu-id="955ca-224">After you've constructed the response document, you set the content type to `application/json`, and write the string.</span></span>

<span data-ttu-id="955ca-225">Теперь наше приложение создает и возвращает случайные прогнозы погоды.</span><span class="sxs-lookup"><span data-stu-id="955ca-225">The application now runs and returns random forecasts.</span></span>

## <a name="build-a-docker-image"></a><span data-ttu-id="955ca-226">Создание образа Docker</span><span class="sxs-lookup"><span data-stu-id="955ca-226">Build a Docker image</span></span>

<span data-ttu-id="955ca-227">Последней задачей в этой статье будет запуск приложения в Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-227">Our final task is to run the application in Docker.</span></span> <span data-ttu-id="955ca-228">Мы создадим контейнер Docker, который выполняет образ Docker с созданным ранее приложением.</span><span class="sxs-lookup"><span data-stu-id="955ca-228">We'll create a Docker container that runs a Docker image that represents our application.</span></span>

<span data-ttu-id="955ca-229">Объект ***образа Docker*** — это файл, который определяет среду для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-229">A ***Docker Image*** is a file that defines the environment for running the application.</span></span>

<span data-ttu-id="955ca-230">***Контейнер Docker*** представляет запущенный экземпляр образа Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-230">A ***Docker Container*** represents a running instance of a Docker Image.</span></span>

<span data-ttu-id="955ca-231">Для упрощения понимания вы можете представить *образ Docker* как *класс*, а *контейнер Docker* — как объект или экземпляр этого класса.</span><span class="sxs-lookup"><span data-stu-id="955ca-231">By analogy, you can think of the *Docker Image* as a *class*, and the *Docker Container* as an object, or an instance of that class.</span></span>  

<span data-ttu-id="955ca-232">Следующий файл Dockerfile будет использоваться для наших целей:</span><span class="sxs-lookup"><span data-stu-id="955ca-232">The following Dockerfile will serve for our purposes:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="955ca-233">Давайте изучим его содержимое.</span><span class="sxs-lookup"><span data-stu-id="955ca-233">Let's go over its contents.</span></span>

<span data-ttu-id="955ca-234">Первая строка задает источник образа, используемого для сборки приложения:</span><span class="sxs-lookup"><span data-stu-id="955ca-234">The first line specifies the source image used for building the application:</span></span>

```
FROM microsoft/dotnet:2.1-sdk AS build
```

<span data-ttu-id="955ca-235">Docker позволяет настроить образ компьютера на основе исходного шаблона.</span><span class="sxs-lookup"><span data-stu-id="955ca-235">Docker allows you to configure a machine image based on a source template.</span></span> <span data-ttu-id="955ca-236">Это значит, что при запуске вам не придется указывать все параметры компьютера. Достаточно указать лишь изменения параметров, если они потребуются.</span><span class="sxs-lookup"><span data-stu-id="955ca-236">That means you don't have to supply all the machine parameters when you start, you only need to supply any changes.</span></span> <span data-ttu-id="955ca-237">Здесь таким изменением станет запуск нашего приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-237">The changes here will be to include our application.</span></span>

<span data-ttu-id="955ca-238">В этом примере мы будем использовать версию `2.1-sdk` образа `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="955ca-238">In this sample, we'll use the `2.1-sdk` version of the `dotnet` image.</span></span> <span data-ttu-id="955ca-239">Это самый простой способ создать рабочую среду Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-239">This is the easiest way to create a working Docker environment.</span></span> <span data-ttu-id="955ca-240">Этот образ содержит среду выполнения .NET Core и пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-240">This image includes the .NET Core runtime, and the .NET Core SDK.</span></span>
<span data-ttu-id="955ca-241">Это упрощает начало работы и сборку, но приводит к созданию более крупного образа, поэтому мы будем использовать этот образ для сборки приложения, а для запуска возьмем другой образ.</span><span class="sxs-lookup"><span data-stu-id="955ca-241">That makes it easier to get started and build, but does create a larger image, so we'll use this image for building the application and a different image to run it.</span></span>

<span data-ttu-id="955ca-242">Следующие строки выполняют настройку и сборку приложения:</span><span class="sxs-lookup"><span data-stu-id="955ca-242">The next lines setup and build your application:</span></span>

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

<span data-ttu-id="955ca-243">Здесь файл проекта копируется из текущего каталога на виртуальную машину Docker, а также восстанавливаются все пакеты.</span><span class="sxs-lookup"><span data-stu-id="955ca-243">This will copy the project file from the  current directory to the Docker VM, and restore all the packages.</span></span> <span data-ttu-id="955ca-244">Мы используем Dotnet CLI, а значит образ Docker должен включать пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-244">Using the dotnet CLI means that the Docker image must include the .NET Core SDK.</span></span> <span data-ttu-id="955ca-245">После этого копируется остальная часть приложения, а команда `dotnet
publish` выполняет сборку и упаковку приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-245">After that, the rest of your application gets copied, and the `dotnet
publish` command builds and packages your application.</span></span>

<span data-ttu-id="955ca-246">Наконец, мы создадим второй образ Docker, который запустит приложение:</span><span class="sxs-lookup"><span data-stu-id="955ca-246">Finally, we create a second Docker image that runs the application:</span></span>

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

<span data-ttu-id="955ca-247">Этот образ использует версию `2.1-aspnetcore-runtime` образа `dotnet`, который содержит все компоненты, необходимые для запуска приложений ASP.NET Core, но не включает пакет SDK для .NET Core.</span><span class="sxs-lookup"><span data-stu-id="955ca-247">This image uses the `2.1-aspnetcore-runtime` version of the `dotnet` image, which contains everything necessary to run ASP.NET Core applications, but does not include the .NET Core SDK.</span></span> <span data-ttu-id="955ca-248">Это означает, что этот образ не может использоваться для сборки приложений .NET Core, но он позволяет уменьшить размер окончательного образа.</span><span class="sxs-lookup"><span data-stu-id="955ca-248">This means this image can't be used to build .NET Core applications, but it also makes the final image smaller.</span></span>

<span data-ttu-id="955ca-249">Для этого мы копируем собранное приложение из первого образа во второй.</span><span class="sxs-lookup"><span data-stu-id="955ca-249">To make this work, we copy the built application from the first image to the second one.</span></span>

<span data-ttu-id="955ca-250">Команда `ENTRYPOINT` сообщает Docker, какая команда запускает службу.</span><span class="sxs-lookup"><span data-stu-id="955ca-250">The `ENTRYPOINT` command informs Docker what command starts the service.</span></span>

## <a name="building-and-running-the-image-in-a-container"></a><span data-ttu-id="955ca-251">Сборка и выполнение образа в контейнере</span><span class="sxs-lookup"><span data-stu-id="955ca-251">Building and running the image in a container</span></span>

<span data-ttu-id="955ca-252">Теперь мы создадим образ и запустим службу в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="955ca-252">Let's build an image and run the service inside a Docker container.</span></span> <span data-ttu-id="955ca-253">Вам не нужно, чтобы в образ копировались все файлы из локального каталога.</span><span class="sxs-lookup"><span data-stu-id="955ca-253">You don't want all the files from your local directory copied into the image.</span></span> <span data-ttu-id="955ca-254">Поэтому приложение следует собирать в контейнере.</span><span class="sxs-lookup"><span data-stu-id="955ca-254">Instead, you'll build the application in the container.</span></span> <span data-ttu-id="955ca-255">Для этого создайте файл `.dockerignore` и перечислите в нем каталоги, которые не нужно копировать в образ.</span><span class="sxs-lookup"><span data-stu-id="955ca-255">You'll create a `.dockerignore` file to specify the directories that are not copied into the image.</span></span> <span data-ttu-id="955ca-256">Например, вам не нужно, чтобы копировались активы сборки.</span><span class="sxs-lookup"><span data-stu-id="955ca-256">You don't want any of the build assets copied.</span></span> <span data-ttu-id="955ca-257">Укажите каталоги для сборки и публикации в файле `.dockerignore`:</span><span class="sxs-lookup"><span data-stu-id="955ca-257">Specify the build and publish directories in the `.dockerignore` file:</span></span>

```
bin/*
obj/*
out/*
```

<span data-ttu-id="955ca-258">Для сборки образа используется команда `docker build`.</span><span class="sxs-lookup"><span data-stu-id="955ca-258">You build the image using the `docker build` command.</span></span> <span data-ttu-id="955ca-259">Выполните следующую команду из каталога, содержащего код приложения.</span><span class="sxs-lookup"><span data-stu-id="955ca-259">Run the following command from the directory containing your code.</span></span>

```console
docker build -t weather-microservice .
```

<span data-ttu-id="955ca-260">Эта команда собирает контейнер изображения, используя информацию из файла Dockerfile.</span><span class="sxs-lookup"><span data-stu-id="955ca-260">This command builds the container image based on all the information in your Dockerfile.</span></span> <span data-ttu-id="955ca-261">Аргумент `-t` содержит тег (имя) для создаваемого образа контейнера.</span><span class="sxs-lookup"><span data-stu-id="955ca-261">The `-t` argument provides a tag, or name, for this container image.</span></span> <span data-ttu-id="955ca-262">В приведенной выше командной строке для контейнера Docker указан тег `weather-microservice`.</span><span class="sxs-lookup"><span data-stu-id="955ca-262">In the command line above, the tag used for the Docker container is `weather-microservice`.</span></span> <span data-ttu-id="955ca-263">Когда завершится выполнение этой команды, у вас будет готовый контейнер для запуска новой службы.</span><span class="sxs-lookup"><span data-stu-id="955ca-263">When this command completes, you have a container ready to run your new service.</span></span> 

<span data-ttu-id="955ca-264">Выполните следующую команду, чтобы запустить созданный контейнер и соответствующую службу:</span><span class="sxs-lookup"><span data-stu-id="955ca-264">Run the following command to start the container and launch your service:</span></span>

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

<span data-ttu-id="955ca-265">Параметр `-d` указывает, что контейнер следует отсоединить от текущего терминала.</span><span class="sxs-lookup"><span data-stu-id="955ca-265">The `-d` option means to run the container detached from the current terminal.</span></span> <span data-ttu-id="955ca-266">Это означает, что вы не увидите выходные данные команды в окне терминала.</span><span class="sxs-lookup"><span data-stu-id="955ca-266">That means you won't see the command output in your terminal.</span></span> <span data-ttu-id="955ca-267">Параметр `-p` настраивает сопоставление портов между службой и узлом.</span><span class="sxs-lookup"><span data-stu-id="955ca-267">The `-p` option indicates the port mapping between the service and the host.</span></span> <span data-ttu-id="955ca-268">В этом примере все входящие запросы на порт 80 будут перенаправляться на порт контейнера 80.</span><span class="sxs-lookup"><span data-stu-id="955ca-268">Here it says that any incoming request on port 80 should be forwarded to port 80 on the container.</span></span> <span data-ttu-id="955ca-269">Мы используем порт 80, потому что он совпадает с портом, от которого ваша служба ожидает передачи данных. Это порт по умолчанию для приложений в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="955ca-269">Using 80 matches the port your service is listening on, which is the default port for production applications.</span></span> <span data-ttu-id="955ca-270">Аргумент `--name` задает имя для выполняемого контейнера.</span><span class="sxs-lookup"><span data-stu-id="955ca-270">The `--name` argument names your running container.</span></span> <span data-ttu-id="955ca-271">Здесь вы можете указать любое удобное для вас имя, которое упростит работу с этим контейнером.</span><span class="sxs-lookup"><span data-stu-id="955ca-271">It's a convenient name you can use to work with that container.</span></span>

<span data-ttu-id="955ca-272">С помощью следующей команды вы можете проверить, выполняется ли образ:</span><span class="sxs-lookup"><span data-stu-id="955ca-272">You can see if the image is running by checking the command:</span></span>

```console
docker ps
```

<span data-ttu-id="955ca-273">Если контейнер работает, вы увидите строку с его именем в списке запущенных процессов.</span><span class="sxs-lookup"><span data-stu-id="955ca-273">If your container is running, you'll see a line that lists it in the running processes.</span></span> <span data-ttu-id="955ca-274">(Возможно, это будет единственная строка в этом списке.)</span><span class="sxs-lookup"><span data-stu-id="955ca-274">(It may be the only one.)</span></span>

<span data-ttu-id="955ca-275">Вы можете проверить работу вашей службы, открыв локальный адрес localhost в окне браузера и введя значения для широты и долготы:</span><span class="sxs-lookup"><span data-stu-id="955ca-275">You can test your service by opening a browser and navigating to localhost, and specifying a latitude and longitude:</span></span>

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a><span data-ttu-id="955ca-276">Присоединение к работающему контейнеру</span><span class="sxs-lookup"><span data-stu-id="955ca-276">Attaching to a running container</span></span>

<span data-ttu-id="955ca-277">Когда вы запускали службу в командном окне, для каждого запроса вы получали диагностические сведения.</span><span class="sxs-lookup"><span data-stu-id="955ca-277">When you ran your service in a command window, you could see diagnostic information printed for each request.</span></span> <span data-ttu-id="955ca-278">Теперь, когда контейнер работает в отсоединенном режиме, вы больше не видите эту информацию.</span><span class="sxs-lookup"><span data-stu-id="955ca-278">You don't see that information when your container is running in detached mode.</span></span> <span data-ttu-id="955ca-279">Команда Docker attach дает возможность присоединиться к выполняющемуся контейнеру, чтобы просмотреть данные журнала.</span><span class="sxs-lookup"><span data-stu-id="955ca-279">The Docker attach command enables you to attach to a running container so that you can see the log information.</span></span>  <span data-ttu-id="955ca-280">В окне командной строки выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="955ca-280">Run this command from a command window:</span></span>

```console
docker attach --sig-proxy=false hello-docker
```

<span data-ttu-id="955ca-281">Аргумент `--sig-proxy=false` означает, что команды <kbd>Ctrl</kbd>+<kbd>C</kbd> не передаются в процесс контейнера, а просто останавливают выполнение команды `docker attach`.</span><span class="sxs-lookup"><span data-stu-id="955ca-281">The `--sig-proxy=false` argument means that <kbd>Ctrl</kbd>+<kbd>C</kbd> commands do not get sent to the container process, but rather stop the `docker attach` command.</span></span> <span data-ttu-id="955ca-282">Последний аргумент обозначает имя, присвоенное контейнеру ранее, при выполнении команды `docker run`.</span><span class="sxs-lookup"><span data-stu-id="955ca-282">The final argument is the name given to the container in the `docker run` command.</span></span> 

> [!NOTE]
> <span data-ttu-id="955ca-283">Также для ссылки на любой контейнер вы можете использовать назначенный Docker идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="955ca-283">You can also use the Docker assigned container ID to refer to any container.</span></span> <span data-ttu-id="955ca-284">Если в команде `docker run` не указано имя контейнера, необходимо использовать идентификатор контейнера.</span><span class="sxs-lookup"><span data-stu-id="955ca-284">If you didn't specify a name for your container in `docker run` you must use the container ID.</span></span>

<span data-ttu-id="955ca-285">Откройте браузер и перейдите к адресу вашей службы.</span><span class="sxs-lookup"><span data-stu-id="955ca-285">Open a browser and navigate to your service.</span></span> <span data-ttu-id="955ca-286">В командном окне вы увидите диагностические сообщения, генерируемые присоединенным контейнером.</span><span class="sxs-lookup"><span data-stu-id="955ca-286">You'll see the diagnostic messages in the command windows from the attached running container.</span></span>

<span data-ttu-id="955ca-287">Чтобы остановить этот процесс, нажмите <kbd>Ctrl</kbd>+<kbd>C</kbd>.</span><span class="sxs-lookup"><span data-stu-id="955ca-287">Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the attach process.</span></span>

<span data-ttu-id="955ca-288">Когда вы завершите работу с контейнером, его можно остановить:</span><span class="sxs-lookup"><span data-stu-id="955ca-288">When you are done working with your container, you can stop it:</span></span>

```console
docker stop hello-docker
```

<span data-ttu-id="955ca-289">При этом контейнер и образ останутся доступны, и их можно запустить заново.</span><span class="sxs-lookup"><span data-stu-id="955ca-289">The container and image is still available for you to restart.</span></span>  <span data-ttu-id="955ca-290">Если вы хотите удалить контейнер с компьютера, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="955ca-290">If you want to remove the container from your machine, you use this command:</span></span>

```console
docker rm hello-docker
```

<span data-ttu-id="955ca-291">Если вы хотите удалить с компьютера все неиспользуемые контейнеры, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="955ca-291">If you want to remove unused images from your machine, you use this command:</span></span>

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a><span data-ttu-id="955ca-292">Заключение</span><span class="sxs-lookup"><span data-stu-id="955ca-292">Conclusion</span></span> 

<span data-ttu-id="955ca-293">В этом руководстве вы создали микрослужбу ASP.NET Core и добавили в нее несколько простых функций.</span><span class="sxs-lookup"><span data-stu-id="955ca-293">In this tutorial, you built an ASP.NET Core microservice, and added a few simple features.</span></span>

<span data-ttu-id="955ca-294">Вы создали образ контейнера Docker для этой службы и запустили его на компьютере.</span><span class="sxs-lookup"><span data-stu-id="955ca-294">You built a Docker container image for that service, and ran that container on your machine.</span></span> <span data-ttu-id="955ca-295">Также вы подключили к службе окно терминала и увидели диагностические сообщения от службы.</span><span class="sxs-lookup"><span data-stu-id="955ca-295">You attached a terminal window to the service, and saw the diagnostic messages from your service.</span></span>

<span data-ttu-id="955ca-296">В процессе изучения вы также узнали, как используются некоторые функции языка C#.</span><span class="sxs-lookup"><span data-stu-id="955ca-296">Along the way, you saw several features of the C# language in action.</span></span>
