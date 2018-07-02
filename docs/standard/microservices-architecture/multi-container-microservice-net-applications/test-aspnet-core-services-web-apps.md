---
title: Тестирование служб и веб-приложений ASP.NET Core
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Тестирование служб и веб-приложений ASP.NET Core
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 12/11/2017
ms.openlocfilehash: 5e06f582677e61209d0b226fc68bca81dfe593e5
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104404"
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="75d12-103">Тестирование служб и веб-приложений ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="75d12-103">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="75d12-104">Контроллеры — это центральный элемент любой службы ASP.NET Core API или веб-приложения ASP.NET MVC.</span><span class="sxs-lookup"><span data-stu-id="75d12-104">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="75d12-105">Поэтому необходимо убедиться в том, что они работают так, как это требуется вашему приложению.</span><span class="sxs-lookup"><span data-stu-id="75d12-105">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="75d12-106">Это можно сделать с помощью автоматических тестов, которые помогут также обнаружить имеющиеся ошибки до ввода контроллеров в рабочую среду.</span><span class="sxs-lookup"><span data-stu-id="75d12-106">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="75d12-107">Необходимо протестировать работу контроллера при допустимых и недопустимых значениях входных данных, а также проверить реакцию контроллера в сопоставлении с результатами бизнес-операции, которую он выполняет.</span><span class="sxs-lookup"><span data-stu-id="75d12-107">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="75d12-108">Вместе с тем вам необходимо выполнить следующие тесты микрослужб:</span><span class="sxs-lookup"><span data-stu-id="75d12-108">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="75d12-109">Модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="75d12-109">Unit tests.</span></span> <span data-ttu-id="75d12-110">Позволяют проверить правильность работы отдельных компонентов приложения.</span><span class="sxs-lookup"><span data-stu-id="75d12-110">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="75d12-111">С помощью утверждений тестируется API компонента.</span><span class="sxs-lookup"><span data-stu-id="75d12-111">Assertions test the component API.</span></span>

-   <span data-ttu-id="75d12-112">Интеграционные тесты.</span><span class="sxs-lookup"><span data-stu-id="75d12-112">Integration tests.</span></span> <span data-ttu-id="75d12-113">Позволяют проверить правильность взаимодействия компонента с внешними устройствами, например с базами данных.</span><span class="sxs-lookup"><span data-stu-id="75d12-113">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="75d12-114">С помощью утверждений можно тестировать API компонента, пользовательский интерфейс и побочные эффекты от таких операций, как операции ввода-вывода в базах данных, ведение журнала и т. д.</span><span class="sxs-lookup"><span data-stu-id="75d12-114">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="75d12-115">Функциональные тесты для каждой микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="75d12-115">Functional tests for each microservice.</span></span> <span data-ttu-id="75d12-116">Позволяют проверить правильность работы приложения с точки зрения пользователя.</span><span class="sxs-lookup"><span data-stu-id="75d12-116">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="75d12-117">Тесты служб.</span><span class="sxs-lookup"><span data-stu-id="75d12-117">Service tests.</span></span> <span data-ttu-id="75d12-118">Позволяют проверить, были ли протестированы варианты сквозного использования служб, включая одновременное тестирование нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="75d12-118">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="75d12-119">Для такого тестирования необходимо сначала подготовить среду.</span><span class="sxs-lookup"><span data-stu-id="75d12-119">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="75d12-120">В данном случае это означает запуск служб (например, с помощью docker-compose up).</span><span class="sxs-lookup"><span data-stu-id="75d12-120">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="75d12-121">Реализация модульных тестов для веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="75d12-121">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="75d12-122">Модульное тестирование — это тестирование части приложения изолированно от его инфраструктуры и зависимостей.</span><span class="sxs-lookup"><span data-stu-id="75d12-122">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="75d12-123">При модульном тестировании логики контроллера проверяется только содержимое отдельного действия или метода, а работа его зависимостей и самой платформы в целом не проверяется.</span><span class="sxs-lookup"><span data-stu-id="75d12-123">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="75d12-124">Модульные тесты не выявляют проблемы с взаимодействием между компонентами. Для этого предназначены интеграционные тесты.</span><span class="sxs-lookup"><span data-stu-id="75d12-124">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="75d12-125">Выполняя модульное тестирование действий контроллера, следует сосредоточиться только на этих действиях.</span><span class="sxs-lookup"><span data-stu-id="75d12-125">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="75d12-126">В рамках модульного тестирования контроллера не учитываются такие аспекты, как фильтрация, маршрутизация и привязка модели.</span><span class="sxs-lookup"><span data-stu-id="75d12-126">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="75d12-127">Благодаря их узкой направленности модульные тесты, как правило, проще создавать, а выполняются они быстрее.</span><span class="sxs-lookup"><span data-stu-id="75d12-127">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="75d12-128">Правильно составленный набор модульных тестов можно выполнять часто без значительных затрат.</span><span class="sxs-lookup"><span data-stu-id="75d12-128">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="75d12-129">Модульные тесты реализуются на основе платформ тестирования, таких как xUnit.net MSTest, Moq и NUnit.</span><span class="sxs-lookup"><span data-stu-id="75d12-129">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="75d12-130">Для примера приложения eShopOnContainers мы используем XUnit.</span><span class="sxs-lookup"><span data-stu-id="75d12-130">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="75d12-131">При разработке модульного теста для контроллера веб-API можно создать экземпляр класса контроллера непосредственно с помощью ключевого слова new в языке C\#, таким образом, тест будет выполняться с максимально возможной скоростью.</span><span class="sxs-lookup"><span data-stu-id="75d12-131">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="75d12-132">В следующем примере показано, как это можно сделать в случае использования платформы тестирования [XUnit](https://xunit.github.io/).</span><span class="sxs-lookup"><span data-stu-id="75d12-132">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

```csharp
[Fact]
public void Add_new_Order_raises_new_event()
{
    // Arrange
    var street = " FakeStreet ";
    var city = "FakeCity";
    // Other variables omitted for brevity ...
    // Act
    var fakeOrder = new Order(new Address(street, city, state, country, zipcode),
        cardTypeId, cardNumber,
        cardSecurityNumber, cardHolderName,
        cardExpiration);
    // Assert
    Assert.Equal(fakeOrder.DomainEvents.Count, expectedResult);
}
```

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="75d12-133">Реализация интеграционных и функциональных тестов для каждой микрослужбы</span><span class="sxs-lookup"><span data-stu-id="75d12-133">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="75d12-134">Как уже отмечалось, интеграционные и функциональные тесты имеют разное назначение.</span><span class="sxs-lookup"><span data-stu-id="75d12-134">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="75d12-135">Однако способы реализации тех и других при тестировании контроллеров ASP.NET Core похожи. Поэтому в этом разделе мы сосредоточимся на интеграционных тестах.</span><span class="sxs-lookup"><span data-stu-id="75d12-135">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="75d12-136">При интеграционном тестировании проверяется, будут ли компоненты приложения правильно работать после сборки.</span><span class="sxs-lookup"><span data-stu-id="75d12-136">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="75d12-137">Платформа ASP.NET Core поддерживает интеграционное тестирование с использованием платформ модульного тестирования и встроенного веб-сервера тестирования, который может использоваться для обработки запросов без нагрузки на сеть.</span><span class="sxs-lookup"><span data-stu-id="75d12-137">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="75d12-138">В отличие от модульного тестирования, при интеграционном тестировании часто затрагиваются различные аспекты инфраструктуры приложения, например базы данных, файловые системы, сетевые ресурсы, веб-запросы и ответы.</span><span class="sxs-lookup"><span data-stu-id="75d12-138">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="75d12-139">При модульном тестировании используются имитации или макеты объектов вместо реальных объектов.</span><span class="sxs-lookup"><span data-stu-id="75d12-139">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="75d12-140">Интеграционное тестирование предназначено для проверки того, что система работает должным образом с реальными объектами, поэтому при интеграционном тестировании не используются имитации.</span><span class="sxs-lookup"><span data-stu-id="75d12-140">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="75d12-141">В процесс тестирования вовлекается инфраструктура — проверяется, например, выполнение запросов на доступ к базам данных или вызов одной службы другой службой.</span><span class="sxs-lookup"><span data-stu-id="75d12-141">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="75d12-142">Так как при интеграционном тестировании отрабатывается значительно больший, чем при модульном тестировании, объем кода, а также из-за того, что при этом затрагивается инфраструктура элементов, такие тесты обычно выполняются на порядки медленнее, чем модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="75d12-142">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="75d12-143">Поэтому рекомендуется ограничить количество интеграционных тестов.</span><span class="sxs-lookup"><span data-stu-id="75d12-143">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="75d12-144">Платформа ASP.NET Core содержит встроенный веб-сервер тестирования, который можно использовать для обработки HTTP-запросов без нагрузки на сеть. Это позволяет выполнять тесты быстрее, чем при работе с реальными веб-серверами.</span><span class="sxs-lookup"><span data-stu-id="75d12-144">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="75d12-145">Веб-сервер тестирования доступен в компоненте NuGet как Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="75d12-145">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="75d12-146">Его можно добавлять в проекты интеграционного тестирования и использовать для размещения приложений ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="75d12-146">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="75d12-147">Как можно видеть в следующем коде, при создании интеграционных тестов для контроллеров ASP.NET Core создается экземпляр контроллера на сервере тестирования.</span><span class="sxs-lookup"><span data-stu-id="75d12-147">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="75d12-148">Это похоже на HTTP-запрос, но выполняется быстрее.</span><span class="sxs-lookup"><span data-stu-id="75d12-148">This is comparable to an HTTP request, but it runs faster.</span></span>

```csharp
public class PrimeWebDefaultRequestShould
{
    private readonly TestServer _server;
    private readonly HttpClient _client;

    public PrimeWebDefaultRequestShould()
    {
        // Arrange
        _server = new TestServer(new WebHostBuilder()
           .UseStartup<Startup>());
           _client = _server.CreateClient();
    }

    [Fact]
    public async Task ReturnHelloWorld()
    {
        // Act
        var response = await _client.GetAsync("/");
        response.EnsureSuccessStatusCode();
        var responseString = await response.Content.ReadAsStringAsync();
        // Assert
        Assert.Equal("Hello World!", responseString);
    }
}
```

#### <a name="additional-resources"></a><span data-ttu-id="75d12-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="75d12-149">Additional resources</span></span>

-   <span data-ttu-id="75d12-150">**Стив Смит (Steve Smith). Тестирование контроллеров** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="75d12-150">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="75d12-151">**Стив Смит (Steve Smith). Тестирование интеграции** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="75d12-151">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="75d12-152">**Модульное тестирование в .NET Core с помощью команды dotnet test**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span><span class="sxs-lookup"><span data-stu-id="75d12-152">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](../../../core/testing/unit-testing-with-dotnet-test.md)</span></span>

-   <span data-ttu-id="75d12-153">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="75d12-153">**xUnit.net**.</span></span> <span data-ttu-id="75d12-154">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="75d12-154">Official site.</span></span>
    [*https://xunit.github.io/*](https://xunit.github.io/)

-   <span data-ttu-id="75d12-155">**Основные сведения о модульных тестах.**
    [*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="75d12-155">**Unit Test Basics.**
[*https://msdn.microsoft.com/library/hh694602.aspx*](https://msdn.microsoft.com/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="75d12-156">**Moq**.</span><span class="sxs-lookup"><span data-stu-id="75d12-156">**Moq**.</span></span> <span data-ttu-id="75d12-157">Репозиторий GitHub.</span><span class="sxs-lookup"><span data-stu-id="75d12-157">GitHub repo.</span></span>
    [*https://github.com/moq/moq*](https://github.com/moq/moq)

-   <span data-ttu-id="75d12-158">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="75d12-158">**NUnit**.</span></span> <span data-ttu-id="75d12-159">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="75d12-159">Official site.</span></span>
    [*https://www.nunit.org/*](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="75d12-160">Реализация тестов служб в приложении с несколькими контейнерами</span><span class="sxs-lookup"><span data-stu-id="75d12-160">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="75d12-161">Как уже упоминалось, при тестировании приложения с несколькими контейнерами необходимо, чтобы все микрослужбы были запущены на узле Docker или в кластере контейнера.</span><span class="sxs-lookup"><span data-stu-id="75d12-161">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="75d12-162">Для выполнения сквозного тестирования служб, включающего в себя множество операций, затрагивающих несколько микрослужб, требуется развертывание и запуск всего приложения на узле Docker с помощью docker-compose up (или аналогичного механизма, если используется оркестратор).</span><span class="sxs-lookup"><span data-stu-id="75d12-162">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="75d12-163">После запуска приложения и всех его служб вы можете выполнять сквозное интеграционное и функциональное тестирование.</span><span class="sxs-lookup"><span data-stu-id="75d12-163">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="75d12-164">Здесь можно использовать несколько методов.</span><span class="sxs-lookup"><span data-stu-id="75d12-164">There are a few approaches you can use.</span></span> <span data-ttu-id="75d12-165">В файле docker compose.yml, который используется для развертывания приложения (или аналогичном ему, например, docker-compose.ci.build.yml), на уровне решения можно развернуть точку входа, чтобы можно было использовать [тест dotnet](../../../core/tools/dotnet-test.md).</span><span class="sxs-lookup"><span data-stu-id="75d12-165">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](../../../core/tools/dotnet-test.md).</span></span> <span data-ttu-id="75d12-166">Можно также использовать другой файл Compose, который будет запускать ваши тесты в целевом образе.</span><span class="sxs-lookup"><span data-stu-id="75d12-166">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="75d12-167">Используя другой файл Compose для интеграционного тестирования, включающего в себя микрослужбы и базы данных в контейнерах, можно гарантировать, что соответствующие данные будут всегда переведены в исходное состояние перед выполнением тестов.</span><span class="sxs-lookup"><span data-stu-id="75d12-167">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="75d12-168">После того как приложение Compose будет установлено и запущено, вы сможете воспользоваться преимуществами точек останова и исключений, если используется Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="75d12-168">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="75d12-169">Интеграционные тесты можно выполнять автоматически в конвейере CI в Visual Studio Team Services или в любой другой системе CI/CD, которая поддерживает контейнеры Docker.</span><span class="sxs-lookup"><span data-stu-id="75d12-169">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="75d12-170">[Назад](subscribe-events.md)
[Вперед](../microservice-ddd-cqrs-patterns/index.md)</span><span class="sxs-lookup"><span data-stu-id="75d12-170">[Previous](subscribe-events.md)
[Next](../microservice-ddd-cqrs-patterns/index.md)</span></span>
