---
title: Создание клиента REST с использованием .NET Core
description: Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: 09eda08f82490070c66d0b290359872c1043b0c2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737574"
---
# <a name="rest-client"></a><span data-ttu-id="bbf16-103">Клиент REST</span><span class="sxs-lookup"><span data-stu-id="bbf16-103">REST client</span></span>

## <a name="introduction"></a><span data-ttu-id="bbf16-104">Вступление</span><span class="sxs-lookup"><span data-stu-id="bbf16-104">Introduction</span></span>

<span data-ttu-id="bbf16-105">Это руководство раскроет для вас некоторые возможности .NET Core и языка C#.</span><span class="sxs-lookup"><span data-stu-id="bbf16-105">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="bbf16-106">Вы узнаете:</span><span class="sxs-lookup"><span data-stu-id="bbf16-106">You’ll learn:</span></span>

* <span data-ttu-id="bbf16-107">работа с интерфейсом командной строки (CLI) в .NET Core;</span><span class="sxs-lookup"><span data-stu-id="bbf16-107">The basics of the .NET Core Command Line Interface (CLI).</span></span>
* <span data-ttu-id="bbf16-108">обзор возможностей языка C#;</span><span class="sxs-lookup"><span data-stu-id="bbf16-108">An overview of C# Language features.</span></span>
* <span data-ttu-id="bbf16-109">управление зависимостями с помощью NuGet;</span><span class="sxs-lookup"><span data-stu-id="bbf16-109">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="bbf16-110">взаимодействие по протоколу HTTP;</span><span class="sxs-lookup"><span data-stu-id="bbf16-110">HTTP Communications</span></span>
* <span data-ttu-id="bbf16-111">обработка информации в формате JSON;</span><span class="sxs-lookup"><span data-stu-id="bbf16-111">Processing JSON information</span></span>
* <span data-ttu-id="bbf16-112">управление конфигурацией с помощью атрибутов.</span><span class="sxs-lookup"><span data-stu-id="bbf16-112">Managing configuration with Attributes.</span></span>

<span data-ttu-id="bbf16-113">Вам предстоит создать приложение, которое отправляет запросы HTTP к службе REST на GitHub.</span><span class="sxs-lookup"><span data-stu-id="bbf16-113">You’ll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="bbf16-114">Вы будете считывать данные в формате JSON и преобразовывать полученный пакет JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="bbf16-114">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="bbf16-115">И наконец, вы увидите примеры работы с объектами C#.</span><span class="sxs-lookup"><span data-stu-id="bbf16-115">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="bbf16-116">В этом руководстве описано множество функций.</span><span class="sxs-lookup"><span data-stu-id="bbf16-116">There are many features in this tutorial.</span></span> <span data-ttu-id="bbf16-117">Давайте начнем поочередно разбирать их.</span><span class="sxs-lookup"><span data-stu-id="bbf16-117">Let’s build them one by one.</span></span>

<span data-ttu-id="bbf16-118">Если вы хотите поработать с [примером окончательного кода](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) в этом разделе, вы можете его загрузить.</span><span class="sxs-lookup"><span data-stu-id="bbf16-118">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this topic, you can download it.</span></span> <span data-ttu-id="bbf16-119">Инструкции по загрузке см. в разделе [Просмотр и скачивание примеров](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="bbf16-119">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bbf16-120">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="bbf16-120">Prerequisites</span></span>

<span data-ttu-id="bbf16-121">Компьютер должен быть настроен для выполнения .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bbf16-121">You’ll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="bbf16-122">Инструкции по установке см. на странице [скачиваемых файлов .NET Core](https://dotnet.microsoft.com/download).</span><span class="sxs-lookup"><span data-stu-id="bbf16-122">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="bbf16-123">Это приложение можно запустить в ОС Windows, Linux, macOS или в контейнере Docker.</span><span class="sxs-lookup"><span data-stu-id="bbf16-123">You can run this application on Windows, Linux, macOS or in a Docker container.</span></span>
<span data-ttu-id="bbf16-124">Вам потребуется редактор кода, но вы можете выбрать любой привычный для вас.</span><span class="sxs-lookup"><span data-stu-id="bbf16-124">You’ll need to install your favorite code editor.</span></span> <span data-ttu-id="bbf16-125">В примерах ниже используется кроссплатформенный редактор [Visual Studio Code](https://code.visualstudio.com/) с открытым исходным кодом.</span><span class="sxs-lookup"><span data-stu-id="bbf16-125">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="bbf16-126">Вы можете заменить его на любое другое средство, с которым вам удобно работать.</span><span class="sxs-lookup"><span data-stu-id="bbf16-126">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="bbf16-127">Создание приложения</span><span class="sxs-lookup"><span data-stu-id="bbf16-127">Create the Application</span></span>

<span data-ttu-id="bbf16-128">Первым шагом является создание нового приложения.</span><span class="sxs-lookup"><span data-stu-id="bbf16-128">The first step is to create a new application.</span></span> <span data-ttu-id="bbf16-129">Откройте командную строку и создайте новый каталог для приложения.</span><span class="sxs-lookup"><span data-stu-id="bbf16-129">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="bbf16-130">Перейдите в этот каталог.</span><span class="sxs-lookup"><span data-stu-id="bbf16-130">Make that the current directory.</span></span> <span data-ttu-id="bbf16-131">Введите следующую команду в окне консоли:</span><span class="sxs-lookup"><span data-stu-id="bbf16-131">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebApiClient
```

<span data-ttu-id="bbf16-132">Эта команда создает начальный набор файлов для базового приложения Hello World.</span><span class="sxs-lookup"><span data-stu-id="bbf16-132">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="bbf16-133">Имя проекта — "WebApiClient".</span><span class="sxs-lookup"><span data-stu-id="bbf16-133">The project name is "WebApiClient".</span></span> <span data-ttu-id="bbf16-134">Так как это новый проект, зависимостей нет на месте.</span><span class="sxs-lookup"><span data-stu-id="bbf16-134">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="bbf16-135">При первом запуске будет скачана платформа .NET Core, установлен сертификат разработки и запущен диспетчер пакетов NuGet для восстановления отсутствующих зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bbf16-135">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="bbf16-136">Прежде чем вносить изменения, введите `dotnet run` ([см. примечание](#dotnet-restore-note)) в командной строке, чтобы запустить приложение.</span><span class="sxs-lookup"><span data-stu-id="bbf16-136">Before you start making modifications, type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="bbf16-137">`dotnet run` автоматически выполняет `dotnet restore` при отсутствии зависимостей в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="bbf16-137">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="bbf16-138">Он также выполнит `dotnet build`, если приложение необходимо пересобрать.</span><span class="sxs-lookup"><span data-stu-id="bbf16-138">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="bbf16-139">После первоначальной настройки будет достаточно запуска `dotnet restore` или `dotnet build`, когда это имеет смысл для вашего проекта.</span><span class="sxs-lookup"><span data-stu-id="bbf16-139">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="bbf16-140">Добавление новых зависимостей</span><span class="sxs-lookup"><span data-stu-id="bbf16-140">Adding New Dependencies</span></span>

<span data-ttu-id="bbf16-141">Одна из важнейших миссий .NET Core — снизить размер установки .NET.</span><span class="sxs-lookup"><span data-stu-id="bbf16-141">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="bbf16-142">Если для каких-то задач приложению нужны дополнительные библиотеки, добавляйте их в качестве зависимостей в файл проекта C# (\*.csproj).</span><span class="sxs-lookup"><span data-stu-id="bbf16-142">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="bbf16-143">В нашем примере нужно добавить пакет `System.Runtime.Serialization.Json`, чтобы приложение могло обрабатывать ответы JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-143">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="bbf16-144">Для этого приложения понадобится пакет `System.Runtime.Serialization.Json`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-144">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="bbf16-145">Добавьте его в свой проект, запустив следующую команду [.NET CLI](../../core/tools/dotnet-add-package.md):</span><span class="sxs-lookup"><span data-stu-id="bbf16-145">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```console
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="bbf16-146">Выполнение веб-запросов</span><span class="sxs-lookup"><span data-stu-id="bbf16-146">Making Web Requests</span></span>

<span data-ttu-id="bbf16-147">Теперь вы готовы получать данные из Интернета.</span><span class="sxs-lookup"><span data-stu-id="bbf16-147">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="bbf16-148">В этом приложении вы будете считывать информацию из [API GitHub](https://developer.github.com/v3/).</span><span class="sxs-lookup"><span data-stu-id="bbf16-148">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="bbf16-149">Давайте, например, получим информацию о проектах под зонтичным брендом [.NET Foundation](https://www.dotnetfoundation.org/).</span><span class="sxs-lookup"><span data-stu-id="bbf16-149">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="bbf16-150">Для начала вам нужно составить запрос к API GitHub для получения информации о проектах.</span><span class="sxs-lookup"><span data-stu-id="bbf16-150">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="bbf16-151">Используемая конечная точка: <https://api.github.com/orgs/dotnet/repos>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-151">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="bbf16-152">Вы будете получать все данные об этих проектах, поэтому используйте запрос HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="bbf16-152">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="bbf16-153">Браузер также использует запросы HTTP GET, поэтому вы можете указать этот URL-адрес в адресной строке браузера и увидеть, какие сведения вы будете получать и обрабатывать.</span><span class="sxs-lookup"><span data-stu-id="bbf16-153">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="bbf16-154">Для выполнения веб-запросов используется класс <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-154">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="bbf16-155">Как и все современные API-интерфейсы .NET, <xref:System.Net.Http.HttpClient> поддерживает для API-интерфейсов длительного выполнения только асинхронные методы.</span><span class="sxs-lookup"><span data-stu-id="bbf16-155">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="bbf16-156">Поэтому вам нужно создать асинхронный метод.</span><span class="sxs-lookup"><span data-stu-id="bbf16-156">Start by making an async method.</span></span> <span data-ttu-id="bbf16-157">Реализацию вы будете добавлять постепенно, по мере создания функций приложения.</span><span class="sxs-lookup"><span data-stu-id="bbf16-157">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="bbf16-158">Сначала откройте файл `program.cs`, расположенный в каталоге проекта, и добавьте в класс `Program` следующий метод:</span><span class="sxs-lookup"><span data-stu-id="bbf16-158">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="bbf16-159">В верхней части метода `Main` нужно добавить директиву `using`, чтобы компилятор C# распознал тип <xref:System.Threading.Tasks.Task>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-159">You'll need to add a `using` directive at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="bbf16-160">Если сейчас вы выполните сборку проекта, то получите предупреждение для этого метода, поскольку он не содержит ни одного оператора `await`, и поэтому будет выполняться синхронно.</span><span class="sxs-lookup"><span data-stu-id="bbf16-160">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="bbf16-161">Пока это предупреждение можно игнорировать. Операторы `await` здесь появятся по мере заполнения метода.</span><span class="sxs-lookup"><span data-stu-id="bbf16-161">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="bbf16-162">А пока переименуйте пространство имен, определенное в инструкции `namespace`, указав имя `WebAPIClient` вместо имени по умолчанию `ConsoleApp`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-162">Next, rename the namespace defined in the `namespace` statement from its default of `ConsoleApp` to `WebAPIClient`.</span></span> <span data-ttu-id="bbf16-163">Позднее в этом пространстве имен мы определим класс `repo`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-163">We'll later define a `repo` class in this namespace.</span></span>

<span data-ttu-id="bbf16-164">Теперь измените метод `Main`, добавив вызов этого метода.</span><span class="sxs-lookup"><span data-stu-id="bbf16-164">Next, update the `Main` method to call this method.</span></span> <span data-ttu-id="bbf16-165">Метод `ProcessRepositories` возвращает задачу, до завершения которой выполнение программы не должно прекращаться.</span><span class="sxs-lookup"><span data-stu-id="bbf16-165">The `ProcessRepositories` method returns a task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="bbf16-166">Поэтому следует изменить сигнатуру `Main`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-166">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="bbf16-167">Добавьте модификатор `async` и измените тип возвращаемого значения на `Task`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-167">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="bbf16-168">Затем в теле метода добавьте вызов к `ProcessRepositories`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-168">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="bbf16-169">Добавьте ключевое слово `await` в этот вызов метода.</span><span class="sxs-lookup"><span data-stu-id="bbf16-169">Add the `await` keyword to that method call:</span></span>

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="bbf16-170">Теперь у вас есть программа, которая работает в асинхронном режиме, но не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="bbf16-170">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="bbf16-171">Давайте улучшим ее.</span><span class="sxs-lookup"><span data-stu-id="bbf16-171">Let's improve it.</span></span>

<span data-ttu-id="bbf16-172">Для начала нужен объект, который может извлечь данные из Интернета. Для этого подойдет <xref:System.Net.Http.HttpClient>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-172">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="bbf16-173">Он будет обрабатывать запрос и ответы на него.</span><span class="sxs-lookup"><span data-stu-id="bbf16-173">This object handles the request and the responses.</span></span> <span data-ttu-id="bbf16-174">Создайте один экземпляр этого типа в классе `Program` из файла *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="bbf16-174">Instantiate a single instance of that type in the `Program` class inside the *Program.cs* file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="bbf16-175">Давайте вернемся к методу `ProcessRepositories` и создадим его первую версию.</span><span class="sxs-lookup"><span data-stu-id="bbf16-175">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

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

<span data-ttu-id="bbf16-176">Чтобы эта версия успешно компилировалась, нужно добавить две новые директивы `using` в верхней части файла.</span><span class="sxs-lookup"><span data-stu-id="bbf16-176">You'll need to also add two new `using` directives at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="bbf16-177">Эта первая версия метода выполняет веб-запрос для чтения списка всех репозиториев в организации dotnet foundation.</span><span class="sxs-lookup"><span data-stu-id="bbf16-177">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="bbf16-178">(На сайте gitHub организация .NET Foundation имеет идентификатор dotnet.)</span><span class="sxs-lookup"><span data-stu-id="bbf16-178">(The gitHub ID for the .NET Foundation is 'dotnet').</span></span> <span data-ttu-id="bbf16-179">Первые несколько строк настраивают <xref:System.Net.Http.HttpClient> для этого запроса.</span><span class="sxs-lookup"><span data-stu-id="bbf16-179">The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="bbf16-180">Сначала мы указываем, что он будет принимать ответы GitHub JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-180">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="bbf16-181">Они возвращаются в простом формате JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-181">This format is simply JSON.</span></span> <span data-ttu-id="bbf16-182">Следующая строка добавляет заголовок User Agent ко всем запросам от этого объекта.</span><span class="sxs-lookup"><span data-stu-id="bbf16-182">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="bbf16-183">Кодом сервера GitHub проверяет эти два заголовка, и их наличие необходимо для извлечения сведений из GitHub.</span><span class="sxs-lookup"><span data-stu-id="bbf16-183">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="bbf16-184">Когда вы настроите объект <xref:System.Net.Http.HttpClient>, можно выполнить веб-запрос и получить ответ.</span><span class="sxs-lookup"><span data-stu-id="bbf16-184">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="bbf16-185">В первой версии используйте удобный метод <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-185">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="bbf16-186">Этот метод запускает задачу для выполнения веб-запроса, а при получении результатов запроса он считывает поток ответа и извлекает из него содержимое.</span><span class="sxs-lookup"><span data-stu-id="bbf16-186">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="bbf16-187">Текст ответа возвращается в формате <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-187">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="bbf16-188">Эта строка становится доступна после завершения задачи.</span><span class="sxs-lookup"><span data-stu-id="bbf16-188">The string is available when the task completes.</span></span>

<span data-ttu-id="bbf16-189">Последние две строки этого метода ожидают выполнения созданной задачи, а затем выводят ответ в консоль.</span><span class="sxs-lookup"><span data-stu-id="bbf16-189">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="bbf16-190">Выполните сборку приложения и запустите его.</span><span class="sxs-lookup"><span data-stu-id="bbf16-190">Build the app, and run it.</span></span> <span data-ttu-id="bbf16-191">Предупреждение при сборке теперь не отображается, поскольку в методе `ProcessRepositories` есть оператор `await`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-191">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="bbf16-192">В ответ вы получите длинный текст в формате JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-192">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="bbf16-193">Обработка результатов JSON</span><span class="sxs-lookup"><span data-stu-id="bbf16-193">Processing the JSON Result</span></span>

<span data-ttu-id="bbf16-194">Сейчас у вас уже есть код, который получает от веб-сервера ответ и отображает текст из этого ответа.</span><span class="sxs-lookup"><span data-stu-id="bbf16-194">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="bbf16-195">Теперь давайте преобразуем этот ответ JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="bbf16-195">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="bbf16-196">Класс <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> сериализирует объекты в JSON и десериализирует JSON на объекты.</span><span class="sxs-lookup"><span data-stu-id="bbf16-196">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="bbf16-197">Начните с определения класса, представляющего объект JSON `repo`, возвращенный из API GitHub:</span><span class="sxs-lookup"><span data-stu-id="bbf16-197">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; };
    }
}
```

<span data-ttu-id="bbf16-198">Поместите приведенный выше код в новый файл с именем repo.cs.</span><span class="sxs-lookup"><span data-stu-id="bbf16-198">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="bbf16-199">Эта версия класса реализует простейший способ обработки данных JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-199">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="bbf16-200">Имя класса и имя элемента совпадают с именами, используемыми в пакете JSON, и не соответствуют соглашениям C# об именовании.</span><span class="sxs-lookup"><span data-stu-id="bbf16-200">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="bbf16-201">Чтобы исправить это, мы позже добавим некоторые атрибуты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bbf16-201">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="bbf16-202">Этот класс демонстрирует еще одну важную возможность сериализации и десериализации JSON — не все поля в пакете JSON входят в этот класс.</span><span class="sxs-lookup"><span data-stu-id="bbf16-202">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="bbf16-203">Сериализатор JSON просто игнорирует информацию, которая не входит в используемый тип класса.</span><span class="sxs-lookup"><span data-stu-id="bbf16-203">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="bbf16-204">Такое поведение позволяет легко создавать типы, работающие с любым подмножеством полей из пакета JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-204">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="bbf16-205">Теперь давайте выполним десериализацию созданного типа.</span><span class="sxs-lookup"><span data-stu-id="bbf16-205">Now that you've created the type, let's deserialize it.</span></span> 

<span data-ttu-id="bbf16-206">Теперь вызовите сериализатор для преобразования пакета JSON в объекты C#.</span><span class="sxs-lookup"><span data-stu-id="bbf16-206">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="bbf16-207">В методе `ProcessRepositories` замените вызов <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> следующими тремя строками:</span><span class="sxs-lookup"><span data-stu-id="bbf16-207">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following three lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="bbf16-208">Вы используете новое пространство имён, поэтому его нужно добавить в верхней части файла:</span><span class="sxs-lookup"><span data-stu-id="bbf16-208">You're using a new namespace, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Text.Json;
```

<span data-ttu-id="bbf16-209">Обратите внимание, что теперь вы используете <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> вместо <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-209">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="bbf16-210">Сериализатор использует в качестве источника поток, а не строку.</span><span class="sxs-lookup"><span data-stu-id="bbf16-210">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="bbf16-211">Рассмотрим несколько функций языка C#, которые используются во второй строке предыдущего фрагмента кода.</span><span class="sxs-lookup"><span data-stu-id="bbf16-211">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="bbf16-212">Первый аргумент <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> является выражением `await`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-212">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="bbf16-213">(Два других параметра являются необязательными и не включены в фрагмент кода.) Выражения await могут использоваться почти в любом месте кода, хотя пока мы их применяли только в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="bbf16-213">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="bbf16-214">Метод `Deserialize` является *общим*, что означает, что необходимо предоставить аргументы типа того, какие объекты следует создать из текста JSON.</span><span class="sxs-lookup"><span data-stu-id="bbf16-214">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="bbf16-215">В этом примере выполняется десериализация в `List<Repository>`, который является еще одним общим объектом <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-215">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="bbf16-216">Класс `List<>` хранит коллекцию объектов.</span><span class="sxs-lookup"><span data-stu-id="bbf16-216">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="bbf16-217">Аргумент типа определяет тип объектов, хранящихся в `List<>`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-217">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="bbf16-218">Текст JSON представляет набор объектов репозитория, поэтому аргументом типа является `Repository`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-218">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="bbf16-219">В этом разделе все почти готово.</span><span class="sxs-lookup"><span data-stu-id="bbf16-219">You're almost done with this section.</span></span> <span data-ttu-id="bbf16-220">Вы уже преобразовали JSON в объекты C#, и теперь можете отобразить имена всех репозиториев.</span><span class="sxs-lookup"><span data-stu-id="bbf16-220">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="bbf16-221">Удалите вот эти строки кода:</span><span class="sxs-lookup"><span data-stu-id="bbf16-221">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="bbf16-222">и замените их следующим фрагментом:</span><span class="sxs-lookup"><span data-stu-id="bbf16-222">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="bbf16-223">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="bbf16-223">Compile and run the application.</span></span> <span data-ttu-id="bbf16-224">Вы получите имена всех репозиториев, которые являются частью .NET Foundation.</span><span class="sxs-lookup"><span data-stu-id="bbf16-224">It will print out the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="bbf16-225">Управление сериализацией</span><span class="sxs-lookup"><span data-stu-id="bbf16-225">Controlling Serialization</span></span>

<span data-ttu-id="bbf16-226">Прежде чем добавлять дополнительные функции, давайте обратимся к свойству `name` с помощью атрибута `[JsonPropertyName]`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-226">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="bbf16-227">В файле repo.cs внесите следующие изменения в объявление `name`:</span><span class="sxs-lookup"><span data-stu-id="bbf16-227">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="bbf16-228">Чтобы использовать атрибут `[JsonPropertyName]`, нужно добавить пространство имен <xref:System.Text.Json.Serialization> в директивы `using`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-228">To use `[JsonPropertyName]` attribute, you will need to add the <xref:System.Text.Json.Serialization> namespace to the `using` directives:</span></span>

```csharp
using System.Text.Json.Serialization;
```

<span data-ttu-id="bbf16-229">Это изменение требует также изменить код в файле program.cs, который записывает имя каждого хранилища:</span><span class="sxs-lookup"><span data-stu-id="bbf16-229">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="bbf16-230">Выполните `dotnet run`, чтобы проверить правильность сопоставления.</span><span class="sxs-lookup"><span data-stu-id="bbf16-230">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="bbf16-231">Результат выполнения должен быть такой же, как прежде.</span><span class="sxs-lookup"><span data-stu-id="bbf16-231">You should see the same output as before.</span></span>

<span data-ttu-id="bbf16-232">И еще одно изменение, прежде чем мы начнем добавлять новые функции.</span><span class="sxs-lookup"><span data-stu-id="bbf16-232">Let's make one more change before adding new features.</span></span> <span data-ttu-id="bbf16-233">Метод `ProcessRepositories` может выполнять работу в асинхронном режиме и возвращает коллекцию репозиториев.</span><span class="sxs-lookup"><span data-stu-id="bbf16-233">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="bbf16-234">Давайте сделаем так, чтобы этот метод возвращал `List<Repository>`, а сегмент кода, который записывает информацию, переместим в метод `Main`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-234">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="bbf16-235">Измените сигнатуру `ProcessRepositories`, чтобы этот метод возвращал задачу, результатом которой является список объектов `Repository`:</span><span class="sxs-lookup"><span data-stu-id="bbf16-235">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="bbf16-236">Теперь мы можем просто возвращать репозитории после обработки ответа JSON:</span><span class="sxs-lookup"><span data-stu-id="bbf16-236">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var repositories = serializer.ReadObject(await streamTask) as List<Repository>;
return repositories;
```

<span data-ttu-id="bbf16-237">Компилятор создает в качестве выходных данных объект `Task<T>`, поскольку этот метод обозначен ключевым словом `async`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-237">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="bbf16-238">Теперь мы изменим метод `Main` так, чтобы он записывает эти результаты и выводил в консоль имя каждого репозитория.</span><span class="sxs-lookup"><span data-stu-id="bbf16-238">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="bbf16-239">Метод `Main` теперь выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bbf16-239">Your `Main` method now looks like this:</span></span>

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="bbf16-240">Получение дополнительных сведений</span><span class="sxs-lookup"><span data-stu-id="bbf16-240">Reading More Information</span></span>

<span data-ttu-id="bbf16-241">И в завершении нашего руководства мы обработаем еще несколько свойств, содержащихся в пакете JSON, который отправляется из API GitHub.</span><span class="sxs-lookup"><span data-stu-id="bbf16-241">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="bbf16-242">Нет смысла обрабатывать всю информацию, но добавление нескольких свойств поможет продемонстрировать еще несколько возможностей языка C#.</span><span class="sxs-lookup"><span data-stu-id="bbf16-242">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="bbf16-243">Сначала добавьте еще несколько простых типов в определение класса `Repository`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-243">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="bbf16-244">Добавьте в этот класс следующие свойства:</span><span class="sxs-lookup"><span data-stu-id="bbf16-244">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName(Name="description")]
public string Description { get; set; }

[JsonPropertyName(Name="html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName(Name="homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName(Name="watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="bbf16-245">Для этих свойств применяются встроенные преобразования из строкового типа (который используется в пакетах JSON) в целевой тип.</span><span class="sxs-lookup"><span data-stu-id="bbf16-245">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="bbf16-246">Возможно, с типом <xref:System.Uri> вы пока не знакомы.</span><span class="sxs-lookup"><span data-stu-id="bbf16-246">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="bbf16-247">Он представляет универсальный код ресурса, например URL-адрес, как в нашем примере.</span><span class="sxs-lookup"><span data-stu-id="bbf16-247">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="bbf16-248">Если вы используете типы `Uri` и `int`, а пакет JSON содержит данные, для которых невозможно выполнить преобразование в целевой тип, действие сериализации создает исключение.</span><span class="sxs-lookup"><span data-stu-id="bbf16-248">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="bbf16-249">Добавив новые типы, включите их в метод `Main`:</span><span class="sxs-lookup"><span data-stu-id="bbf16-249">Once you've added these, update the `Main` method to display those elements:</span></span>

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

<span data-ttu-id="bbf16-250">На последнем этапе мы добавим сведения о последней операции принудительной отправки.</span><span class="sxs-lookup"><span data-stu-id="bbf16-250">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="bbf16-251">Эта информация представлена в ответе JSON в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="bbf16-251">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="bbf16-252">Он не соответствует ни одному из стандартных форматов .NET для типа <xref:System.DateTime>.</span><span class="sxs-lookup"><span data-stu-id="bbf16-252">That format does not follow any of the standard .NET <xref:System.DateTime> formats.</span></span> <span data-ttu-id="bbf16-253">Поэтому нам нужен специализированный метод для преобразования.</span><span class="sxs-lookup"><span data-stu-id="bbf16-253">Because of that, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="bbf16-254">Кроме того, нежелательно предоставлять пользователям класса `Repository` доступ к необработанным строковым данным.</span><span class="sxs-lookup"><span data-stu-id="bbf16-254">You also probably don't want the raw string exposed to users of the `Repository` class.</span></span> <span data-ttu-id="bbf16-255">И здесь нам снова помогут атрибуты.</span><span class="sxs-lookup"><span data-stu-id="bbf16-255">Attributes can help control that as well.</span></span> <span data-ttu-id="bbf16-256">Сначала определите свойство `public`, которое будет содержать строковое представление даты и времени в вашем классе `Repository`, а также свойство `LastPush` `readonly`, которое возвращает отформатированную строку, которая представляет возвращенную дату:</span><span class="sxs-lookup"><span data-stu-id="bbf16-256">First, define a `public` property that will hold the string representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns a formatted string that represents the returned date:</span></span>

```csharp
[JsonPropertyName(Name="pushed_at")]
public string JsonDate { get; set; }

public DateTime LastPush =>
    DateTime.ParseExact(JsonDate, "yyyy-MM-ddTHH:mm:ssZ", CultureInfo.InvariantCulture);
```

<span data-ttu-id="bbf16-257">Давайте подробнее рассмотрим новые конструкции, которые мы только что определили.</span><span class="sxs-lookup"><span data-stu-id="bbf16-257">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="bbf16-258">Свойство `LastPush` определяется с помощью *члена, заданного выражением* для метода доступа `get`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-258">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="bbf16-259">Метод доступа `set` не существует.</span><span class="sxs-lookup"><span data-stu-id="bbf16-259">There is no `set` accessor.</span></span> <span data-ttu-id="bbf16-260">Именно так в C#, пропуская метод доступа `set`, определяется свойство*только для чтения*.</span><span class="sxs-lookup"><span data-stu-id="bbf16-260">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="bbf16-261">(Да, вы можете создать в C# даже свойства *только для записи*, но для них трудно найти применение.) Метод <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> анализирует строку и создает объект <xref:System.DateTime>, используя указанный формат даты, а затем включает в `DateTime` дополнительные метаданные, используя объект `CultureInfo`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-261">(Yes, you can create *write-only* properties in C#, but their value is limited.) The <xref:System.DateTime.ParseExact(System.String,System.String,System.IFormatProvider)> method parses a string and creates a <xref:System.DateTime> object using a provided date format, and adds additional metadata to the `DateTime` using a `CultureInfo` object.</span></span> <span data-ttu-id="bbf16-262">Если операция анализа завершается неудачей, акцессор этого свойства создает исключение.</span><span class="sxs-lookup"><span data-stu-id="bbf16-262">If the parse operation fails, the property accessor throws an exception.</span></span>

<span data-ttu-id="bbf16-263">Чтобы использовать <xref:System.Globalization.CultureInfo.InvariantCulture>, нужно добавить пространство имен <xref:System.Globalization> в директивы `using` в файле `repo.cs`.</span><span class="sxs-lookup"><span data-stu-id="bbf16-263">To use <xref:System.Globalization.CultureInfo.InvariantCulture>, you will need to add the <xref:System.Globalization> namespace to the `using` directives in `repo.cs`:</span></span>

```csharp
using System.Globalization;
```

<span data-ttu-id="bbf16-264">Вам осталось только добавить одну инструкцию вывода данных в консоль, и можно будет заново собрать и запустить приложение:</span><span class="sxs-lookup"><span data-stu-id="bbf16-264">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="bbf16-265">Теперь версия вашего приложения должна совпадать с [полной версией примера](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span><span class="sxs-lookup"><span data-stu-id="bbf16-265">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="bbf16-266">Заключение</span><span class="sxs-lookup"><span data-stu-id="bbf16-266">Conclusion</span></span>

<span data-ttu-id="bbf16-267">В этом руководстве вы увидели, как правильно выполнять веб-запросы, анализировать результаты и отображать полученные в них свойства.</span><span class="sxs-lookup"><span data-stu-id="bbf16-267">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="bbf16-268">Вы также добавили в свой проект несколько новых пакетов в качестве зависимостей.</span><span class="sxs-lookup"><span data-stu-id="bbf16-268">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="bbf16-269">Еще вы увидели примеры некоторых функций языка C#, которые поддерживают объектно-ориентированный подход.</span><span class="sxs-lookup"><span data-stu-id="bbf16-269">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
