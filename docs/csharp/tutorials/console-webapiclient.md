---
title: Создание клиента REST с использованием .NET Core
description: Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 8cca71b9b8e09fd26f80d53618a3f1e278e28390
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2018
---
# <a name="rest-client"></a><span data-ttu-id="6543c-104">Клиент REST</span><span class="sxs-lookup"><span data-stu-id="6543c-104">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="6543c-105">Вступление</span><span class="sxs-lookup"><span data-stu-id="6543c-105">Introduction</span></span>
<span data-ttu-id="6543c-106">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-106">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="6543c-107">Вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="6543c-107">You’ll learn:</span></span>
*   <span data-ttu-id="6543c-108">работа с интерфейсом командной строки (CLI) в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="6543c-108">The basics of the .NET Core Command Line Interface (CLI).</span></span>
*   <span data-ttu-id="6543c-109">обзор возможностей языка C#;</span><span class="sxs-lookup"><span data-stu-id="6543c-109">An overview of C# Language features.</span></span>
*   <span data-ttu-id="6543c-110">управление зависимостями с помощью NuGet;</span><span class="sxs-lookup"><span data-stu-id="6543c-110">Managing dependencies with NuGet</span></span>
*   <span data-ttu-id="6543c-111">взаимодействие по протоколу HTTP;</span><span class="sxs-lookup"><span data-stu-id="6543c-111">HTTP Communications</span></span>
*   <span data-ttu-id="6543c-112">обработка информации в формате JSON;</span><span class="sxs-lookup"><span data-stu-id="6543c-112">Processing JSON information</span></span>
*   <span data-ttu-id="6543c-113">управление конфигурацией с помощью атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6543c-113">Managing configuration with Attributes.</span></span> 

<span data-ttu-id="6543c-114">Вам предстоит создать приложение, которое отправляет запросы HTTP к службе REST на GitHub.</span><span class="sxs-lookup"><span data-stu-id="6543c-114">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="6543c-115">Вы будете считывать данные в формате JSON и преобразовывать полученный пакет JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-115">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="6543c-116">И наконец, вы увидите примеры работы с объектами C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-116">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="6543c-117">В этом руководстве описано множество функций.</span><span class="sxs-lookup"><span data-stu-id="6543c-117">There are a lot of features in this tutorial.</span></span> <span data-ttu-id="6543c-118">Давайте начнем поочередно разбирать их.</span><span class="sxs-lookup"><span data-stu-id="6543c-118">Let’s build them one by one.</span></span>

<span data-ttu-id="6543c-119">Если вы хотите поработать с [примером окончательного кода](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) в этом разделе, вы можете его загрузить.</span><span class="sxs-lookup"><span data-stu-id="6543c-119">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="6543c-120">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="6543c-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6543c-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6543c-121">Prerequisites</span></span>
<span data-ttu-id="6543c-122">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6543c-122">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="6543c-123">Инструкции по установке см. на странице [.NET Core](https://www.microsoft.com/net/core).</span><span class="sxs-lookup"><span data-stu-id="6543c-123">You can find the installation instructions on the [.NET Core](https://www.microsoft.com/net/core) page.</span></span> <span data-ttu-id="6543c-124">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="6543c-124">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span> <span data-ttu-id="6543c-125">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="6543c-125">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="6543c-126">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="6543c-126">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="6543c-127">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="6543c-127">However, you can use whatever tools you are comfortable with.</span></span>
## <a name="create-the-application"></a><span data-ttu-id="6543c-128">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="6543c-128">Create the Application</span></span>
<span data-ttu-id="6543c-129">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="6543c-129">The first step is to create a new application.</span></span> <span data-ttu-id="6543c-130">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="6543c-130">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="6543c-131">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="6543c-131">Make that the current directory.</span></span> <span data-ttu-id="6543c-132">В командной строке введите команду `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="6543c-132">Type the command `dotnet new console` at the command prompt.</span></span> <span data-ttu-id="6543c-133">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="6543c-133">This creates the starter files for a basic "Hello World" application.</span></span>

<span data-ttu-id="6543c-134">Прежде чем вносить изменения в это приложение, давайте разберем процедуру его запуска.</span><span class="sxs-lookup"><span data-stu-id="6543c-134">Before you start making modifications, let’s go through the steps to run the simple Hello World application.</span></span> <span data-ttu-id="6543c-135">Когда вы создадите приложение, введите в командной строке `dotnet restore` ([см. примечание](#dotnet-restore-note)).</span><span class="sxs-lookup"><span data-stu-id="6543c-135">After creating the application, type `dotnet restore` ([see note](#dotnet-restore-note)) at the command prompt.</span></span> <span data-ttu-id="6543c-136">Она запускает процесс восстановления из пакета NuGet.</span><span class="sxs-lookup"><span data-stu-id="6543c-136">This command runs the NuGet package restore process.</span></span> <span data-ttu-id="6543c-137">NuGet представляет собой диспетчер пакетов для .NET.</span><span class="sxs-lookup"><span data-stu-id="6543c-137">NuGet is a .NET package manager.</span></span> <span data-ttu-id="6543c-138">Эта команда загружает все отсутствующие зависимости для проекта.</span><span class="sxs-lookup"><span data-stu-id="6543c-138">This command downloads any of the missing dependencies for your project.</span></span> <span data-ttu-id="6543c-139">Поскольку мы имеем дело с новым проектом, для него пока не существует зависимостей, поэтому при первом запуске будет загружена только платформа .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6543c-139">As this is a new project, none of the dependencies are in place, so the first run will download the .NET Core framework.</span></span> <span data-ttu-id="6543c-140">После этого первого запуска команду `dotnet restore` ([см. примечание](#dotnet-restore-note)) нужно будет запускать только при добавлении новых зависимых пакетов или обновлении версий используемых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="6543c-140">After this initial step, you will only need to run `dotnet restore` ([see note](#dotnet-restore-note)) when you add new dependent packages, or update the versions of any of your dependencies.</span></span>  

<span data-ttu-id="6543c-141">Когда завершится восстановление пакетов, запустите `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="6543c-141">After restoring packages, you run `dotnet build`.</span></span> <span data-ttu-id="6543c-142">Эта команда запускает подсистему сборки и создает готовое приложение.</span><span class="sxs-lookup"><span data-stu-id="6543c-142">This executes the build engine and creates your application.</span></span> <span data-ttu-id="6543c-143">Теперь можно выполнить команду `dotnet run`, которая запустит ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="6543c-143">Finally, you execute `dotnet run` to run your application.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="6543c-144">Добавление новых зависимостей</span><span class="sxs-lookup"><span data-stu-id="6543c-144">Adding New Dependencies</span></span>
<span data-ttu-id="6543c-145">Одна из важнейших миссий .NET Core — снизить размер установки для платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="6543c-145">One of the key design goals for .NET Core is to minimize the size of the .NET framework installation.</span></span> <span data-ttu-id="6543c-146">Платформа приложений .NET Core содержит только самые распространенные элементы полной версии платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="6543c-146">The .NET Core Application framework contains only the most common elements of the .NET full framework.</span></span> <span data-ttu-id="6543c-147">Если для каких-то задач приложению нужны дополнительные библиотеки, добавляйте их в качестве зависимостей в файл проекта C# (\*.csproj).</span><span class="sxs-lookup"><span data-stu-id="6543c-147">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="6543c-148">В нашем примере нужно добавить пакет `System.Runtime.Serialization.Json`, чтобы приложение могло обрабатывать ответы JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-148">For our example, you'll need to add the `System.Runtime.Serialization.Json` package so your application can process JSON responses.</span></span>

<span data-ttu-id="6543c-149">Откройте файл проекта `csproj`.</span><span class="sxs-lookup"><span data-stu-id="6543c-149">Open your `csproj` project file.</span></span> <span data-ttu-id="6543c-150">Первая строка файла должна выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="6543c-150">The first line of the file should appear as:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
```

<span data-ttu-id="6543c-151">Сразу после этой строки добавьте следующий код:</span><span class="sxs-lookup"><span data-stu-id="6543c-151">Add the following immediately after this line:</span></span> 

```xml
   <ItemGroup>
      <PackageReference Include="System.Runtime.Serialization.Json" Version="4.3.0" />
   </ItemGroup> 
```
<span data-ttu-id="6543c-152">Большинство редакторов кода предлагает автозавершение для различных версий этих библиотек.</span><span class="sxs-lookup"><span data-stu-id="6543c-152">Most code editors will provide completion for different versions of these libraries.</span></span> <span data-ttu-id="6543c-153">Обычно разработчики предпочитают использовать последнюю версию каждого добавляемого пакета.</span><span class="sxs-lookup"><span data-stu-id="6543c-153">You'll usually want to use the latest version of any package that you add.</span></span> <span data-ttu-id="6543c-154">Но при этом важно убедиться в том, что версии всех пакетов соответствуют друг другу и версии платформы приложений .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6543c-154">However, it is important to make sure that the versions of all packages match, and that they also match the version of the .NET Core Application framework.</span></span>

<span data-ttu-id="6543c-155">После внесения этих изменений снова запустите команду `dotnet restore` ([см. примечание](#dotnet-restore-note)), чтобы установить в системе нужный пакет.</span><span class="sxs-lookup"><span data-stu-id="6543c-155">After you've made these changes, you should run `dotnet restore` ([see note](#dotnet-restore-note)) again so that the package is installed on your system.</span></span>

## <a name="making-web-requests"></a><span data-ttu-id="6543c-156">Выполнение веб-запросов</span><span class="sxs-lookup"><span data-stu-id="6543c-156">Making Web Requests</span></span>
<span data-ttu-id="6543c-157">Теперь вы готовы получать данные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="6543c-157">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="6543c-158">В этом приложении вы будете считывать информацию из [API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="6543c-158">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="6543c-159">Давайте, например, получим информацию о проектах под зонтичным брендом [.NET Foundation](http://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="6543c-159">Let's read information about the projects under the [.NET Foundation](http://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="6543c-160">Для начала вам нужно составить запрос к API GitHub для получения информации о проектах.</span><span class="sxs-lookup"><span data-stu-id="6543c-160">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="6543c-161">Используемая конечная точка: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span><span class="sxs-lookup"><span data-stu-id="6543c-161">The endpoint you'll use is: [https://api.github.com/orgs/dotnet/repos](https://api.github.com/orgs/dotnet/repos).</span></span> <span data-ttu-id="6543c-162">Вы будете получать все данные об этих проектах, поэтому используйте запрос HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="6543c-162">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="6543c-163">Браузер также использует запросы HTTP GET, поэтому вы можете указать этот URL-адрес в адресной строке браузера и увидеть, какие сведения вы будете получать и обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="6543c-163">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="6543c-164">Для выполнения веб-запросов используется класс <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="6543c-164">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="6543c-165">Как и все современные API-интерфейсы .NET, <xref:System.Net.Http.HttpClient> поддерживает для API-интерфейсов длительного выполнения только асинхронные методы.</span><span class="sxs-lookup"><span data-stu-id="6543c-165">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="6543c-166">Поэтому вам нужно создать асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="6543c-166">Start by making an async method.</span></span> <span data-ttu-id="6543c-167">Реализацию вы будете добавлять постепенно, по мере создания функций приложения.</span><span class="sxs-lookup"><span data-stu-id="6543c-167">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="6543c-168">Сначала откройте файл `program.cs`, расположенный в каталоге проекта, и добавьте в класс `Program` следующий метод:</span><span class="sxs-lookup"><span data-stu-id="6543c-168">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    
}
```

<span data-ttu-id="6543c-169">В верхней части метода `Main` нужно разместить инструкцию `using`, чтобы компилятор C# распознал тип <xref:System.Threading.Tasks.Task>:</span><span class="sxs-lookup"><span data-stu-id="6543c-169">You'll need to add a `using` statement at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="6543c-170">Если сейчас вы выполните сборку проекта, то получите предупреждение для этого метода, поскольку он не содержит ни одного оператора `await`, и поэтому будет выполняться синхронно.</span><span class="sxs-lookup"><span data-stu-id="6543c-170">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="6543c-171">Пока это предупреждение можно игнорировать. Операторы `await` здесь появятся по мере заполнения метода.</span><span class="sxs-lookup"><span data-stu-id="6543c-171">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="6543c-172">А пока переименуйте пространство имен, определенное в инструкции `namespace`, указав имя `WebAPIClient` вместо имени по умолчанию `ConsoleApp`.</span><span class="sxs-lookup"><span data-stu-id="6543c-172">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="6543c-173">Позднее в этом пространстве имен мы определим класс `repo`.</span><span class="sxs-lookup"><span data-stu-id="6543c-173">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="6543c-174">Теперь измените метод `Main`, добавив вызов этого метода.</span><span class="sxs-lookup"><span data-stu-id="6543c-174">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="6543c-175">Метод `ProcessRepositories` возвращает задачу, до завершения которой выполнение программы не должно прекращаться.</span><span class="sxs-lookup"><span data-stu-id="6543c-175">The `ProcessRepositories` method returns a Task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="6543c-176">Чтобы обеспечить это, используйте метод `Wait`, который блокирует программу и ожидает завершения задачи:</span><span class="sxs-lookup"><span data-stu-id="6543c-176">Therefore, you must use the `Wait` method to block and wait for the task to finish:</span></span>

```csharp
static void Main(string[] args)
{
    ProcessRepositories().Wait();
}
```

<span data-ttu-id="6543c-177">Теперь у вас есть программа, которая работает в асинхронном режиме, но не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="6543c-177">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="6543c-178">Давайте улучшим ее.</span><span class="sxs-lookup"><span data-stu-id="6543c-178">Let's improve it.</span></span>

<span data-ttu-id="6543c-179">Для начала нужен объект, который может извлечь данные из Интернета. Для этого подойдет <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="6543c-179">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="6543c-180">Он будет обрабатывать запрос и ответы на него.</span><span class="sxs-lookup"><span data-stu-id="6543c-180">This object handles the request and the responses.</span></span> <span data-ttu-id="6543c-181">Создайте один экземпляр этого типа в классе `Program` из файла Program.cs.</span><span class="sxs-lookup"><span data-stu-id="6543c-181">Instantiate a single instance of that type in the `Program` class inside the Program.cs file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static void Main(string[] args)
        {
            //...
        }
    }
}
```

 <span data-ttu-id="6543c-182">Давайте вернемся к методу `ProcessRepositories` и создадим его первую версию.</span><span class="sxs-lookup"><span data-stu-id="6543c-182">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="6543c-183">Чтобы эта версия успешно компилировалась, необходимо добавить две новые инструкции using в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="6543c-183">You'll need to also add two new using statements at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="6543c-184">Эта первая версия метода выполняет веб-запрос для чтения списка всех репозиториев в организации dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="6543c-184">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="6543c-185">(На сайте gitHub организация .NET Foundation имеет идентификатор dotnet.)</span><span class="sxs-lookup"><span data-stu-id="6543c-185">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="6543c-186">Первые несколько строк настраивают <xref:System.Net.Http.HttpClient> для этого запроса.</span><span class="sxs-lookup"><span data-stu-id="6543c-186">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="6543c-187">Сначала мы указываем, что он будет принимать ответы GitHub JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-187">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="6543c-188">Они возвращаются в простом формате JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-188">This format is simply JSON.</span></span> <span data-ttu-id="6543c-189">Следующая строка добавляет заголовок User Agent ко всем запросам от этого объекта.</span><span class="sxs-lookup"><span data-stu-id="6543c-189">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="6543c-190">Кодом сервера GitHub проверяет эти два заголовка, и их наличие необходимо для извлечения сведений из GitHub.</span><span class="sxs-lookup"><span data-stu-id="6543c-190">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="6543c-191">Когда вы настроите объект <xref:System.Net.Http.HttpClient>, можно выполнить веб-запрос и получить ответ.</span><span class="sxs-lookup"><span data-stu-id="6543c-191">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="6543c-192">В первой версии используйте удобный метод <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6543c-192">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="6543c-193">Этот метод запускает задачу для выполнения веб-запроса, а при получении результатов запроса он считывает поток ответа и извлекает из него содержимое.</span><span class="sxs-lookup"><span data-stu-id="6543c-193">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="6543c-194">Текст ответа возвращается в формате <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6543c-194">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="6543c-195">Эта строка становится доступна после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="6543c-195">The string is available when the task completes.</span></span> 

<span data-ttu-id="6543c-196">Последние две строки этого метода ожидают выполнения созданной задачи, а затем выводят ответ в консоль.</span><span class="sxs-lookup"><span data-stu-id="6543c-196">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="6543c-197">Выполните сборку приложения и запустите его.</span><span class="sxs-lookup"><span data-stu-id="6543c-197">Build the app, and run it.</span></span> <span data-ttu-id="6543c-198">Предупреждение при сборке теперь не отображается, поскольку в методе `ProcessRepositories` есть оператор `await`.</span><span class="sxs-lookup"><span data-stu-id="6543c-198">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="6543c-199">В ответ вы получите длинный текст в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-199">You'll see a long display of JSON formatted text.</span></span>   

## <a name="processing-the-json-result"></a><span data-ttu-id="6543c-200">Обработка результатов JSON</span><span class="sxs-lookup"><span data-stu-id="6543c-200">Processing the JSON Result</span></span>

<span data-ttu-id="6543c-201">Сейчас у вас уже есть код, который получает от веб-сервера ответ и отображает текст из этого ответа.</span><span class="sxs-lookup"><span data-stu-id="6543c-201">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="6543c-202">Теперь давайте преобразуем этот ответ JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-202">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="6543c-203">Сериализатор JSON преобразует данные в формате JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-203">The JSON Serializer converts JSON data into C# Objects.</span></span> <span data-ttu-id="6543c-204">Первым делом следует определить тип класса C# для хранения информации, которую вы извлечете из ответа.</span><span class="sxs-lookup"><span data-stu-id="6543c-204">Your first task is to define a C# class type to contain the information you use from this response.</span></span> <span data-ttu-id="6543c-205">Мы будем создавать код постепенно, и начнем с простого типа C#, который содержит имя репозитория:</span><span class="sxs-lookup"><span data-stu-id="6543c-205">Let's build this slowly, so start with a simple C# type that contains the name of the repository:</span></span>

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

<span data-ttu-id="6543c-206">Поместите приведенный выше код в новый файл с именем repo.cs.</span><span class="sxs-lookup"><span data-stu-id="6543c-206">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="6543c-207">Эта версия класса реализует простейший способ обработки данных JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-207">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="6543c-208">Имя класса и имя элемента совпадают с именами, используемыми в пакете JSON, и не соответствуют соглашениям C# об именовании.</span><span class="sxs-lookup"><span data-stu-id="6543c-208">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="6543c-209">Чтобы исправить это, мы позже добавим некоторые атрибуты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6543c-209">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="6543c-210">Этот класс демонстрирует еще одну важную возможность сериализации и десериализации JSON: не все поля в пакете JSON входят в этот класс.</span><span class="sxs-lookup"><span data-stu-id="6543c-210">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="6543c-211">Сериализатор JSON просто игнорирует информацию, которая не входит в используемый тип класса.</span><span class="sxs-lookup"><span data-stu-id="6543c-211">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="6543c-212">Такое поведение позволяет легко создавать типы, работающие с любым подмножеством полей из пакета JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-212">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="6543c-213">Теперь давайте выполним десериализацию созданного типа.</span><span class="sxs-lookup"><span data-stu-id="6543c-213">Now that you've created the type, let's deserialize it.</span></span> <span data-ttu-id="6543c-214">Вам потребуется создать объект <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span><span class="sxs-lookup"><span data-stu-id="6543c-214">You'll need to create a <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> object.</span></span> <span data-ttu-id="6543c-215">Этот объект должен знать тип среды CLR, которая ожидается для полученного пакета JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-215">This object must know the CLR type expected for the JSON packet it retrieves.</span></span> <span data-ttu-id="6543c-216">Пакет, получаемый от GitHub, содержит последовательность репозиториев, и правильным типом в этом случае будет `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="6543c-216">The packet from GitHub contains a sequence of repositories, so a `List<repo>` is the correct type.</span></span> <span data-ttu-id="6543c-217">Добавьте следующую строку в метод `ProcessRepositories`:</span><span class="sxs-lookup"><span data-stu-id="6543c-217">Add the following line to your `ProcessRepositories` method:</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<repo>));
```

<span data-ttu-id="6543c-218">Вы создали два новых пространства имен, и их тоже нужно добавить сюда:</span><span class="sxs-lookup"><span data-stu-id="6543c-218">You're using two new namespaces, so you'll need to add those as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Runtime.Serialization.Json;
```

<span data-ttu-id="6543c-219">Теперь вызовите сериализатор для преобразования пакета JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-219">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="6543c-220">В методе `ProcessRepositories` замените вызов <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> следующими двумя строками.</span><span class="sxs-lookup"><span data-stu-id="6543c-220">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following two lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = serializer.ReadObject(await streamTask) as List<repo>;
```

<span data-ttu-id="6543c-221">Обратите внимание, что теперь вы используете <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> вместо <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="6543c-221">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="6543c-222">Сериализатор использует в качестве источника поток, а не строку.</span><span class="sxs-lookup"><span data-stu-id="6543c-222">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="6543c-223">Мы хотим объяснить вам функции языка C#, которые используются во второй строке представленного выше фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="6543c-223">Let's explain a couple features of the C# language that are being used in the second line above.</span></span> <span data-ttu-id="6543c-224">Аргумент <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> является выражением `await`.</span><span class="sxs-lookup"><span data-stu-id="6543c-224">The argument to <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> is an `await` expression.</span></span> <span data-ttu-id="6543c-225">Выражения await могут использоваться почти в любом месте кода, хотя пока мы их применяли только в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="6543c-225">Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span>

<span data-ttu-id="6543c-226">Во-вторых, оператор `as` преобразует тип `object`, используемый во время компиляции, в `List<repo>`.</span><span class="sxs-lookup"><span data-stu-id="6543c-226">Secondly, the `as` operator converts from the compile time type of `object` to `List<repo>`.</span></span> <span data-ttu-id="6543c-227">Объявление оператора <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> указывает, что он возвращает объект типа <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6543c-227">The declaration of <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> declares that it returns an object of type <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6543c-228"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> возвращает тип, который вы указали при конструировании (в нашем примере это тип `List<repo>`).</span><span class="sxs-lookup"><span data-stu-id="6543c-228"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.ReadObject(System.IO.Stream)> will return the type you specified when you constructed it (`List<repo>` in this tutorial).</span></span> <span data-ttu-id="6543c-229">Если преобразование завершается неудачно, оператор `as` возвращает `null`, но не создает исключение.</span><span class="sxs-lookup"><span data-stu-id="6543c-229">If the conversion does not succeed, the `as` operator evaluates to `null`, instead of throwing an exception.</span></span>

<span data-ttu-id="6543c-230">В этом разделе все почти готово.</span><span class="sxs-lookup"><span data-stu-id="6543c-230">You're almost done with this section.</span></span> <span data-ttu-id="6543c-231">Вы уже преобразовали JSON в объекты C#, и теперь можете отобразить имена всех репозиториев.</span><span class="sxs-lookup"><span data-stu-id="6543c-231">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="6543c-232">Удалите вот эти строки кода:</span><span class="sxs-lookup"><span data-stu-id="6543c-232">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="6543c-233">и замените их следующим фрагментом:</span><span class="sxs-lookup"><span data-stu-id="6543c-233">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="6543c-234">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="6543c-234">Compile and run the application.</span></span> <span data-ttu-id="6543c-235">Вы получите имена всех репозиториев, которые являются частью .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="6543c-235">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="6543c-236">Управление сериализацией</span><span class="sxs-lookup"><span data-stu-id="6543c-236">Controlling Serialization</span></span>

<span data-ttu-id="6543c-237">Прежде чем добавлять новые возможности, давайте разберемся с типом `repo`, чтобы он соответствовал стандартным соглашениям C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-237">Before you add more features, let's address the `repo` type and make it follow more standard C# conventions.</span></span> <span data-ttu-id="6543c-238">Для этого добавьте к объявлению типа `repo` *атрибуты*, которые управляют работой сериализатора JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-238">You'll do this by annotating the `repo` type with *attributes* that control how the JSON Serializer works.</span></span> <span data-ttu-id="6543c-239">В вашем примере эти атрибуты будут определять сопоставление между именами ключей в пакете JSON и именами классов и членов C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-239">In your case, you'll use these attributes to define a mapping between the JSON key names and the C# class and member names.</span></span> <span data-ttu-id="6543c-240">Вам понадобятся два атрибута: `DataContract` и `DataMember`.</span><span class="sxs-lookup"><span data-stu-id="6543c-240">The two attributes used are the `DataContract` attribute and the `DataMember` attribute.</span></span> <span data-ttu-id="6543c-241">По соглашению, все классы атрибутов завершаются суффиксом `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="6543c-241">By convention, all Attribute classes end in the suffix `Attribute`.</span></span> <span data-ttu-id="6543c-242">Но этот суффикс не обязательно указывать, когда вы применяете атрибуты.</span><span class="sxs-lookup"><span data-stu-id="6543c-242">However, you do not need to use that suffix when you apply an attribute.</span></span> 

<span data-ttu-id="6543c-243">Атрибуты `DataContract` и `DataMember` атрибуты находятся в другой библиотеке, и эту библиотеку необходимо добавить в файл проекта C# в качестве зависимости.</span><span class="sxs-lookup"><span data-stu-id="6543c-243">The `DataContract` and `DataMember` attributes are in a different library, so you'll need to add that library to your C# project file as a dependency.</span></span> <span data-ttu-id="6543c-244">Добавьте следующую строку в раздел `<ItemGroup>` файла проекта:</span><span class="sxs-lookup"><span data-stu-id="6543c-244">Add the following line to the `<ItemGroup>` section of your project file:</span></span>

```xml
<PackageReference Include="System.Runtime.Serialization.Primitives" Version="4.3.0" />
```

<span data-ttu-id="6543c-245">Сохраните файл и выполните команду `dotnet restore` ([см. примечание](#dotnet-restore-note)), чтобы получить этот пакет.</span><span class="sxs-lookup"><span data-stu-id="6543c-245">After you save the file, run `dotnet restore` ([see note](#dotnet-restore-note)) to retrieve this package.</span></span>

<span data-ttu-id="6543c-246">Теперь откройте файл `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="6543c-246">Next, open the `repo.cs` file.</span></span> <span data-ttu-id="6543c-247">Здесь мы хотим изменить имя, чтобы слово `Repository` было представлено в нем целиком и с капитализацией в стиле Pascal.</span><span class="sxs-lookup"><span data-stu-id="6543c-247">Let's change the name to use Pascal Case, and fully spell out the name `Repository`.</span></span> <span data-ttu-id="6543c-248">Но при этом узлы repo из JSON должны по-прежнему сопоставляться с этим типом, так что вам нужно добавить атрибут `DataContract` к объявлению класса.</span><span class="sxs-lookup"><span data-stu-id="6543c-248">We still want to map JSON 'repo' nodes to this type, so you'll need to add the `DataContract` attribute to the class declaration.</span></span> <span data-ttu-id="6543c-249">Для этого атрибута должно быть задано свойство `Name` с именем узлов JSON, которые будут сопоставлены с этим типом:</span><span class="sxs-lookup"><span data-stu-id="6543c-249">You'll set the `Name` property of the attribute to the name of the JSON nodes that map to this type:</span></span>

```csharp
[DataContract(Name="repo")]
public class Repository
```

<span data-ttu-id="6543c-250">Атрибут <xref:System.Runtime.Serialization.DataContractAttribute> входит в пространство имен <xref:System.Runtime.Serialization>, поэтому вам потребуется соответствующая инструкция `using` в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="6543c-250">The <xref:System.Runtime.Serialization.DataContractAttribute> is a member of the <xref:System.Runtime.Serialization> namespace, so you'll need to add the appropriate `using` statement at the top of the file:</span></span>

```csharp
using System.Runtime.Serialization;
```

<span data-ttu-id="6543c-251">Имя класса изменилось с `repo` на `Repository`, а значит аналогичные изменения нужно внести в файл Program.cs (некоторые редакторы поддерживают рефакторинг путем переименования, при котором все нужные изменения будут применены автоматически).</span><span class="sxs-lookup"><span data-stu-id="6543c-251">You changed the name of the `repo` class to `Repository`, so you'll need to make the same name change in Program.cs (some editors may support a rename refactoring that will make this change automatically:)</span></span>

```csharp
var serializer = new DataContractJsonSerializer(typeof(List<Repository>));

// ...

var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
```

<span data-ttu-id="6543c-252">Теперь выполните такие же преобразования для поля `name` в классе <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="6543c-252">Next, let's make the same change with the `name` field by using the <xref:System.Runtime.Serialization.DataMemberAttribute> class.</span></span> <span data-ttu-id="6543c-253">В файле repo.cs внесите следующие изменения в объявление `name`:</span><span class="sxs-lookup"><span data-stu-id="6543c-253">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[DataMember(Name="name")]
public string Name;
```

<span data-ttu-id="6543c-254">Это изменение требует также изменить код в файле program.cs, который записывает имя каждого хранилища:</span><span class="sxs-lookup"><span data-stu-id="6543c-254">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="6543c-255">Выполните `dotnet build`, а затем `dotnet run`, чтобы проверить правильность сопоставления.</span><span class="sxs-lookup"><span data-stu-id="6543c-255">Do a `dotnet build` followed by a `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="6543c-256">Результат выполнения должен быть такой же, как прежде.</span><span class="sxs-lookup"><span data-stu-id="6543c-256">You should see the same output as before.</span></span> <span data-ttu-id="6543c-257">Прежде чем перейти к обработке дополнительных свойств, полученных от веб-сервера, давайте внесем еще одно изменение в класс `Repository`.</span><span class="sxs-lookup"><span data-stu-id="6543c-257">Before we process more properties from the web server, let's make one more change to the `Repository` class.</span></span> <span data-ttu-id="6543c-258">Член `Name` является общедоступным полем.</span><span class="sxs-lookup"><span data-stu-id="6543c-258">The `Name` member is a publicly accessible field.</span></span> <span data-ttu-id="6543c-259">Это плохо соотносится с рекомендациями по объектно-ориентированному программированию, поэтому вместо него мы будем использовать свойство.</span><span class="sxs-lookup"><span data-stu-id="6543c-259">That's not a good object-oriented practice, so let's change it to a property.</span></span> <span data-ttu-id="6543c-260">В нашем примере пока не требуется выполнять специальный код при получении или задании свойства, но благодаря такому изменению нам позднее будет проще добавить такой код, не переделывая вызовы класса `Repository`.</span><span class="sxs-lookup"><span data-stu-id="6543c-260">For our purposes, we don't need any specific code to run when getting or setting the property, but changing to a property makes it easier to add those changes later without breaking any code that uses the `Repository` class.</span></span>

<span data-ttu-id="6543c-261">Удалите определение поля и замените его [автоматически реализуемым свойством](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span><span class="sxs-lookup"><span data-stu-id="6543c-261">Remove the field definition, and replace it with an [auto-implemented property](../programming-guide/classes-and-structs/auto-implemented-properties.md):</span></span>

```csharp
public string Name { get; set; }
```

<span data-ttu-id="6543c-262">Компилятор создает текст акцессоров `get` и `set`, а также закрытое поле для хранения имени.</span><span class="sxs-lookup"><span data-stu-id="6543c-262">The compiler generates the body of the `get` and `set` accessors, as well as a private field to store the name.</span></span> <span data-ttu-id="6543c-263">Этот код будет выглядеть примерно так, как показано ниже. Вы также можете ввести такой код вручную:</span><span class="sxs-lookup"><span data-stu-id="6543c-263">It would be similar to the following code that you could type by hand:</span></span>

```csharp
public string Name 
{ 
    get { return this._name; }
    set { this._name = value; }
}
private string _name;
```

<span data-ttu-id="6543c-264">И еще одно изменение, прежде чем мы начнем добавлять новые функции.</span><span class="sxs-lookup"><span data-stu-id="6543c-264">Let's make one more change before adding new features.</span></span> <span data-ttu-id="6543c-265">Метод `ProcessRepositories` может выполнять работу в асинхронном режиме и возвращает коллекцию репозиториев.</span><span class="sxs-lookup"><span data-stu-id="6543c-265">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="6543c-266">Давайте сделаем так, чтобы этот метод возвращал `List<Repository>`, а сегмент кода, который записывает информацию, переместим в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="6543c-266">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="6543c-267">Измените сигнатуру `ProcessRepositories`, чтобы этот метод возвращал задачу, результатом которой является список объектов `Repository`:</span><span class="sxs-lookup"><span data-stu-id="6543c-267">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="6543c-268">Теперь мы можем просто возвращать репозитории после обработки ответа JSON:</span><span class="sxs-lookup"><span data-stu-id="6543c-268">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="6543c-269">Компилятор создает в качестве выходных данных объект `Task<T>`, поскольку этот метод обозначен ключевым словом `async`.</span><span class="sxs-lookup"><span data-stu-id="6543c-269">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="6543c-270">Теперь мы изменим метод `Main` так, чтобы он записывает эти результаты и выводил в консоль имя каждого репозитория.</span><span class="sxs-lookup"><span data-stu-id="6543c-270">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="6543c-271">Метод `Main` теперь выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6543c-271">Your `Main` method now looks like this:</span></span>

```csharp
public static void Main(string[] args)
{
    var repositories = ProcessRepositories().Result;

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

<span data-ttu-id="6543c-272">Доступ к свойству `Result` блокируется, пока не завершится созданная задача.</span><span class="sxs-lookup"><span data-stu-id="6543c-272">Accessing the `Result` property of a Task blocks until the task has completed.</span></span> <span data-ttu-id="6543c-273">Было бы лучше использовать `await`, чтобы подождать завершения задачи, как мы сделали это в методе `ProcessRepositories`, но это не допускается для метода `Main`.</span><span class="sxs-lookup"><span data-stu-id="6543c-273">Normally, you would prefer to `await` the completion of the task, as in the `ProcessRepositories` method, but that isn't allowed in the `Main` method.</span></span>

## <a name="reading-more-information"></a><span data-ttu-id="6543c-274">Получение дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="6543c-274">Reading More Information</span></span>

<span data-ttu-id="6543c-275">И в завершении нашего руководства мы обработаем еще несколько свойств, содержащихся в пакете JSON, который отправляется из API GitHub.</span><span class="sxs-lookup"><span data-stu-id="6543c-275">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="6543c-276">Нет смысла обрабатывать всю информацию, но добавление нескольких свойств поможет продемонстрировать еще несколько возможностей языка C#.</span><span class="sxs-lookup"><span data-stu-id="6543c-276">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="6543c-277">Сначала добавьте еще несколько простых типов в определение класса `Repository`.</span><span class="sxs-lookup"><span data-stu-id="6543c-277">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="6543c-278">Добавьте в этот класс следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="6543c-278">Add these properties to that class:</span></span>

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

<span data-ttu-id="6543c-279">Для этих свойств применяются встроенные преобразования из строкового типа (который используется в пакетах JSON) в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="6543c-279">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="6543c-280">Возможно, с типом <xref:System.Uri> вы пока не знакомы.</span><span class="sxs-lookup"><span data-stu-id="6543c-280">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="6543c-281">Он представляет универсальный код ресурса, например URL-адрес, как в нашем примере.</span><span class="sxs-lookup"><span data-stu-id="6543c-281">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="6543c-282">Если вы используете типы `Uri` и `int`, а пакет JSON содержит данные, для которых невозможно выполнить преобразование в целевой тип, действие сериализации создает исключение.</span><span class="sxs-lookup"><span data-stu-id="6543c-282">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="6543c-283">Добавив новые типы, включите их в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="6543c-283">Once you've added these, update the `Main` method to display those elements:</span></span>

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
<span data-ttu-id="6543c-284">На последнем этапе мы добавим сведения о последней операции принудительной отправки.</span><span class="sxs-lookup"><span data-stu-id="6543c-284">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="6543c-285">Эта информация представлена в ответе JSON в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="6543c-285">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="6543c-286">Он не соответствует ни одному из стандартных форматов .NET для типа <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6543c-286">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="6543c-287">Поэтому нам нужен специализированный метод для преобразования.</span><span class="sxs-lookup"><span data-stu-id="6543c-287">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="6543c-288">Кроме того, нежелательно предоставлять пользователям класса `Repository` доступ к необработанным строковым данным.</span><span class="sxs-lookup"><span data-stu-id="6543c-288">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="6543c-289">И здесь нам снова помогут атрибуты.</span><span class="sxs-lookup"><span data-stu-id="6543c-289">Attributes can help control that as well.</span></span> <span data-ttu-id="6543c-290">Во-первых, определите свойство `private`, которое будет содержать строковое представление даты и времени в классе `Repository`:</span><span class="sxs-lookup"><span data-stu-id="6543c-290">First, define a `private` property that will hold the string representation of the date time in your `Repository` class:</span></span>

```csharp
[DataMember(Name="pushed_at")]
private string JsonDate { get; set; }
```

<span data-ttu-id="6543c-291">Атрибут `DataMember` сообщает сериализатору, что эти данные нужно обрабатывать, поскольку по умолчанию обрабатываются только открытые члены.</span><span class="sxs-lookup"><span data-stu-id="6543c-291">The `DataMember` attribute informs the serializer that this should be processed, even though it is not a public member.</span></span> <span data-ttu-id="6543c-292">Во-вторых, создайте открытое свойство только для чтения, которое преобразует строку в допустимый объект <xref:System.DateTime> и возвращает этот объект <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="6543c-292">Next, you need to write a public read-only property that converts the string to a valid <xref:System.DateTime> object, and returns that <xref:System.DateTime>:</span></span>

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

<span data-ttu-id="6543c-293">Давайте подробнее рассмотрим представленные выше новые конструкции.</span><span class="sxs-lookup"><span data-stu-id="6543c-293">Let's go over the new constructs above.</span></span> <span data-ttu-id="6543c-294">Атрибут `IgnoreDataMember` сообщает сериализатору, что этот тип не должен использоваться для чтения или записи в любых объектах JSON.</span><span class="sxs-lookup"><span data-stu-id="6543c-294">The `IgnoreDataMember` attribute instructs the serializer that this type should not be read to or written from any JSON object.</span></span> <span data-ttu-id="6543c-295">Это свойство содержит только акцессор `get`.</span><span class="sxs-lookup"><span data-stu-id="6543c-295">This property contains only a `get` accessor.</span></span> <span data-ttu-id="6543c-296">Метод доступа `set` не существует.</span><span class="sxs-lookup"><span data-stu-id="6543c-296">There is no `set` accessor.</span></span> <span data-ttu-id="6543c-297">Именно так в C# определяются свойства *только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="6543c-297">That's how you define a *read-only* property in C#.</span></span> <span data-ttu-id="6543c-298">(Да, вы можете создать в C# даже свойства *только для записи*, но для них трудно найти применение.) Метод <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> анализирует строку и создает объект <xref:System.DateTime>, используя указанный формат даты, а затем включает в `DateTime` дополнительные метаданные, используя объект `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="6543c-298">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="6543c-299">Если операция анализа завершается неудачей, акцессор этого свойства создает исключение.</span><span class="sxs-lookup"><span data-stu-id="6543c-299">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="6543c-300">Чтобы использовать <xref:System.Globalization.CultureInfo.InvariantCulture>, необходимо добавить пространство имен <xref:System.Globalization> в набор инструкций `using` в файле `repo.cs`:</span><span class="sxs-lookup"><span data-stu-id="6543c-300">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` statements in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="6543c-301">Вам осталось только добавить одну инструкцию вывода данных в консоль, и можно будет заново собрать и запустить приложение:</span><span class="sxs-lookup"><span data-stu-id="6543c-301">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="6543c-302">Теперь версия вашего приложения должна совпадать с [полной версией примера](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="6543c-302">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>
 
## <a name="conclusion"></a><span data-ttu-id="6543c-303">Заключение</span><span class="sxs-lookup"><span data-stu-id="6543c-303">Conclusion</span></span>

<span data-ttu-id="6543c-304">В этом руководстве вы увидели, как правильно выполнять веб-запросы, анализировать результаты и отображать полученные в них свойства.</span><span class="sxs-lookup"><span data-stu-id="6543c-304">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="6543c-305">Вы также добавили в свой проект несколько новых пакетов в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="6543c-305">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="6543c-306">Еще вы увидели примеры некоторых функций языка C#, которые поддерживают объектно-ориентированный подход.</span><span class="sxs-lookup"><span data-stu-id="6543c-306">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
