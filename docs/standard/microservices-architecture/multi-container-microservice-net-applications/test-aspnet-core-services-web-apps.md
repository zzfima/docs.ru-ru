---
title: "Проверка служб ASP.NET Core и веб-приложений"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Проверка служб ASP.NET Core и веб-приложений"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f756a679befee676db2bf6d402fd7e34b1621b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="testing-aspnet-core-services-and-web-apps"></a><span data-ttu-id="e2e2a-104">Проверка служб ASP.NET Core и веб-приложений</span><span class="sxs-lookup"><span data-stu-id="e2e2a-104">Testing ASP.NET Core services and web apps</span></span>

<span data-ttu-id="e2e2a-105">Контроллеры являются центральным элементом любого службы основному API ASP.NET и MVC веб-приложения ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-105">Controllers are a central part of any ASP.NET Core API service and ASP.NET MVC Web application.</span></span> <span data-ttu-id="e2e2a-106">Таким образом должны иметь достоверности они ведут себя так, как для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-106">As such, you should have confidence they behave as intended for your application.</span></span> <span data-ttu-id="e2e2a-107">Автоматические тесты можно получить у этого достоверности и выявить ошибки, прежде чем они достигнут рабочей.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-107">Automated tests can provide you with this confidence and can detect errors before they reach production.</span></span>

<span data-ttu-id="e2e2a-108">Необходимо протестировать поведение контроллера в зависимости от входных данных допустимое или недопустимое и на основе результатов бизнес-операции, выполняемые ею ответы контроллера тестирования.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-108">You need to test how the controller behaves based on valid or invalid inputs, and test controller responses based on the result of the business operation it performs.</span></span> <span data-ttu-id="e2e2a-109">Однако эти типы тестов необходимо иметь вашей микрослужбами:</span><span class="sxs-lookup"><span data-stu-id="e2e2a-109">However, you should have these types of tests your microservices:</span></span>

-   <span data-ttu-id="e2e2a-110">Модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-110">Unit tests.</span></span> <span data-ttu-id="e2e2a-111">Эти убедитесь, что компоненты приложения работают должным образом.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-111">These ensure that individual components of the application work as expected.</span></span> <span data-ttu-id="e2e2a-112">Утверждения проверки компонента API.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-112">Assertions test the component API.</span></span>

-   <span data-ttu-id="e2e2a-113">Интеграционные тесты.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-113">Integration tests.</span></span> <span data-ttu-id="e2e2a-114">Эти убедитесь, что взаимодействие компонентов работать, как ожидалось в отношении внешние устройства, например баз данных.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-114">These ensure that component interactions work as expected against external artifacts like databases.</span></span> <span data-ttu-id="e2e2a-115">Утверждения можно проверить компонент API, пользовательского интерфейса или побочные эффекты действий, таких как базы данных операций ввода-вывода, ведение журнала и т. д.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-115">Assertions can test component API, UI, or the side effects of actions like database I/O, logging, etc.</span></span>

-   <span data-ttu-id="e2e2a-116">Функциональных тестов для каждого микрослужбы.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-116">Functional tests for each microservice.</span></span> <span data-ttu-id="e2e2a-117">Это обеспечивает, что приложение работает с точки зрения пользователя.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-117">These ensure that the application works as expected from the user’s perspective.</span></span>

-   <span data-ttu-id="e2e2a-118">Проверка службы.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-118">Service tests.</span></span> <span data-ttu-id="e2e2a-119">Это обеспечивает, были протестированы вариантов использования службы начала до конца, включая тестирование нескольких служб в то же время.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-119">These ensure that end-to-end service use cases, including testing multiple services at the same time, are tested.</span></span> <span data-ttu-id="e2e2a-120">Этот тип проверки необходимо сначала подготовить среду.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-120">For this type of testing, you need to prepare the environment first.</span></span> <span data-ttu-id="e2e2a-121">В данном случае означает запуск служб (например, с помощью docker составления вверх).</span><span class="sxs-lookup"><span data-stu-id="e2e2a-121">In this case, it means starting the services (for example, by using docker-compose up).</span></span>

### <a name="implementing-unit-tests-for-aspnet-core-web-apis"></a><span data-ttu-id="e2e2a-122">Реализация модульных тестов для веб-API ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e2e2a-122">Implementing unit tests for ASP.NET Core Web APIs</span></span>

<span data-ttu-id="e2e2a-123">Модульное тестирование включает в себя проверку частью приложения отдельно от инфраструктуры и зависимости.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-123">Unit testing involves testing a part of an application in isolation from its infrastructure and dependencies.</span></span> <span data-ttu-id="e2e2a-124">При модульного тестирования логику контроллера, содержимое только одно действие или метод проверяется, не поведение из ее зависимостей или сам платформы.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-124">When you unit test controller logic, only the content of a single action or method is tested, not the behavior of its dependencies or of the framework itself.</span></span> <span data-ttu-id="e2e2a-125">Модульные тесты, не обнаруживают проблемы во взаимодействии между компонентами — то есть назначение интеграционного тестирования.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-125">Unit tests do not detect issues in the interaction between components—that is the purpose of integration testing.</span></span>

<span data-ttu-id="e2e2a-126">Как модульного тестирования ваши действия контроллера, убедитесь, что сосредоточиться только на их работу.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-126">As you unit test your controller actions, make sure you focus only on their behavior.</span></span> <span data-ttu-id="e2e2a-127">Модульный тест контроллер позволяет избежать таких вещей, как фильтры маршрутизации и привязки модели.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-127">A controller unit test avoids things like filters, routing, or model binding.</span></span> <span data-ttu-id="e2e2a-128">Так как они сосредоточиться на тестировании только одно, модульные тесты — обычно просто для записи и быстро выполнять.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-128">Because they focus on testing just one thing, unit tests are generally simple to write and quick to run.</span></span> <span data-ttu-id="e2e2a-129">Грамотно сконструированные набор модульные тесты могут выполняться без большой нагрузки часто.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-129">A well-written set of unit tests can be run frequently without much overhead.</span></span>

<span data-ttu-id="e2e2a-130">Модульные тесты реализуются в зависимости от платформы тестирования как xUnit.net MSTest, заказа и NUnit.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-130">Unit tests are implemented based on test frameworks like xUnit.net, MSTest, Moq, or NUnit.</span></span> <span data-ttu-id="e2e2a-131">Для примера приложения eShopOnContainers мы используем XUnit.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-131">For the eShopOnContainers sample application, we are using XUnit.</span></span>

<span data-ttu-id="e2e2a-132">При создании модульного теста для контроллера веб-API, можно создать экземпляр класса контроллера, непосредственно с помощью ключевого слова new в языке C\#таким образом, тест будет запускаться максимально возможной скоростью.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-132">When you write a unit test for a Web API controller, you instantiate the controller class directly using the new keyword in C\#, so that the test will run as fast as possible.</span></span> <span data-ttu-id="e2e2a-133">Следующий пример показывает, как это сделать при использовании [XUnit](https://xunit.github.io/) как платформы тестирования.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-133">The following example shows how to do this when using [XUnit](https://xunit.github.io/) as the Test framework.</span></span>

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

### <a name="implementing-integration-and-functional-tests-for-each-microservice"></a><span data-ttu-id="e2e2a-134">Реализация интеграции и функциональных тестов для каждого микрослужбу</span><span class="sxs-lookup"><span data-stu-id="e2e2a-134">Implementing integration and functional tests for each microservice</span></span>

<span data-ttu-id="e2e2a-135">Как уже отмечалось, тесты интеграции и функциональных тестов имеют различные предназначения и целей.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-135">As noted, integration tests and functional tests have different purposes and goals.</span></span> <span data-ttu-id="e2e2a-136">Тем не менее можно реализовывать при тестировании контроллеры ASP.NET Core способ аналогичен, в этом разделе мы сосредоточиться на тесты интеграции.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-136">However, the way you implement both when testing ASP.NET Core controllers is similar, so in this section we concentrate on integration tests.</span></span>

<span data-ttu-id="e2e2a-137">Интеграционного тестирования гарантирует, что компоненты приложения работать должным образом, относительно.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-137">Integration testing ensures that an application's components function correctly when assembled.</span></span> <span data-ttu-id="e2e2a-138">ASP.NET Core предоставляет возможности интеграции тестирования с помощью платформы модульного тестирования и встроенных тестов веб-узел, который может использоваться для обработки запросов без нагрузки на сеть.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-138">ASP.NET Core supports integration testing using unit test frameworks and a built-in test web host that can be used to handle requests without network overhead.</span></span>

<span data-ttu-id="e2e2a-139">В отличие от модульного тестирования тесты интеграции часто включают проблемы инфраструктуры приложения, такие как базы данных, файловая система, сетевые ресурсы, или веб-запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-139">Unlike unit testing, integration tests frequently involve application infrastructure concerns, such as a database, file system, network resources, or web requests and responses.</span></span> <span data-ttu-id="e2e2a-140">Модульные тесты использовать fakes или создания объектов вместо этих проблем.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-140">Unit tests use fakes or mock objects in place of these concerns.</span></span> <span data-ttu-id="e2e2a-141">Но интеграционные тесты предназначен для убедитесь, что система работает должным образом с этими системами, поэтому для тестирования интеграции не использовать fakes и создания объектов.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-141">But the purpose of integration tests is to confirm that the system works as expected with these systems, so for integration testing you do not use fakes or mock objects.</span></span> <span data-ttu-id="e2e2a-142">Вместо этого можно включить инфраструктуры, таких как базы данных access или служба вызова от других служб.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-142">Instead, you include the infrastructure, like database access or service invocation from other services.</span></span>

<span data-ttu-id="e2e2a-143">Поскольку тесты интеграции использовать больший сегменты кода, чем модульные тесты и тесты интеграции зависит от инфраструктуры элементов, они обычно бывают порядков медленнее, чем модульные тесты.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-143">Because integration tests exercise larger segments of code than unit tests, and because integration tests rely on infrastructure elements, they tend to be orders of magnitude slower than unit tests.</span></span> <span data-ttu-id="e2e2a-144">Таким образом рекомендуется ограничить количество тестов интеграции написание и запуск.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-144">Thus, it is a good idea to limit how many integration tests you write and run.</span></span>

<span data-ttu-id="e2e2a-145">ASP.NET Core включает встроенных тестов веб-узел, можно использовать для обработки HTTP-запросы без нагрузки на сеть, это означает, что можно запускать эти тесты быстрее при использовании с реальными веб-узла.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-145">ASP.NET Core includes a built-in test web host that can be used to handle HTTP requests without network overhead, meaning that you can run those tests faster when using a real web host.</span></span> <span data-ttu-id="e2e2a-146">Тест веб-узел доступен в компоненте NuGet как Microsoft.AspNetCore.TestHost.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-146">The test web host is available in a NuGet component as Microsoft.AspNetCore.TestHost.</span></span> <span data-ttu-id="e2e2a-147">Его можно добавить к интеграции тестовые проекты и используется для узла ASP.NET Core приложений.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-147">It can be added to integration test projects and used to host ASP.NET Core applications.</span></span>

<span data-ttu-id="e2e2a-148">Как видно в следующем коде при создании интеграционных тестов для ASP.NET Core контроллеров, создайте экземпляр контроллеров путем тестового узла.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-148">As you can see in the following code, when you create integration tests for ASP.NET Core controllers, you instantiate the controllers through the test host.</span></span> <span data-ttu-id="e2e2a-149">Это можно сравнить с HTTP-запроса, но он выполняется быстрее.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-149">This is comparable to an HTTP request, but it runs faster.</span></span>

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

#### <a name="additional-resources"></a><span data-ttu-id="e2e2a-150">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="e2e2a-150">Additional resources</span></span>

-   <span data-ttu-id="e2e2a-151">**Стив Смит. Контроллеры тестирования** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span><span class="sxs-lookup"><span data-stu-id="e2e2a-151">**Steve Smith. Testing controllers** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/mvc/controllers/testing*](https://docs.microsoft.com/aspnet/core/mvc/controllers/testing)</span></span>

-   <span data-ttu-id="e2e2a-152">**Стив Смит. Интеграционного тестирования** (ASP.NET Core) [ *https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span><span class="sxs-lookup"><span data-stu-id="e2e2a-152">**Steve Smith. Integration testing** (ASP.NET Core) [*https://docs.microsoft.com/aspnet/core/testing/integration-testing*](https://docs.microsoft.com/aspnet/core/testing/integration-testing)</span></span>

-   <span data-ttu-id="e2e2a-153">**Модульное тестирование в .NET Core с помощью теста dotnet**
    [*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span><span class="sxs-lookup"><span data-stu-id="e2e2a-153">**Unit testing in .NET Core using dotnet test**
[*https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test*](https://docs.microsoft.com/dotnet/core/testing/unit-testing-with-dotnet-test)</span></span>

-   <span data-ttu-id="e2e2a-154">**xUnit.net**.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-154">**xUnit.net**.</span></span> <span data-ttu-id="e2e2a-155">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="e2e2a-155">Official site.</span></span>
    [<span data-ttu-id="e2e2a-156">*https://xUnit.github.IO/*</span><span class="sxs-lookup"><span data-stu-id="e2e2a-156">*https://xunit.github.io/*</span></span>](https://xunit.github.io/)

-   <span data-ttu-id="e2e2a-157">**О модульных тестах. ** 
     [ *https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span><span class="sxs-lookup"><span data-stu-id="e2e2a-157">**Unit Test Basics.**
[*https://msdn.microsoft.com/en-us/library/hh694602.aspx*](https://msdn.microsoft.com/en-us/library/hh694602.aspx)</span></span>

-   <span data-ttu-id="e2e2a-158">**Заказа**.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-158">**Moq**.</span></span> <span data-ttu-id="e2e2a-159">В репозитории GitHub.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-159">GitHub repo.</span></span>
    [<span data-ttu-id="e2e2a-160">*https://github.com/MOQ/MOQ*</span><span class="sxs-lookup"><span data-stu-id="e2e2a-160">*https://github.com/moq/moq*</span></span>](https://github.com/moq/moq)

-   <span data-ttu-id="e2e2a-161">**NUnit**.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-161">**NUnit**.</span></span> <span data-ttu-id="e2e2a-162">Официальный сайт</span><span class="sxs-lookup"><span data-stu-id="e2e2a-162">Official site.</span></span>
    [<span data-ttu-id="e2e2a-163">*https://www.NUnit.org/*</span><span class="sxs-lookup"><span data-stu-id="e2e2a-163">*https://www.nunit.org/*</span></span>](https://www.nunit.org/)

### <a name="implementing-service-tests-on-a-multi-container-application"></a><span data-ttu-id="e2e2a-164">Реализация службы тесты в приложении несколькими контейнера</span><span class="sxs-lookup"><span data-stu-id="e2e2a-164">Implementing service tests on a multi-container application</span></span> 

<span data-ttu-id="e2e2a-165">Как уже упоминалось, при тестировании приложения несколькими контейнера, микрослужбами нужно запускать в кластере или контейнера Docker.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-165">As noted earlier, when you test multi-container applications, all the microservices need to be running within the Docker host or container cluster.</span></span> <span data-ttu-id="e2e2a-166">Служба конца в конец тесты, включающие несколько операций, включающих несколько микрослужбами требуется развертывание и запуск приложения целиком в узле Docker, выполнив docker-составления вверх (или механизм сопоставимых при использовании orchestrator).</span><span class="sxs-lookup"><span data-stu-id="e2e2a-166">End-to-end service tests that include multiple operations involving several microservices require you to deploy and start the whole application in the Docker host by running docker-compose up (or a comparable mechanism if you are using an orchestrator).</span></span> <span data-ttu-id="e2e2a-167">После запуска всего приложения и все его службы вы можете выполнять интеграцию с начала до конца и функциональных тестов.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-167">Once the whole application and all its services is running, you can execute end-to-end integration and functional tests.</span></span>

<span data-ttu-id="e2e2a-168">Существует несколько подходов, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-168">There are a few approaches you can use.</span></span> <span data-ttu-id="e2e2a-169">В файле docker compose.yml, который используется для развертывания приложения (или аналогичные назначения, такие как docker compose.ci.build.yml), на уровне решения можно развернуть точку входа для использования [dotnet теста](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span><span class="sxs-lookup"><span data-stu-id="e2e2a-169">In the docker-compose.yml file that you use to deploy the application (or similar ones, like docker-compose.ci.build.yml), at the solution level you can expand the entry point to use [dotnet test](https://docs.microsoft.com/dotnet/core/tools/dotnet-test).</span></span> <span data-ttu-id="e2e2a-170">Можно также использовать другой создать файл, который будет выполнять тесты в образ, который вы используете.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-170">You can also use another compose file that would run your tests in the image you are targeting.</span></span> <span data-ttu-id="e2e2a-171">С помощью другого файла создания сообщения для интеграции тестов, которые включают микрослужбами и баз данных на контейнеры, можно убедитесь, что связанные данные всегда сбросить в исходное состояние перед выполнением тестов.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-171">By using another compose file for integration tests that includes your microservices and databases on containers, you can make sure that the related data is always reset to its original state before running the tests.</span></span>

<span data-ttu-id="e2e2a-172">После создания сообщения приложение не работает, можно воспользоваться преимуществами точки останова и исключения, если вы используете Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-172">Once the compose application is up and running, you can take advantage of breakpoints and exceptions if you are running Visual Studio.</span></span> <span data-ttu-id="e2e2a-173">Или можно выполнить тесты интеграции автоматически в конвейер элемента конфигурации в Visual Studio Team Services или любую другую систему CI или компакт-диска, который поддерживает контейнеры Docker.</span><span class="sxs-lookup"><span data-stu-id="e2e2a-173">Or you can run the integration tests automatically in your CI pipeline in Visual Studio Team Services or any other CI/CD system that supports Docker containers.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="e2e2a-174">[Предыдущие] (подписаться events.md) [Далее] (.. /microservice-ddd-CQRS-Patterns/index.MD)</span><span class="sxs-lookup"><span data-stu-id="e2e2a-174">[Previous] (subscribe-events.md) [Next] (../microservice-ddd-cqrs-patterns/index.md)</span></span>
