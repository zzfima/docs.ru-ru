---
title: "Создание клиента REST с использованием .NET Core"
description: "Это руководство раскроет для вас некоторые возможности .NET Core и языка C#."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.translationtype: Human Translation
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3dcf0204d57861543743fee4de9523231465d24c
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---

# <a name="rest-client"></a><span data-ttu-id="2fb70-104">Клиент REST</span><span class="sxs-lookup"><span data-stu-id="2fb70-104">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="2fb70-105">Вступление</span><span class="sxs-lookup"><span data-stu-id="2fb70-105">Introduction</span></span>
<span data-ttu-id="2fb70-106">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="2fb70-107">Вы познакомитесь со следующими аспектами:</span><span class="sxs-lookup"><span data-stu-id="2fb70-107">You’ll learn:</span></span>
*   <span data-ttu-id="2fb70-108">работа с интерфейсом командной строки (CLI) в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="2fb70-108">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="2fb70-109">обзор возможностей языка C#;</span><span class="sxs-lookup"><span data-stu-id="2fb70-109">An overview of C# Language features.</span></span>
*   <span data-ttu-id="2fb70-110">управление зависимостями с помощью NuGet;</span><span class="sxs-lookup"><span data-stu-id="2fb70-110">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="2fb70-111">взаимодействие по протоколу HTTP;</span><span class="sxs-lookup"><span data-stu-id="2fb70-111">HTTP Communications</span></span>
*   <span data-ttu-id="2fb70-112">обработка информации в формате JSON;</span><span class="sxs-lookup"><span data-stu-id="2fb70-112">Processing JSON information</span></span>
*   <span data-ttu-id="2fb70-113">управление конфигурацией с помощью атрибутов.</span><span class="sxs-lookup"><span data-stu-id="2fb70-113">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="2fb70-114">Вам предстоит создать приложение, которое отправляет запросы HTTP к службе REST на GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fb70-114">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="2fb70-115">Вы будете считывать данные в формате JSON и преобразовывать полученный пакет JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-115">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="2fb70-116">И наконец, вы увидите примеры работы с объектами C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-116">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="2fb70-117">В этом руководстве описано множество функций.</span><span class="sxs-lookup"><span data-stu-id="2fb70-117">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="2fb70-118">Давайте начнем поочередно разбирать их.</span><span class="sxs-lookup"><span data-stu-id="2fb70-118">Let’s build them one by one.</span></span>

<span data-ttu-id="2fb70-119">Если вы хотите поработать с [примером окончательного кода](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) в этом разделе, вы можете его загрузить.</span><span class="sxs-lookup"><span data-stu-id="2fb70-119">If you prefer to follow along with the [final sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="2fb70-120">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="2fb70-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2fb70-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="2fb70-121">Prerequisites</span></span>
<span data-ttu-id="2fb70-122">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fb70-122">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="2fb70-123">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="2fb70-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="2fb70-124">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="2fb70-124">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="2fb70-125">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="2fb70-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="2fb70-126">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="2fb70-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="2fb70-127">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="2fb70-127">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="2fb70-128">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="2fb70-128">Create the Application</span></span>
<span data-ttu-id="2fb70-129">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="2fb70-129">The first step is to create a new application.</span></span> <span data-ttu-id="2fb70-130">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="2fb70-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="2fb70-131">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="2fb70-131">Make that the current directory.</span></span> <span data-ttu-id="2fb70-132">В командной строке введите команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="2fb70-133">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="2fb70-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="2fb70-134">Прежде чем вносить изменения в это приложение, давайте разберем процедуру его запуска.</span><span class="sxs-lookup"><span data-stu-id="2fb70-134">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="2fb70-135">Когда вы создадите приложение, наберите в командной строке команду `dotnet restore`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-135">After creating the application, type `dotnet restore` at the command prompt.</span></span> <span data-ttu-id="2fb70-136">Она запускает процесс восстановления из пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="2fb70-136">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="2fb70-137">NuGet представляет собой диспетчер пакетов для .NET.</span><span class="sxs-lookup"><span data-stu-id="2fb70-137">NuGet is a .NET package manager.</span></span> <span data-ttu-id="2fb70-138">Эта команда загружает все отсутствующие зависимости для проекта.</span><span class="sxs-lookup"><span data-stu-id="2fb70-138">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="2fb70-139">Поскольку мы имеем дело с новым проектом, для него пока не существует зависимостей, поэтому при первом запуске будет загружена только платформа .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fb70-139">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="2fb70-140">После этого первого запуска команду `dotnet restore` нужно будет запускать только после добавления новых зависимых пакетов или при обновлении версий используемых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2fb70-140">After this initial step, you will only need to run `dotnet restore` when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="2fb70-141">Когда завершится восстановление пакетов, запустите `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-141">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="2fb70-142">Эта команда запускает подсистему сборки и создает готовое приложение.</span><span class="sxs-lookup"><span data-stu-id="2fb70-142">This executes the build engine and creates your application.</span></span> <span data-ttu-id="2fb70-143">Теперь можно выполнить команду `dotnet run`, которая запустит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="2fb70-143">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="2fb70-144">Добавление новых зависимостей</span><span class="sxs-lookup"><span data-stu-id="2fb70-144">Adding New Dependencies</span></span>
<span data-ttu-id="2fb70-145">Одна из важнейших миссий .NET Core — снизить размер установки для платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="2fb70-145">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="2fb70-146">Платформа приложений .NET Core содержит только самые распространенные элементы полной версии платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="2fb70-146">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="2fb70-147">Если приложению для выполнения его задач требуются дополнительные библиотеки, их следует добавить в качестве зависимостей в файл проекта C# (*.csproj).</span><span class="sxs-lookup"><span data-stu-id="2fb70-147">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (*.csproj) file.</span></span> <span data-ttu-id="2fb70-148">В нашем примере нужно добавить пакет `System.Runtime.Serialization.Json`, чтобы приложение могло обрабатывать ответы JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-148">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="2fb70-149">Откройте файл проекта `csproj`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-149">Open your `csproj` project file.</span></span> <span data-ttu-id="2fb70-150">Первая строка файла должна выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="2fb70-150">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="2fb70-151">Сразу после этой строки добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="2fb70-151">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="2fb70-152">Большинство редакторов кода предлагает автозавершение для различных версий этих библиотек.</span><span class="sxs-lookup"><span data-stu-id="2fb70-152">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="2fb70-153">Обычно разработчики предпочитают использовать последнюю версию каждого добавляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="2fb70-153">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="2fb70-154">Но при этом важно убедиться в том, что версии всех пакетов соответствуют друг другу и версии платформы приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2fb70-154">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="2fb70-155">После внесения этих изменений снова запустите команду `dotnet restore`, которая установит на компьютер нужный пакет.</span><span class="sxs-lookup"><span data-stu-id="2fb70-155">After you've made these changes, you should run `dotnet restore` again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="2fb70-156">Выполнение веб-запросов</span><span class="sxs-lookup"><span data-stu-id="2fb70-156">Making Web Requests</span></span>
<span data-ttu-id="2fb70-157">Теперь вы готовы получать данные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="2fb70-157">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="2fb70-158">В этом приложении вы будете считывать информацию из [API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="2fb70-158">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="2fb70-159">Давайте, например, получим информацию о проектах под зонтичным брендом [.NET Foundation](http://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="2fb70-159">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="2fb70-160">Для начала вам нужно составить запрос к API GitHub для получения информации о проектах.</span><span class="sxs-lookup"><span data-stu-id="2fb70-160">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="2fb70-161">Вы будете использовать вот эту конечную точку: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span><span class="sxs-lookup"><span data-stu-id="2fb70-161">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="2fb70-162">Вы будете получать все данные об этих проектах, поэтому используйте запрос HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="2fb70-162">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="2fb70-163">Браузер также использует запросы HTTP GET, поэтому вы можете указать этот URL-адрес в адресной строке браузера и увидеть, какие сведения вы будете получать и обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="2fb70-163">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="2fb70-164">Для выполнения веб-запросов используется класс @System.Net.Http.HttpClient.</span><span class="sxs-lookup"><span data-stu-id="2fb70-164">You use the @System.Net.Http.HttpClient class to make web requests.</span></span> <span data-ttu-id="2fb70-165">Как и все современные API-интерфейсы .NET, @System.Net.Http.HttpClient поддерживает для API-интерфейсов длительного выполнения только асинхронные методы.</span><span class="sxs-lookup"><span data-stu-id="2fb70-165">Like all modern .NET APIs, @System.Net.Http.HttpClient supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="2fb70-166">Поэтому вам нужно создать асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="2fb70-166">Start by making an async method.</span></span> <span data-ttu-id="2fb70-167">Реализацию вы будете добавлять постепенно, по мере создания функций приложения.</span><span class="sxs-lookup"><span data-stu-id="2fb70-167">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="2fb70-168">Сначала откройте файл `program.cs`, расположенный в каталоге проекта, и добавьте в класс `Program` следующий метод:</span><span class="sxs-lookup"><span data-stu-id="2fb70-168">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="2fb70-169">В верхней части метода `Main` нужно разместить инструкцию `using`, чтобы компилятор C# распознал тип @System.Threading.Tasks.Task:</span><span class="sxs-lookup"><span data-stu-id="2fb70-169">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the @System.Threading.Tasks.Task type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="2fb70-170">Если сейчас вы выполните сборку проекта, то получите предупреждение для этого метода, поскольку он не содержит ни одного оператора `await`, и поэтому будет выполняться синхронно.</span><span class="sxs-lookup"><span data-stu-id="2fb70-170">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="2fb70-171">Пока это предупреждение можно игнорировать. Операторы `await` здесь появятся по мере заполнения метода.</span><span class="sxs-lookup"><span data-stu-id="2fb70-171">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="2fb70-172">А пока переименуйте пространство имен, определенное в инструкции `namespace`, указав имя `WebAPIClient` вместо имени по умолчанию `ConsoleApp`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-172">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="2fb70-173">Позднее в этом пространстве имен мы определим класс `repo`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-173">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="2fb70-174">Теперь измените метод `Main`, добавив вызов этого метода.</span><span class="sxs-lookup"><span data-stu-id="2fb70-174">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="2fb70-175">Метод `ProcessRepositories` возвращает задачу, до завершения которой выполнение программы не должно прекращаться.</span><span class="sxs-lookup"><span data-stu-id="2fb70-175">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="2fb70-176">Чтобы обеспечить это, используйте метод `Wait`, который блокирует программу и ожидает завершения задачи:</span><span class="sxs-lookup"><span data-stu-id="2fb70-176">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
public static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="2fb70-177">Теперь у вас есть программа, которая работает в асинхронном режиме, но не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2fb70-177">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="2fb70-178">Давайте вернемся к методу `ProcessRepositories` и создадим его первую версию.</span><span class="sxs-lookup"><span data-stu-id="2fb70-178">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    var client = new HttpClient();
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="2fb70-179">Чтобы эта версия успешно компилировалась, необходимо добавить две новые инструкции using в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="2fb70-179">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="2fb70-180">Эта первая версия метода выполняет веб-запрос для чтения списка всех репозиториев в организации dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="2fb70-180">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="2fb70-181">(На сайте gitHub организация .NET Foundation имеет идентификатор dotnet.)</span><span class="sxs-lookup"><span data-stu-id="2fb70-181">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="2fb70-182">Сначала вы создаете новый объект @System.Net.Http.HttpClient.</span><span class="sxs-lookup"><span data-stu-id="2fb70-182">First, you create a new @System.Net.Http.HttpClient.</span></span> <span data-ttu-id="2fb70-183">Он будет обрабатывать запрос и ответы на него.</span><span class="sxs-lookup"><span data-stu-id="2fb70-183">This object handles the request and the responses.</span></span> <span data-ttu-id="2fb70-184">Следующие несколько строк настраивают @System.Net.Http.HttpClient для выполнения запроса.</span><span class="sxs-lookup"><span data-stu-id="2fb70-184">The next few lines set up the @System.Net.Http.HttpClient for this request.</span></span> <span data-ttu-id="2fb70-185">Сначала мы указываем, что он будет принимать ответы GitHub JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-185">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="2fb70-186">Они возвращаются в простом формате JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-186">This format is simply JSON.</span></span> <span data-ttu-id="2fb70-187">Следующая строка добавляет заголовок User Agent ко всем запросам от этого объекта.</span><span class="sxs-lookup"><span data-stu-id="2fb70-187">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="2fb70-188">Кодом сервера GitHub проверяет эти два заголовка, и их наличие необходимо для извлечения сведений из GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fb70-188">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="2fb70-189">Когда вы настроите объект @System.Net.Http.HttpClient, можно выполнить веб-запрос и получить ответ.</span><span class="sxs-lookup"><span data-stu-id="2fb70-189">After you've configured the @System.Net.Http.HttpClient, you make a web request and retrieve the response.</span></span> <span data-ttu-id="2fb70-190">В первой версии используйте удобный метод <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=fullname>.</span><span class="sxs-lookup"><span data-stu-id="2fb70-190">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=fullname> convenience method.</span></span> <span data-ttu-id="2fb70-191">Этот метод запускает задачу для выполнения веб-запроса, а при получении результатов запроса он считывает поток ответа и извлекает из него содержимое.</span><span class="sxs-lookup"><span data-stu-id="2fb70-191">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="2fb70-192">Текст ответа возвращается в формате @System.String.</span><span class="sxs-lookup"><span data-stu-id="2fb70-192">The body of the response is returned as a @System.String.</span></span> <span data-ttu-id="2fb70-193">Эта строка становится доступна после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="2fb70-193">The string is available when the task completes.</span></span> 

<span data-ttu-id="2fb70-194">Последние две строки этого метода ожидают выполнения созданной задачи, а затем выводят ответ в консоль.</span><span class="sxs-lookup"><span data-stu-id="2fb70-194">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="2fb70-195">Выполните сборку приложения и запустите его.</span><span class="sxs-lookup"><span data-stu-id="2fb70-195">Build the app, and run it.</span></span> <span data-ttu-id="2fb70-196">Предупреждение при сборке теперь не отображается, поскольку в методе `ProcessRepositories` есть оператор `await`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-196">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="2fb70-197">В ответ вы получите длинный текст в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-197">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="2fb70-198">Обработка результатов JSON</span><span class="sxs-lookup"><span data-stu-id="2fb70-198">Processing the JSON Result</span></span>

<span data-ttu-id="2fb70-199">Сейчас у вас уже есть код, который получает от веб-сервера ответ и отображает текст из этого ответа.</span><span class="sxs-lookup"><span data-stu-id="2fb70-199">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="2fb70-200">Теперь давайте преобразуем этот ответ JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-200">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="2fb70-201">Сериализатор JSON преобразует данные в формате JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-201">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="2fb70-202">Первым делом следует определить тип класса C# для хранения информации, которую вы извлечете из ответа.</span><span class="sxs-lookup"><span data-stu-id="2fb70-202">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="2fb70-203">Мы будем создавать код постепенно, и начнем с простого типа C#, который содержит имя репозитория:</span><span class="sxs-lookup"><span data-stu-id="2fb70-203">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class repo
    {
        public string name;
    }
}
``` 

<span data-ttu-id="2fb70-204">Поместите приведенный выше код в новый файл с именем repo.cs.</span><span class="sxs-lookup"><span data-stu-id="2fb70-204">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="2fb70-205">Эта версия класса реализует простейший способ обработки данных JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-205">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="2fb70-206">Имя класса и имя элемента совпадают с именами, используемыми в пакете JSON, и не соответствуют соглашениям C# об именовании.</span><span class="sxs-lookup"><span data-stu-id="2fb70-206">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="2fb70-207">Чтобы исправить это, мы позже добавим некоторые атрибуты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2fb70-207">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="2fb70-208">Этот класс демонстрирует еще одну важную возможность сериализации и десериализации JSON: не все поля в пакете JSON входят в этот класс.</span><span class="sxs-lookup"><span data-stu-id="2fb70-208">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="2fb70-209">Сериализатор JSON просто игнорирует информацию, которая не входит в используемый тип класса.</span><span class="sxs-lookup"><span data-stu-id="2fb70-209">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="2fb70-210">Такое поведение позволяет легко создавать типы, работающие с любым подмножеством полей из пакета JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-210">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="2fb70-211">Теперь давайте выполним десериализацию созданного типа.</span><span class="sxs-lookup"><span data-stu-id="2fb70-211">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="2fb70-212">Вам потребуется создать объект @System.Runtime.Serialization.Json.DataContractJsonSerializer.</span><span class="sxs-lookup"><span data-stu-id="2fb70-212">You'll need to create a @System.Runtime.Serialization.Json.DataContractJsonSerializer object.</span></span> <span data-ttu-id="2fb70-213">Этот объект должен знать тип среды CLR, которая ожидается для полученного пакета JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-213">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="2fb70-214">Пакет, получаемый от GitHub, содержит последовательность репозиториев, и правильным типом в этом случае будет `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-214">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="2fb70-215">Добавьте следующую строку в метод `ProcessRepositories`:</span><span class="sxs-lookup"><span data-stu-id="2fb70-215">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="2fb70-216">Вы создали два новых пространства имен, и их тоже нужно добавить сюда:</span><span class="sxs-lookup"><span data-stu-id="2fb70-216">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="2fb70-217">Теперь вызовите сериализатор для преобразования пакета JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-217">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="2fb70-218">В методе `ProcessRepositories` замените вызов @System.Net.Http.HttpClient.GetStringAsync(System.String) следующими двумя строками:</span><span class="sxs-lookup"><span data-stu-id="2fb70-218">Replace the call to @System.Net.Http.HttpClient.GetStringAsync(System.String) in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="2fb70-219">Обратите внимание, что теперь вместо @System.Net.Http.HttpClient.GetStringAsync(System.String) вы используете @System.Net.Http.HttpClient.GetStreamAsync(System.String).</span><span class="sxs-lookup"><span data-stu-id="2fb70-219">Notice that you're now using @System.Net.Http.HttpClient.GetStreamAsync(System.String) instead of @System.Net.Http.HttpClient.GetStringAsync(System.String).</span></span> <span data-ttu-id="2fb70-220">Сериализатор использует в качестве источника поток, а не строку.</span><span class="sxs-lookup"><span data-stu-id="2fb70-220">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="2fb70-221">Мы хотим объяснить вам функции языка C#, которые используются во второй строке представленного выше фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="2fb70-221">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="2fb70-222">В качестве аргумента методу @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) передается выражение `await`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-222">The argument to @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) is an `await` expression.</span></span> <span data-ttu-id="2fb70-223">Выражения await могут использоваться почти в любом месте кода, хотя пока мы их применяли только в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="2fb70-223">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="2fb70-224">Во-вторых, оператор `as` преобразует тип `object`, используемый во время компиляции, в `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-224">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="2fb70-225">Объявление оператора @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) гласит, что он возвращает объект типа <xref:System.Object?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="2fb70-225">The declaration of @System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) declares that it returns an object of type <xref:System.Object?displayProperty=fullName>.</span></span> <span data-ttu-id="2fb70-226">@System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) возвращает тип, который вы укажете при конструировании (в нашем примере это тип `List<repo>`).</span><span class="sxs-lookup"><span data-stu-id="2fb70-226">@System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream) will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="2fb70-227">Если преобразование завершается неудачно, оператор `as` возвращает `null`, но не создает исключение.</span><span class="sxs-lookup"><span data-stu-id="2fb70-227">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="2fb70-228">В этом разделе все почти готово.</span><span class="sxs-lookup"><span data-stu-id="2fb70-228">You're almost done with this section.</span></span> <span data-ttu-id="2fb70-229">Вы уже преобразовали JSON в объекты C#, и теперь можете отобразить имена всех репозиториев.</span><span class="sxs-lookup"><span data-stu-id="2fb70-229">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="2fb70-230">Удалите вот эти строки кода:</span><span class="sxs-lookup"><span data-stu-id="2fb70-230">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="2fb70-231">и замените их следующим фрагментом:</span><span class="sxs-lookup"><span data-stu-id="2fb70-231">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="2fb70-232">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="2fb70-232">Compile and run the application.</span></span> <span data-ttu-id="2fb70-233">Вы получите имена всех репозиториев, которые являются частью .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="2fb70-233">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="2fb70-234">Управление сериализацией</span><span class="sxs-lookup"><span data-stu-id="2fb70-234">Controlling Serialization</span></span>

<span data-ttu-id="2fb70-235">Прежде чем добавлять новые возможности, давайте разберемся с типом `repo`, чтобы он соответствовал стандартным соглашениям C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-235">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="2fb70-236">Для этого добавьте к объявлению типа `repo` *атрибуты*, которые управляют работой сериализатора JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-236">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="2fb70-237">В вашем примере эти атрибуты будут определять сопоставление между именами ключей в пакете JSON и именами классов и членов C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-237">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="2fb70-238">Вам понадобятся два атрибута: `DataContract` и `DataMember`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-238">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="2fb70-239">По соглашению, все классы атрибутов завершаются суффиксом `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-239">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="2fb70-240">Но этот суффикс не обязательно указывать, когда вы применяете атрибуты.</span><span class="sxs-lookup"><span data-stu-id="2fb70-240">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="2fb70-241">Атрибуты `DataContract` и `DataMember` атрибуты находятся в другой библиотеке, и эту библиотеку необходимо добавить в файл проекта C# в качестве зависимости.</span><span class="sxs-lookup"><span data-stu-id="2fb70-241">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="2fb70-242">Добавьте следующую строку в раздел `<ItemGroup>` файла проекта:</span><span class="sxs-lookup"><span data-stu-id="2fb70-242">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="2fb70-243">Сохраните файл и выполните команду `dotnet restore`, чтобы скачать этот пакет.</span><span class="sxs-lookup"><span data-stu-id="2fb70-243">After you save the file, run `dotnet restore` to retrieve this package.</span></span>

<span data-ttu-id="2fb70-244">Теперь откройте файл `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-244">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="2fb70-245">Здесь мы хотим изменить имя, чтобы слово `Repository` было представлено в нем целиком и с капитализацией в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="2fb70-245">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="2fb70-246">Но при этом узлы repo из JSON должны по-прежнему сопоставляться с этим типом, так что вам нужно добавить атрибут `DataContract` к объявлению класса.</span><span class="sxs-lookup"><span data-stu-id="2fb70-246">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="2fb70-247">Для этого атрибута должно быть задано свойство `Name` с именем узлов JSON, которые будут сопоставлены с этим типом:</span><span class="sxs-lookup"><span data-stu-id="2fb70-247">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="2fb70-248">Атрибут @System.Runtime.Serialization.DataContractAttribute входит в пространство имен @System.Runtime.Serialization, поэтому вам потребуется соответствующая инструкция `using` в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="2fb70-248">The @System.Runtime.Serialization.DataContractAttribute is a member of the @System.Runtime.Serialization namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="2fb70-249">Имя класса изменилось с `repo` на `Repository`, а значит аналогичные изменения нужно внести в файл Program.cs (некоторые редакторы поддерживают рефакторинг путем переименования, при котором все нужные изменения будут применены автоматически).</span><span class="sxs-lookup"><span data-stu-id="2fb70-249">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="2fb70-250">Теперь выполните такие же преобразования для поля `name` в классе @System.Runtime.Serialization.DataMemberAttribute.</span><span class="sxs-lookup"><span data-stu-id="2fb70-250">Next, let's make the same change with the `name` field by using the @System.Runtime.Serialization.DataMemberAttribute class.</span></span> <span data-ttu-id="2fb70-251">В файле repo.cs внесите следующие изменения в объявление `name`:</span><span class="sxs-lookup"><span data-stu-id="2fb70-251">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="2fb70-252">Это изменение требует также изменить код в файле program.cs, который записывает имя каждого хранилища:</span><span class="sxs-lookup"><span data-stu-id="2fb70-252">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="2fb70-253">Выполните `dotnet build`, а затем `dotnet run`, чтобы проверить правильность сопоставления.</span><span class="sxs-lookup"><span data-stu-id="2fb70-253">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="2fb70-254">Результат выполнения должен быть такой же, как прежде.</span><span class="sxs-lookup"><span data-stu-id="2fb70-254">You should see the same output as before.</span></span> <span data-ttu-id="2fb70-255">Прежде чем перейти к обработке дополнительных свойств, полученных от веб-сервера, давайте внесем еще одно изменение в класс `Repository`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-255">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="2fb70-256">Член `Name` является общедоступным полем.</span><span class="sxs-lookup"><span data-stu-id="2fb70-256">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="2fb70-257">Это плохо соотносится с рекомендациями по объектно-ориентированному программированию, поэтому вместо него мы будем использовать свойство.</span><span class="sxs-lookup"><span data-stu-id="2fb70-257">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="2fb70-258">В нашем примере пока не требуется выполнять специальный код при получении или задании свойства, но благодаря такому изменению нам позднее будет проще добавить такой код, не переделывая вызовы класса `Repository`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-258">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="2fb70-259">Удалите определение поля и замените его [автоматически реализуемым свойством](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span><span class="sxs-lookup"><span data-stu-id="2fb70-259">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="2fb70-260">Компилятор создает текст акцессоров `get` и `set`, а также закрытое поле для хранения имени.</span><span class="sxs-lookup"><span data-stu-id="2fb70-260">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="2fb70-261">Этот код будет выглядеть примерно так, как показано ниже. Вы также можете ввести такой код вручную:</span><span class="sxs-lookup"><span data-stu-id="2fb70-261">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="2fb70-262">И еще одно изменение, прежде чем мы начнем добавлять новые функции.</span><span class="sxs-lookup"><span data-stu-id="2fb70-262">Let's make one more change before adding new features.</span></span> <span data-ttu-id="2fb70-263">Метод `ProcessRepositories` может выполнять работу в асинхронном режиме и возвращает коллекцию репозиториев.</span><span class="sxs-lookup"><span data-stu-id="2fb70-263">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="2fb70-264">Давайте сделаем так, чтобы этот метод возвращал `List<Repository>`, а сегмент кода, который записывает информацию, переместим в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-264">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="2fb70-265">Измените сигнатуру `ProcessRepositories`, чтобы этот метод возвращал задачу, результатом которой является список объектов `Repository`:</span><span class="sxs-lookup"><span data-stu-id="2fb70-265">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="2fb70-266">Теперь мы можем просто возвращать репозитории после обработки ответа JSON:</span><span class="sxs-lookup"><span data-stu-id="2fb70-266">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="2fb70-267">Компилятор создает в качестве выходных данных объект `Task<T>`, поскольку этот метод обозначен ключевым словом `async`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-267">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="2fb70-268">Теперь мы изменим метод `Main` так, чтобы он записывает эти результаты и выводил в консоль имя каждого репозитория.</span><span class="sxs-lookup"><span data-stu-id="2fb70-268">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="2fb70-269">Метод `Main` теперь выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="2fb70-269">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="2fb70-270">Доступ к свойству `Result` блокируется, пока не завершится созданная задача.</span><span class="sxs-lookup"><span data-stu-id="2fb70-270">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="2fb70-271">Было бы лучше использовать `await`, чтобы подождать завершения задачи, как мы сделали это в методе `ProcessRepositories`, но это не допускается для метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-271">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="2fb70-272">Получение дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="2fb70-272">Reading More Information</span></span>

<span data-ttu-id="2fb70-273">И в завершении нашего руководства мы обработаем еще несколько свойств, содержащихся в пакете JSON, который отправляется из API GitHub.</span><span class="sxs-lookup"><span data-stu-id="2fb70-273">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="2fb70-274">Нет смысла обрабатывать всю информацию, но добавление нескольких свойств поможет продемонстрировать еще несколько возможностей языка C#.</span><span class="sxs-lookup"><span data-stu-id="2fb70-274">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="2fb70-275">Сначала добавьте еще несколько простых типов в определение класса `Repository`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-275">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="2fb70-276">Добавьте в этот класс следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="2fb70-276">Add these properties to that class:</span></span>

```csharp
[DataMember(Name="description")]
public string Description { get; set; }

[DataMember(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[DataMember(Name="homepage")]
public Uri Homepage { get; set; }

[DataMember(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="2fb70-277">Для этих свойств применяются встроенные преобразования из строкового типа (который используется в пакетах JSON) в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="2fb70-277">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="2fb70-278">Возможно, с типом @System.Uri вы пока не знакомы.</span><span class="sxs-lookup"><span data-stu-id="2fb70-278">The @System.Uri type may be new to you.</span></span> <span data-ttu-id="2fb70-279">Он представляет универсальный код ресурса, например URL-адрес, как в нашем примере.</span><span class="sxs-lookup"><span data-stu-id="2fb70-279">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="2fb70-280">Если вы используете типы `Uri` и `int`, а пакет JSON содержит данные, для которых невозможно выполнить преобразование в целевой тип, действие сериализации создает исключение.</span><span class="sxs-lookup"><span data-stu-id="2fb70-280">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="2fb70-281">Добавив новые типы, включите их в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="2fb70-281">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```
<span data-ttu-id="2fb70-282">На последнем этапе мы добавим сведения о последней операции принудительной отправки.</span><span class="sxs-lookup"><span data-stu-id="2fb70-282">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="2fb70-283">Эта информация представлена в ответе JSON в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="2fb70-283">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="2fb70-284">Он не соответствует ни одному из стандартных форматов .NET для типа @System.DateTime.</span><span class="sxs-lookup"><span data-stu-id="2fb70-284">That format does not follow any of the standard .NET @System.DateTime formats.</span></span> <span data-ttu-id="2fb70-285">Поэтому нам нужен специализированный метод для преобразования.</span><span class="sxs-lookup"><span data-stu-id="2fb70-285">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="2fb70-286">Кроме того, нежелательно предоставлять пользователям класса `Repository` доступ к необработанным строковым данным.</span><span class="sxs-lookup"><span data-stu-id="2fb70-286">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="2fb70-287">И здесь нам снова помогут атрибуты.</span><span class="sxs-lookup"><span data-stu-id="2fb70-287">Attributes can help control that as well.</span></span> <span data-ttu-id="2fb70-288">Во-первых, определите свойство `private`, которое будет содержать строковое представление даты и времени в классе `Repository`:</span><span class="sxs-lookup"><span data-stu-id="2fb70-288">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="2fb70-289">Атрибут `DataMember` сообщает сериализатору, что эти данные нужно обрабатывать, поскольку по умолчанию обрабатываются только открытые члены.</span><span class="sxs-lookup"><span data-stu-id="2fb70-289">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="2fb70-290">Во-вторых, создайте открытое свойство только для чтения, которое преобразует строку в допустимый объект @System.DateTime и возвращает этот объект @System.DateTime:</span><span class="sxs-lookup"><span data-stu-id="2fb70-290">Next, you need to write a public read-only property that converts the string to a valid @System.DateTime object, and returns that @System.DateTime:</span></span>

```csharp
[IgnoreDataMember]
public DateTime LastPush
{
    get
    {
        return DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
    }
}
```

<span data-ttu-id="2fb70-291">Давайте подробнее рассмотрим представленные выше новые конструкции.</span><span class="sxs-lookup"><span data-stu-id="2fb70-291">Let's go over the new constructs above.</span></span> <span data-ttu-id="2fb70-292">Атрибут `IgnoreDataMember` сообщает сериализатору, что этот тип не должен использоваться для чтения или записи в любых объектах JSON.</span><span class="sxs-lookup"><span data-stu-id="2fb70-292">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="2fb70-293">Это свойство содержит только акцессор `get`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-293">This property contains only a `get` accessor.</span></span> <span data-ttu-id="2fb70-294">Метод доступа `set` не существует.</span><span class="sxs-lookup"><span data-stu-id="2fb70-294">There is no `set` accessor.</span></span> <span data-ttu-id="2fb70-295">Именно так в C# определяются свойства *только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="2fb70-295">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="2fb70-296">(Да, вы можете создать в C# даже свойства *только для записи*, но для них трудно найти применение.) Метод @System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider) выполняет анализ строки и создает объект @System.DateTime, используя предоставленный формат даты, а затем добавляет в `DateTime` дополнительные данные, используя объект `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="2fb70-296">(Yes, you can create *write-only* properties in C#, but their value is limited.) The @System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider) method parses a string and creates a @System.DateTime object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="2fb70-297">Если операция анализа завершается неудачей, акцессор этого свойства создает исключение.</span><span class="sxs-lookup"><span data-stu-id="2fb70-297">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="2fb70-298">Чтобы использовать @System.Globalization.CultureInfo.InvariantCulture, необходимо добавить пространство имен @System.Globalization в набор инструкций `using` в файле `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="2fb70-298">To use @System.Globalization.CultureInfo.InvariantCulture, you will need to add the @System.Globalization namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="2fb70-299">Вам осталось только добавить одну инструкцию вывода данных в консоль, и можно будет заново собрать и запустить приложение:</span><span class="sxs-lookup"><span data-stu-id="2fb70-299">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="2fb70-300">Теперь версия вашего приложения должна совпадать с [полной версией примера](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="2fb70-300">Your version should now match the [finished sample](https://github.com/dotnet/docs/tree/master/samples/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="2fb70-301">Заключение</span><span class="sxs-lookup"><span data-stu-id="2fb70-301">Conclusion</span></span>

<span data-ttu-id="2fb70-302">В этом руководстве вы увидели, как правильно выполнять веб-запросы, анализировать результаты и отображать полученные в них свойства.</span><span class="sxs-lookup"><span data-stu-id="2fb70-302">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="2fb70-303">Вы также добавили в свой проект несколько новых пакетов в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="2fb70-303">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="2fb70-304">Еще вы увидели примеры некоторых функций языка C#, которые поддерживают объектно-ориентированный подход.</span><span class="sxs-lookup"><span data-stu-id="2fb70-304">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>


