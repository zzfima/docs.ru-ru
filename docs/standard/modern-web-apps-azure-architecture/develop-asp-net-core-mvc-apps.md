---
title: "Разработка приложений MVC ASP.NET Core"
description: "Архитектора современных веб-приложений с помощью ASP.NET Core и Azure | Разработка приложений MVC ASP.NET Core"
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c10bf66dd37f0d99c038db7f95999d84986152fa
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="develop-aspnet-core-mvc-apps"></a><span data-ttu-id="44232-103">Разработка приложений MVC ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="44232-103">Develop ASP.NET Core MVC Apps</span></span>

> <span data-ttu-id="44232-104">«Важно не получается в первый раз.</span><span class="sxs-lookup"><span data-stu-id="44232-104">"It's not important to get it right the first time.</span></span> <span data-ttu-id="44232-105">Важно жизненно получается в последний раз.»</span><span class="sxs-lookup"><span data-stu-id="44232-105">It's vitally important to get it right the last time."</span></span>  
> <span data-ttu-id="44232-106">_-Эндрю слежения и Дэвид Thomas_</span><span class="sxs-lookup"><span data-stu-id="44232-106">_- Andrew Hunt and David Thomas_</span></span>

## <a name="summary"></a><span data-ttu-id="44232-107">Сводка</span><span class="sxs-lookup"><span data-stu-id="44232-107">Summary</span></span>

<span data-ttu-id="44232-108">ASP.NET Core — это кросс платформенных, открытая платформа для создания современных оптимизированными для облака веб-приложений.</span><span class="sxs-lookup"><span data-stu-id="44232-108">ASP.NET Core is a cross-platform, open-source framework for building modern cloud-optimized web applications.</span></span> <span data-ttu-id="44232-109">Приложения ASP.NET Core — это упрощенный и модульной со встроенной поддержкой для внедрения зависимости, включение в больше возможностей тестирования и сопровождения.</span><span class="sxs-lookup"><span data-stu-id="44232-109">ASP.NET Core apps are lightweight and modular, with built-in support for dependency injection, enabling in greater testability and maintainability.</span></span> <span data-ttu-id="44232-110">В сочетании с MVC, который поддерживает построение современных веб-API в дополнение к приложения на основе представления, ASP.NET Core — это мощный платформа, для создания веб-приложений корпоративного.</span><span class="sxs-lookup"><span data-stu-id="44232-110">Combined with MVC, which supports building modern web APIs in addition to view-based apps, ASP.NET Core is a powerful framework with which to build enterprise web applications.</span></span>

## <a name="mapping-requests-to-responses"></a><span data-ttu-id="44232-111">Сопоставление запросов для ответов</span><span class="sxs-lookup"><span data-stu-id="44232-111">Mapping Requests to Responses</span></span>

<span data-ttu-id="44232-112">Сущность приложения ASP.NET Core назначают входящие запросы для исходящих ответов.</span><span class="sxs-lookup"><span data-stu-id="44232-112">At its heart, ASP.NET Core apps map incoming requests to outgoing responses.</span></span> <span data-ttu-id="44232-113">На низком уровне это делается с помощью по промежуточного слоя и простых приложений ASP.NET Core и микрослужбами может состоять только из пользовательских по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="44232-113">At a low level, this is done with middleware, and simple ASP.NET Core apps and microservices may be comprised solely of custom middleware.</span></span> <span data-ttu-id="44232-114">При использовании ASP.NET MVC основных компонентов, можно работать несколько более высокого уровня, подхода на основе *маршруты*, *контроллеров*, и *действия*.</span><span class="sxs-lookup"><span data-stu-id="44232-114">When using ASP.NET Core MVC, you can work at a somewhat higher level, thinking in terms of *routes*, *controllers*, and *actions*.</span></span> <span data-ttu-id="44232-115">Каждый входящий запрос сравнивается с таблицу маршрутизации для приложения, и при обнаружении подходящего маршрута для обработки запроса вызывается связанный метод действия (принадлежащих контроллера).</span><span class="sxs-lookup"><span data-stu-id="44232-115">Each incoming request is compared with the application's routing table, and if a matching route is found, the associated action method (belonging to a controller) is called to handle the request.</span></span> <span data-ttu-id="44232-116">При обнаружении подходящего маршрута, вызывается обработчик ошибок (в данном случае, возвращая результат не найдено).</span><span class="sxs-lookup"><span data-stu-id="44232-116">If no matching route is found, an error handler (in this case, returning a NotFound result) is called.</span></span>

<span data-ttu-id="44232-117">Приложения MVC ASP.NET Core можно использовать обычные маршрутов и маршрутов с атрибутами.</span><span class="sxs-lookup"><span data-stu-id="44232-117">ASP.NET Core MVC apps can use conventional routes, attribute routes, or both.</span></span> <span data-ttu-id="44232-118">Обычные маршруты были определены в коде, указав маршрутизации *соглашения* с помощью синтаксиса, как в приведенном ниже примере:</span><span class="sxs-lookup"><span data-stu-id="44232-118">Conventional routes are defined in code, specifying routing *conventions* using syntax like in the example below:</span></span>

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="44232-119">В этом примере маршрут с именем «default» добавлена в таблицу маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="44232-119">In this example, a route named "default" has been added to the routing table.</span></span> <span data-ttu-id="44232-120">Он определяет шаблон маршрута с заполнителями для *контроллера*, *действия*, и *идентификатор*. Заполнители контроллера и действия имеют значения по умолчанию («Home» и «Индекс», соответственно), и заполнитель идентификатора является необязательным (посредством «?» применяемый к нему).</span><span class="sxs-lookup"><span data-stu-id="44232-120">It defines a route template with placeholders for *controller*, *action*, and *id*. The controller and action placeholders have default specified ("Home" and "Index", respectively), and the id placeholder is optional (by virtue of a "?" applied to it).</span></span> <span data-ttu-id="44232-121">Согласно правилам для определенных здесь состояний, которые должны соответствовать первой части запроса, имя контроллера, вторая часть для этого действия, и затем при необходимости третья часть будет представлять параметр id.</span><span class="sxs-lookup"><span data-stu-id="44232-121">The convention defined here states that the first part of a request should correspond to the name of the controller, the second part to the action, and then if necessary a third part will represent an id parameter.</span></span> <span data-ttu-id="44232-122">Обычные маршруты обычно определяются в одном месте для приложения, такие как Настройка метода в класс Startup.</span><span class="sxs-lookup"><span data-stu-id="44232-122">Conventional routes are typically defined in one place for the application, such as in the Configure method in the Startup class.</span></span>

<span data-ttu-id="44232-123">Атрибут маршруты, применяется непосредственно к контроллерам и действия, а не указан глобально.</span><span class="sxs-lookup"><span data-stu-id="44232-123">Attribute routes are applied to controllers and actions directly, rather than specified globally.</span></span> <span data-ttu-id="44232-124">Это преимущество становятся гораздо более доступными при вы просматриваете конкретного метода, но означает, что сведения о маршрутизации не будет содержаться в одном месте в приложении.</span><span class="sxs-lookup"><span data-stu-id="44232-124">This has the advantage of making them much more discoverable when you're looking at a particular method, but does mean that routing information is not kept in one place in the application.</span></span> <span data-ttu-id="44232-125">Маршруты атрибута вы можно легко указать несколько маршрутов для выполнения данного действия, а также объединять маршруты между контроллеров и действий.</span><span class="sxs-lookup"><span data-stu-id="44232-125">With attribute routes, you can easily specify multiple routes for a given action, as well as combine routes between controllers and actions.</span></span> <span data-ttu-id="44232-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="44232-126">For example:</span></span>

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

<span data-ttu-id="44232-127">Маршруты могут быть заданы в [HttpGet] и похожими атрибутами, устраняя необходимость добавить отделения [маршрута\] атрибуты.</span><span class="sxs-lookup"><span data-stu-id="44232-127">Routes can be specified on [HttpGet] and similar attributes, avoiding the need to add separate [Route\] attributes.</span></span> <span data-ttu-id="44232-128">Маршруты атрибута также можно использовать токены для уменьшения необходимость повторения имена контроллер или действие, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="44232-128">Attribute routes can also use tokens to reduce the need to repeat controller or action names, as shown below:</span></span>

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

<span data-ttu-id="44232-129">После указанного запроса было сопоставлено с маршрутом, но перед действием будет вызван, будет выполнять ASP.NET Core MVC [привязки модели](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) и [проверка модели](https://docs.microsoft.com/aspnet/core/mvc/models/validation) в запросе.</span><span class="sxs-lookup"><span data-stu-id="44232-129">Once a given request has been matched to a route, but before the action method is called, ASP.NET Core MVC will perform [model binding](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) and [model validation](https://docs.microsoft.com/aspnet/core/mvc/models/validation) on the request.</span></span> <span data-ttu-id="44232-130">Привязка модели отвечает за преобразование входящих HTTP-данных в типы .NET, определяются как параметры метода действия для вызова.</span><span class="sxs-lookup"><span data-stu-id="44232-130">Model binding is responsible for converting incoming HTTP data into the .NET types specified as parameters of the action method to be called.</span></span> <span data-ttu-id="44232-131">Например если метод действия требуется параметр id int, привязки модели будет пытаться предоставить этот параметр со значением параметра предоставляется как часть запроса.</span><span class="sxs-lookup"><span data-stu-id="44232-131">For example, if the action method expects an int id parameter, model binding will attempt to provide this parameter from a value provided as part of the request.</span></span> <span data-ttu-id="44232-132">Чтобы сделать это, привязки модели выполняет поиск значения в отправленной формы, значения в сам маршрут и значения строки запроса.</span><span class="sxs-lookup"><span data-stu-id="44232-132">To do so, model binding looks for values in a posted form, values in the route itself, and query string values.</span></span> <span data-ttu-id="44232-133">Предположим, что найдено значение идентификатора, он преобразуется в целое перед передачей в метод действия.</span><span class="sxs-lookup"><span data-stu-id="44232-133">Assuming an id value is found, it will be converted to an integer before being passed into the action method.</span></span>

<span data-ttu-id="44232-134">После привязки модели, но перед вызовом метода действия выполняется проверка модели.</span><span class="sxs-lookup"><span data-stu-id="44232-134">After binding the model but before calling the action method, model validation occurs.</span></span> <span data-ttu-id="44232-135">Проверка модели использует необязательные атрибуты типа модели и помогут обеспечить соответствие определенным требованиям данных объект заданной модели.</span><span class="sxs-lookup"><span data-stu-id="44232-135">Model validation uses optional attributes on the model type, and can help ensure that the provided model object conforms to certain data requirements.</span></span> <span data-ttu-id="44232-136">Некоторые значения могут быть указаны как необходимые или ограниченные длины или числовой диапазон, и т. д. Если указаны атрибуты проверки, но модель не соответствует их требованиям, свойство ModelState.IsValid будет иметь значение false и набор сбойных правил проверки будет доступен для отправки клиенту, выполняющего запрос.</span><span class="sxs-lookup"><span data-stu-id="44232-136">Certain values may be specified as required, or limited to a certain length or numeric range, etc. If validation attributes are specified but the model does not conform to their requirements, the property ModelState.IsValid will be false, and the set of failing validation rules will be available to send to the client making the request.</span></span>

<span data-ttu-id="44232-137">При использовании проверки модели следует убедиться, что всегда модели выполняется проверка допустимости перед выполнением любые изменения состояния команды, чтобы убедиться, что приложение не повреждены, недопустимые данные.</span><span class="sxs-lookup"><span data-stu-id="44232-137">If you are using model validation, you should be sure to always check that the model is valid before performing any state-altering commands, to ensure your app is not corrupted by invalid data.</span></span> <span data-ttu-id="44232-138">Можно использовать [фильтра](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) позволяет избежать необходимости, чтобы добавить код для этого в каждом действии.</span><span class="sxs-lookup"><span data-stu-id="44232-138">You can use a [filter](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) to avoid the need to add code for this in every action.</span></span> <span data-ttu-id="44232-139">Фильтры MVC ASP.NET Core позволяют перехватывающего группы запросов, таким образом, можно применять на основе целевого общую политики и проблемы пересечения.</span><span class="sxs-lookup"><span data-stu-id="44232-139">ASP.NET Core MVC filters offer a way of intercepting groups of requests, so that common policies and cross-cutting concerns can be applied on a targeted basis.</span></span> <span data-ttu-id="44232-140">Фильтры могут применяться для отдельных действий, всего контроллеров или для приложения.</span><span class="sxs-lookup"><span data-stu-id="44232-140">Filters can be applied to individual actions, whole controllers, or globally for an application.</span></span>

<span data-ttu-id="44232-141">Для веб-API ASP.NET Core MVC поддерживает [ *содержимого согласования*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), разрешение запросов указать, как следует форматировать ответов.</span><span class="sxs-lookup"><span data-stu-id="44232-141">For web APIs, ASP.NET Core MVC supports [*content negotiation*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), allowing requests to specify how responses should be formatted.</span></span> <span data-ttu-id="44232-142">На основании заголовки, предоставляемые в запросе, действия, возвращая данные форматирования ответа в XML, JSON или другом поддерживаемом формате.</span><span class="sxs-lookup"><span data-stu-id="44232-142">Based on headers provided in the request, actions returning data will format the response in XML, JSON, or another supported format.</span></span> <span data-ttu-id="44232-143">Эта функция обеспечивает такой же API для использования с различными данными требования к формату несколькими клиентами.</span><span class="sxs-lookup"><span data-stu-id="44232-143">This feature enables the same API to be used by multiple clients with different data format requirements.</span></span>

> ### <a name="references--mapping-requests-to-responses"></a><span data-ttu-id="44232-144">Ссылки — сопоставление запросов для ответов</span><span class="sxs-lookup"><span data-stu-id="44232-144">References – Mapping Requests to Responses</span></span>
> - <span data-ttu-id="44232-145">**Маршрутизация в действиях контроллера**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span><span class="sxs-lookup"><span data-stu-id="44232-145">**Routing to Controller Actions**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span></span>
> - <span data-ttu-id="44232-146">**Привязки модели** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span><span class="sxs-lookup"><span data-stu-id="44232-146">**Model Binding** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span></span>
> - <span data-ttu-id="44232-147">**Проверка модели**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation></span><span class="sxs-lookup"><span data-stu-id="44232-147">**Model Validation**
<https://docs.microsoft.com/aspnet/core/mvc/models/validation></span></span>
> - <span data-ttu-id="44232-148">**Filters** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span><span class="sxs-lookup"><span data-stu-id="44232-148">**Filters** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span></span>

## <a name="working-with-dependencies"></a><span data-ttu-id="44232-149">Работа с зависимостями</span><span class="sxs-lookup"><span data-stu-id="44232-149">Working with Dependencies</span></span>

<span data-ttu-id="44232-150">ASP.NET Core имеет встроенную поддержку и внутренним образом использует подход, называемый [внедрения зависимостей](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="44232-150">ASP.NET Core has built-in support for and internally makes use of a technique known as [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="44232-151">Внедрение зависимостей — это методика, которая обеспечивает слабую связь между разными частями приложения.</span><span class="sxs-lookup"><span data-stu-id="44232-151">Dependency injection is a technique that enabled loose coupling between different parts of an application.</span></span> <span data-ttu-id="44232-152">Свободную привязку является предпочтительным, так как он позволяет упростить для изоляции частей приложения, что для тестирования или замены.</span><span class="sxs-lookup"><span data-stu-id="44232-152">Looser coupling is desirable because it makes it easier to isolate parts of the application, allowing for testing or replacement.</span></span> <span data-ttu-id="44232-153">Кроме того, он менее вероятно, что изменение в одной части приложения будет иметь непредвиденного влияния где-либо еще в приложении.</span><span class="sxs-lookup"><span data-stu-id="44232-153">It also makes it less likely that a change in one part of the application will have an unexpected impact somewhere else in the application.</span></span> <span data-ttu-id="44232-154">Внедрение зависимостей на основании принципом инверсии зависимостей и часто является достижение принцип открытый/закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="44232-154">Dependency injection is based on the dependency inversion principle, and is often key to achieving the open/closed principle.</span></span> <span data-ttu-id="44232-155">При оценке, как приложение работает с зависимостями, учтите, что [статических напечатанными](http://deviq.com/static-cling/) вонь от кода и запоминать aphorism "[новый связующего](http://ardalis.com/new-is-glue).»</span><span class="sxs-lookup"><span data-stu-id="44232-155">When evaluating how your application works with its dependencies, beware of the [static cling](http://deviq.com/static-cling/) code smell, and remember the aphorism "[new is glue](http://ardalis.com/new-is-glue)."</span></span>

<span data-ttu-id="44232-156">Статические напечатанными происходит, когда ваши классы вызывать статические методы или доступ статических свойств, которые имеют побочные эффекты или зависимости от инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="44232-156">Static cling occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.</span></span> <span data-ttu-id="44232-157">Например если у вас есть метод, который вызывает статический метод, который в свою очередь выполняет запись в базу данных, метод тесно связана с базы данных.</span><span class="sxs-lookup"><span data-stu-id="44232-157">For example, if you have a method that calls a static method, which in turn writes to a database, your method is tightly coupled to the database.</span></span> <span data-ttu-id="44232-158">Все, что разрывы, вызывающих метод базы данных приведет к разрыву метод.</span><span class="sxs-lookup"><span data-stu-id="44232-158">Anything that breaks that database call will break your method.</span></span> <span data-ttu-id="44232-159">Тестирование таких методов — это трудные, поскольку такие тесты необходимы коммерческих имитации библиотеки для макета вызывает статический, либо можно протестировать с тестовую базу данных на месте.</span><span class="sxs-lookup"><span data-stu-id="44232-159">Testing such methods is notoriously difficult, since such tests either require commercial mocking libraries to mock the static calls, or can only be tested with a test database in place.</span></span> <span data-ttu-id="44232-160">Статические вызовы, которые не являются любые зависимость от инфраструктуры, особенно тех, которые не полностью поддерживает состояние, допустимы для вызова и не влияют на соединения или пригодности для тестирования (помимо взаимозависимость код в сам вызов статических).</span><span class="sxs-lookup"><span data-stu-id="44232-160">Static calls that don't have any dependence on infrastructure, especially those that are completely stateless, are fine to call and have no impact on coupling or testability (beyond coupling code to the static call itself).</span></span>

<span data-ttu-id="44232-161">Многие разработчики понимаете риски статических напечатанными и глобальное состояние, но будет по-прежнему тесно связать свой код для определенных реализаций через прямое создание экземпляров.</span><span class="sxs-lookup"><span data-stu-id="44232-161">Many developers understand the risks of static cling and global state, but will still tightly couple their code to specific implementations through direct instantiation.</span></span> <span data-ttu-id="44232-162">«Новый связующего» должен быть напоминание такое объединение, а не общие condemnation использование ключевое слово new.</span><span class="sxs-lookup"><span data-stu-id="44232-162">"New is glue" is meant to be a reminder of this coupling, and not a general condemnation of the use of the new keyword.</span></span> <span data-ttu-id="44232-163">Так же, как с помощью вызовов статических методов, новые экземпляры типов, которые не имеют внешних зависимостей обычно не тесно привязать к сведения о реализации кода или затруднить тестирования.</span><span class="sxs-lookup"><span data-stu-id="44232-163">Just as with static method calls, new instances of types that have no external dependencies typically do not tightly couple code to implementation details or make testing more difficult.</span></span> <span data-ttu-id="44232-164">Однако каждый раз, когда создается экземпляр класса, просто короткий промежуток времени следует учитывать ли смысл в коде этого конкретного экземпляра в определенном месте или было бы изменить оформление запрашивать этот экземпляр в качестве зависимости.</span><span class="sxs-lookup"><span data-stu-id="44232-164">But each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.</span></span>

### <a name="declare-your-dependencies"></a><span data-ttu-id="44232-165">Объявите зависимостей</span><span class="sxs-lookup"><span data-stu-id="44232-165">Declare Your Dependencies</span></span>

<span data-ttu-id="44232-166">ASP.NET Core строится с методы и классы объявите их зависимости, запросив их как аргументы.</span><span class="sxs-lookup"><span data-stu-id="44232-166">ASP.NET Core is built around having methods and classes declare their dependencies, requesting them as arguments.</span></span> <span data-ttu-id="44232-167">Приложения ASP.NET обычно настраиваются в классе запуска, который в свою очередь, настроена поддержка внедрения зависимостей в нескольких точках.</span><span class="sxs-lookup"><span data-stu-id="44232-167">ASP.NET applications are typically set up in a Startup class, which itself is configured to support dependency injection at several points.</span></span> <span data-ttu-id="44232-168">Если при запуске класс имеет конструктор, его можно запросить через конструктор, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="44232-168">If your Startup class has a constructor, it can request dependencies through the constructor, like so:</span></span>

```csharp
public class Startup
{
    public Startup(IHostingEnvironment env)
    {
        var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
        .AddJsonFile(\$"appsettings.{env.EnvironmentName}.json", optional: true);
    }
}
```

<span data-ttu-id="44232-169">Класс Startup представляет интерес, в том, что явный тип требования для него отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="44232-169">The Startup class is interesting in that there are no explicit type requirements for it.</span></span> <span data-ttu-id="44232-170">Он не наследуется от базового класса специальные запуска, а также реализовать любой определенный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="44232-170">It doesn't inherit from a special Startup base class, nor does it implement any particular interface.</span></span> <span data-ttu-id="44232-171">Ему можно присвоить конструктор, или нет и указать необходимое количество параметров в конструкторе требуется.</span><span class="sxs-lookup"><span data-stu-id="44232-171">You can give it a constructor, or not, and you can specify as many parameters on the constructor as you want.</span></span> <span data-ttu-id="44232-172">При запуске веб-узла, настроенному для вашего приложения, он будет вызывать при запуске класса, который вы указано, что для использования и будет использовать внедрения зависимостей для заполнения все зависимости, необходимые для запуска класса.</span><span class="sxs-lookup"><span data-stu-id="44232-172">When the web host you've configured for your application starts, it will call the Startup class you've told it to use, and will use dependency injection to populate any dependencies the Startup class requires.</span></span> <span data-ttu-id="44232-173">Конечно Если параметры, которые не настроены в контейнере службы, используемые ASP.NET Core запроса, будет вызвано исключение, но при условии, что вы будете использовать зависимости контейнера известны, можно запросить любым способом.</span><span class="sxs-lookup"><span data-stu-id="44232-173">Of course, if you request parameters that aren't configured in the services container used by ASP.NET Core, you'll get an exception, but as long as you stick to dependencies the container knows about, you can request anything you want.</span></span>

<span data-ttu-id="44232-174">При создании экземпляра запуска внедрения зависимостей встроены в приложения ASP.NET Core с самого начала.</span><span class="sxs-lookup"><span data-stu-id="44232-174">Dependency injection is built into your ASP.NET Core apps right from the start, when you create the Startup instance.</span></span> <span data-ttu-id="44232-175">Он еще не класса начальной.</span><span class="sxs-lookup"><span data-stu-id="44232-175">It doesn't stop there for the Startup class.</span></span> <span data-ttu-id="44232-176">Можно также запросить зависимостей в метод конфигурации:</span><span class="sxs-lookup"><span data-stu-id="44232-176">You can also request dependencies in the Configure method:</span></span>

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

<span data-ttu-id="44232-177">Метод ConfigureServices является исключением из этого поведения; она должна принимать только один параметр типа IServiceCollection.</span><span class="sxs-lookup"><span data-stu-id="44232-177">The ConfigureServices method is the exception to this behavior; it must take just one parameter of type IServiceCollection.</span></span> <span data-ttu-id="44232-178">Он не потребуются для поддержки внедрения зависимостей, так как с одной стороны он отвечает за добавление объектов в контейнере службы, а с другой, он имеет доступ ко всем службам, настроенных через параметр IServiceCollection.</span><span class="sxs-lookup"><span data-stu-id="44232-178">It doesn't really need to support dependency injection, since on the one hand it is responsible for adding objects to the services container, and on the other it has access to all currently configured services via the IServiceCollection parameter.</span></span> <span data-ttu-id="44232-179">Таким образом можно работать с зависимостями, определенным в коллекции служб ASP.NET Core в каждой части класса запуска, запросив необходимые службы, как параметр или при работе с IServiceCollection в ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="44232-179">Thus, you can work with dependencies defined in the ASP.NET Core services collection in every part of the Startup class, either by requesting the needed service as a parameter or by working with the IServiceCollection in ConfigureServices.</span></span>

> [!NOTE]
> <span data-ttu-id="44232-180">Если требуется обеспечить доступность в класс запуска определенных служб, их можно настроить с помощью WebHostBuilder и его ConfigureServices метода.</span><span class="sxs-lookup"><span data-stu-id="44232-180">If you need to ensure certain services are available to your Startup class, you can configure them using WebHostBuilder and its ConfigureServices method.</span></span>

<span data-ttu-id="44232-181">Класс запуска — это модель для требуемой структуре других частей приложения ASP.NET Core из контроллеров с по промежуточного слоя, чтобы фильтры для собственных служб.</span><span class="sxs-lookup"><span data-stu-id="44232-181">The Startup class is a model for how you should structure other parts of your ASP.NET Core application, from Controllers to Middleware to Filters to your own Services.</span></span> <span data-ttu-id="44232-182">В каждом случае необходимо следовать [явные зависимости принцип](http://deviq.com/explicit-dependencies-principle/), запрашивающего зависимостей, а не непосредственно их создание и использование внедрения зависимостей во всем приложении.</span><span class="sxs-lookup"><span data-stu-id="44232-182">In each case, you should follow the [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/), requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.</span></span> <span data-ttu-id="44232-183">Будьте внимательны из где и как можно непосредственно создать экземпляр реализации, особенно службы и объекты, которые работают с инфраструктурой или иметь побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="44232-183">Be careful of where and how you directly instantiate implementations, especially services and objects that work with infrastructure or have side effects.</span></span> <span data-ttu-id="44232-184">Предпочтение работе с абстрактные классы определены в основные приложения и переданных в качестве аргументов для жесткого задания ссылки на типы конкретной реализации.</span><span class="sxs-lookup"><span data-stu-id="44232-184">Prefer working with abstractions defined in your application core and passed in as arguments to hardcoding references to specific implementation types.</span></span>

## <a name="structuring-the-application"></a><span data-ttu-id="44232-185">Структурирование приложения</span><span class="sxs-lookup"><span data-stu-id="44232-185">Structuring the Application</span></span>

<span data-ttu-id="44232-186">Монолитные приложения обычно имеют одну точку входа.</span><span class="sxs-lookup"><span data-stu-id="44232-186">Monolithic applications typically have a single entry point.</span></span> <span data-ttu-id="44232-187">В случае веб-приложения ASP.NET Core точка входа будет веб-проекта ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44232-187">In the case of an ASP.NET Core web application, the entry point will be the ASP.NET Core web project.</span></span> <span data-ttu-id="44232-188">Тем не менее, это не означает, что решение должно состоять из одного проекта.</span><span class="sxs-lookup"><span data-stu-id="44232-188">However, that doesn't mean the solution should consist of just a single project.</span></span> <span data-ttu-id="44232-189">Полезно разбить приложение в различные слои, чтобы выполнить разделение областей ответственности.</span><span class="sxs-lookup"><span data-stu-id="44232-189">It's useful to break up the application into different layers in order to follow separation of concerns.</span></span> <span data-ttu-id="44232-190">После разбитого на слои, бывает полезно выходит за пределы папки для проектов, которые могут помочь добиться улучшенную инкапсуляцию разделения.</span><span class="sxs-lookup"><span data-stu-id="44232-190">Once broken up into layers, it's helpful to go beyond folders to separate projects, which can help achieve better encapsulation.</span></span> <span data-ttu-id="44232-191">Для достижения этих целей с приложением ASP.NET Core лучшим подходом является разновидностью чистой архитектуры, описанных в главе 5.</span><span class="sxs-lookup"><span data-stu-id="44232-191">The best approach to achieve these goals with an ASP.NET Core application is a variation of the Clean Architecture discussed in chapter 5.</span></span> <span data-ttu-id="44232-192">Следующий подход решение приложения будет состоять из отдельных библиотек для пользовательского интерфейса, инфраструктуры и ApplicationCore.</span><span class="sxs-lookup"><span data-stu-id="44232-192">Following this approach, the application's solution will be comprised of separate libraries for the UI, Infrastructure, and ApplicationCore.</span></span>

<span data-ttu-id="44232-193">Помимо этих проектах отдельных тестовых проектов включены также (тестирование рассматривается в главе 9).</span><span class="sxs-lookup"><span data-stu-id="44232-193">In addition to these projects, separate test projects are included as well (Testing is discussed in Chapter 9).</span></span>

<span data-ttu-id="44232-194">Объектная модель приложения и интерфейсы должны размещаться в проекте ApplicationCore.</span><span class="sxs-lookup"><span data-stu-id="44232-194">The application's object model and interfaces should be placed in the ApplicationCore project.</span></span> <span data-ttu-id="44232-195">Этот проект будет содержать как можно меньшее число зависимостей можно и другие проекты в решении будет ссылаться на него.</span><span class="sxs-lookup"><span data-stu-id="44232-195">This project will have as few dependencies as possible, and the other projects in the solution will reference it.</span></span> <span data-ttu-id="44232-196">Бизнес-сущности, которые необходимо сохранить определенные в проекте ApplicationCore, как службы, которые непосредственно не зависящие от инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="44232-196">Business entities that need to be persisted are defined in the ApplicationCore project, as are services that do not directly depend on infrastructure.</span></span>

<span data-ttu-id="44232-197">Особенности реализации, например, как выполняется сохраняемости или как уведомления могут отправляться пользователю, хранятся в проекте инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="44232-197">Implementation details, such as how persistence is performed or how notifications might be sent to a user, are kept in the Infrastructure project.</span></span> <span data-ttu-id="44232-198">Этот проект будет ссылаться на пакеты зависит от реализации, такие как Entity Framework Core, но не должны предоставлять подробные сведения об этих реализаций вне проекта.</span><span class="sxs-lookup"><span data-stu-id="44232-198">This project will reference implementation-specific packages such as Entity Framework Core, but should not expose details about these implementations outside of the project.</span></span> <span data-ttu-id="44232-199">Репозиториев и службы инфраструктуры, которые должны реализовывать интерфейсы, определенные в проекте ApplicationCore и его реализация сохраняемости отвечают за получение и сохранение сущностей, определенных в ApplicationCore.</span><span class="sxs-lookup"><span data-stu-id="44232-199">Infrastructure services and repositories should implement interfaces that are defined in the ApplicationCore project, and its persistence implementations are responsible for retrieving and storing entities defined in ApplicationCore.</span></span>

<span data-ttu-id="44232-200">Сам проект ASP.NET Core несет ответственность за любые проблемы уровня пользовательского интерфейса, но не должно содержать сведения о компании логики или инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="44232-200">The ASP.NET Core project itself is responsible for any UI level concerns, but should not include business logic or infrastructure details.</span></span> <span data-ttu-id="44232-201">На самом деле в идеальном случае его не следует даже имеют зависимость от проекта инфраструктуры, который поможет обеспечить успешную случайно введен никакой зависимости между двумя проектами.</span><span class="sxs-lookup"><span data-stu-id="44232-201">In fact, ideally it shouldn't even have a dependency on the Infrastructure project, which will help ensure no dependency between the two projects is introduced accidentally.</span></span> <span data-ttu-id="44232-202">Это можно сделать с помощью сторонних DI контейнера как StructureMap, который позволяет определить правила DI реестра классов в каждом проекте.</span><span class="sxs-lookup"><span data-stu-id="44232-202">This can be achieved using a third-party DI container like StructureMap, which allows you to define DI rules in Registry classes in each project.</span></span>

<span data-ttu-id="44232-203">Другой подход к отделение приложения от конкретной реализации является микрослужбами вызов приложения, может быть развернут в отдельные контейнеры Docker.</span><span class="sxs-lookup"><span data-stu-id="44232-203">Another approach to decoupling the application from implementation details is to have the application call microservices, perhaps deployed in individual Docker containers.</span></span> <span data-ttu-id="44232-204">Это обеспечивает улучшенное разделение о проблемах и отделение, чем использование DI между двумя проектами, но также имеет дополнительные сложности.</span><span class="sxs-lookup"><span data-stu-id="44232-204">This provides even greater separation of concerns and decoupling than leveraging DI between two projects, but has additional complexity.</span></span>

### <a name="feature-organization"></a><span data-ttu-id="44232-205">Функция организации</span><span class="sxs-lookup"><span data-stu-id="44232-205">Feature Organization</span></span>

<span data-ttu-id="44232-206">По умолчанию приложения ASP.NET Core организовывать их структуру папок для включения контроллеров, представлений и часто ViewModels.</span><span class="sxs-lookup"><span data-stu-id="44232-206">By default, ASP.NET Core applications organize their folder structure to include Controllers and Views, and frequently ViewModels.</span></span> <span data-ttu-id="44232-207">Код на стороне клиента для поддержки этих структур серверные отдельно обычно хранится в папке wwwroot.</span><span class="sxs-lookup"><span data-stu-id="44232-207">Client-side code to support these server-side structures is typically stored separately in the wwwroot folder.</span></span> <span data-ttu-id="44232-208">Однако крупных приложений могут возникнуть проблемы с этой организации, поскольку часто работать на любой данной функции требуется переходе между этими папками.</span><span class="sxs-lookup"><span data-stu-id="44232-208">However, large applications may encounter problems with this organization, since working on any given feature often requires jumping between these folders.</span></span> <span data-ttu-id="44232-209">Это возвращает более сложность по мере роста числа файлы и вложенные папки из каждой папки приведет к значительные возможности прокрутки с помощью обозревателя решений.</span><span class="sxs-lookup"><span data-stu-id="44232-209">This gets more and more difficult as the number of files and subfolders in each folder grows, resulting in a great deal of scrolling through Solution Explorer.</span></span> <span data-ttu-id="44232-210">Одно из решений этой проблемы является для организации кода приложения с *функция* вместо по тип файла.</span><span class="sxs-lookup"><span data-stu-id="44232-210">One solution to this problem is to organize application code by *feature* instead of by file type.</span></span> <span data-ttu-id="44232-211">Этот стиль организации обычно называется папки функций или компонентов фрагментов (см. также: [вертикальные срезы](http://deviq.com/vertical-slices/)).</span><span class="sxs-lookup"><span data-stu-id="44232-211">This organizational style is typically referred to as feature folders or feature slices (see also: [Vertical Slices](http://deviq.com/vertical-slices/)).</span></span>

<span data-ttu-id="44232-212">ASP.NET Core MVC поддерживает областей для этой цели.</span><span class="sxs-lookup"><span data-stu-id="44232-212">ASP.NET Core MVC supports Areas for this purpose.</span></span> <span data-ttu-id="44232-213">Использование областей, можно создать отдельные наборы контроллеры и представления папок (а также все связанные модели) в каждой папке области.</span><span class="sxs-lookup"><span data-stu-id="44232-213">Using areas, you can create separate sets of Controllers and Views folders (as well as any associated models) in each Area folder.</span></span> <span data-ttu-id="44232-214">Рис. 7-1 показан пример структуры папок, использование областей.</span><span class="sxs-lookup"><span data-stu-id="44232-214">Figure 7-1 shows an example folder structure, using Areas.</span></span>

![](./media/image7-1.png)

<span data-ttu-id="44232-215">Рис. 7-1 Пример области организации</span><span class="sxs-lookup"><span data-stu-id="44232-215">Figure 7-1 Sample Area Organization</span></span>

<span data-ttu-id="44232-216">При использовании области, необходимо использовать атрибуты для оформления контроллеры с имя области, к которому они принадлежат:</span><span class="sxs-lookup"><span data-stu-id="44232-216">When using Areas, you must use attributes to decorate your controllers with the name of the area to which they belong:</span></span>

```csharp
[Area("Catalog")]
public class HomeController
{}
```

<span data-ttu-id="44232-217">Также необходим для добавления поддержки области свои маршруты.</span><span class="sxs-lookup"><span data-stu-id="44232-217">You also need to add area support to your routes:</span></span>

```csharp
app.UseMvc(routes =>
{
    // Areas support
    routes.MapRoute(
    name: "areaRoute",
    template: "{area:exists}/{controller=Home}/{action=Index}/{id?}");
    routes.MapRoute(
    name: "default",
    template: "{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="44232-218">Помимо встроенной поддержки для областей также можно использовать собственные структуры папок и соглашения вместо атрибутов и настраиваемых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="44232-218">In addition to the built-in support for Areas, you can also use your own folder structure, and conventions in place of attributes and custom routes.</span></span> <span data-ttu-id="44232-219">Это позволит иметь папки функций, которые не были включены отдельные папки для представления, контроллеры, т. д., поддержание иерархии плоское и упрощает для просмотра все связанные файлы в одном месте для каждого компонента.</span><span class="sxs-lookup"><span data-stu-id="44232-219">This would allow you to have feature folders that didn't include separate folders for Views, Controllers, etc., keeping the hierarchy flatter and making it easier to see all related files in a single place for each feature.</span></span>

<span data-ttu-id="44232-220">ASP.NET Core использует соглашение о встроенные типы для управления их поведением.</span><span class="sxs-lookup"><span data-stu-id="44232-220">ASP.NET Core uses built-in convention types to control its behavior.</span></span> <span data-ttu-id="44232-221">Можно изменить или заменить эти соглашения.</span><span class="sxs-lookup"><span data-stu-id="44232-221">You can modify or replace these conventions.</span></span> <span data-ttu-id="44232-222">Например можно создать соглашение, которое автоматически получают имя компонента для данного контроллера, в зависимости от его пространство имен (который обычно связано с папки, в котором расположен контроллер):</span><span class="sxs-lookup"><span data-stu-id="44232-222">For example, you can create a convention that will automatically get the feature name for a given controller based on its namespace (which typically correlates to the folder in which the controller is located):</span></span>

```csharp
FeatureConvention : IControllerModelConvention
{
    public void Apply(ControllerModel controller)
    {
        controller.Properties.Add("feature",
        GetFeatureName(controller.ControllerType));
    }

    private string GetFeatureName(TypeInfo controllerType)
    {
        string[] tokens = controllerType.FullName.Split('.');
        if (!tokens.Any(t => t == "Features")) return "";
        string featureName = tokens
        .SkipWhile(t => !t.Equals("features",
        StringComparison.CurrentCultureIgnoreCase))
        .Skip(1)
        .Take(1)
        .FirstOrDefault();
        return featureName;
    }
}
```

<span data-ttu-id="44232-223">Затем указываются это соглашение в качестве альтернативы после добавления поддержки для MVC в ConfigureServices приложение.</span><span class="sxs-lookup"><span data-stu-id="44232-223">You then specify this convention as an option when you add support for MVC to your application in ConfigureServices:</span></span>

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

<span data-ttu-id="44232-224">ASP.NET Core MVC также используется соглашение для поиска представления.</span><span class="sxs-lookup"><span data-stu-id="44232-224">ASP.NET Core MVC also uses a convention to locate views.</span></span> <span data-ttu-id="44232-225">Его можно переопределить с помощью пользовательского соглашения, чтобы представления будет находиться в папках функции (с помощью имя функции, предоставляемые FeatureConvention выше).</span><span class="sxs-lookup"><span data-stu-id="44232-225">You can override it with a custom convention so that views will be located in your feature folders (using the feature name provided by the FeatureConvention, above).</span></span> <span data-ttu-id="44232-226">Можно узнать больше об этом подходе и загрузить рабочий образец из статьи MSDN [фрагментов функции для ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span><span class="sxs-lookup"><span data-stu-id="44232-226">You can learn more about this approach and download a working sample from the MSDN article, [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span></span>

### <a name="cross-cutting-concerns"></a><span data-ttu-id="44232-227">Сквозная функциональность</span><span class="sxs-lookup"><span data-stu-id="44232-227">Cross-Cutting Concerns</span></span>

<span data-ttu-id="44232-228">По мере роста приложения становится все более важными вынести решении общих задач, чтобы избежать дублирования и поддержания согласованности.</span><span class="sxs-lookup"><span data-stu-id="44232-228">As applications grow, it becomes increasingly important to factor out cross-cutting concerns to eliminate duplication and maintain consistency.</span></span> <span data-ttu-id="44232-229">Некоторые примеры перекрестными проблемы в приложениях ASP.NET Core, проверки подлинности, правила проверки модели, кэширование вывода и обработки ошибок, хотя и существуют многие другие.</span><span class="sxs-lookup"><span data-stu-id="44232-229">Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling, though there are many others.</span></span> <span data-ttu-id="44232-230">ASP.NET Core MVC [фильтры](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) позволяют выполнять код до или после определенных действий в конвейер обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="44232-230">ASP.NET Core MVC [filters](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) allow you to run code before or after certain steps in the request processing pipeline.</span></span> <span data-ttu-id="44232-231">Например фильтр можно запустить до и после привязки модели, до и после действия, или перед и после результата действия.</span><span class="sxs-lookup"><span data-stu-id="44232-231">For instance, a filter can run before and after model binding, before and after an action, or before and after an action's result.</span></span> <span data-ttu-id="44232-232">Также можно использовать фильтр авторизации для управления доступом к оставшуюся часть конвейера.</span><span class="sxs-lookup"><span data-stu-id="44232-232">You can also use an authorization filter to control access to the rest of the pipeline.</span></span> <span data-ttu-id="44232-233">Рисунки 7-2 показывает способ запроса выполнения потоков фильтры, если настроен.</span><span class="sxs-lookup"><span data-stu-id="44232-233">Figures 7-2 shows how request execution flows through filters, if configured.</span></span>

![Запрос обрабатывается посредством фильтров авторизации, фильтров ресурсов, привязки модели, фильтров действий, выполнения действия и преобразования результата действия, фильтров исключений, фильтров результатов и выполнения результатов.](./media/image7-2.png)

<span data-ttu-id="44232-236">Выполнение запроса на рис. 7-2 через фильтры и конвейер обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="44232-236">Figure 7-2 Request execution through filters and request pipeline.</span></span>

<span data-ttu-id="44232-237">Фильтры обычно реализуются как атрибуты, поэтому их можно применить контроллеров или действий.</span><span class="sxs-lookup"><span data-stu-id="44232-237">Filters are usually implemented as attributes, so you can apply them controllers or actions.</span></span> <span data-ttu-id="44232-238">При добавлении таким образом, указанные на переопределение уровня действия или сборки после фильтров, определенных на уровне контроллера, фильтры какие сами переопределить глобальные фильтры.</span><span class="sxs-lookup"><span data-stu-id="44232-238">When added in this fashion, filters specified at the action level override or build upon filters specified at the controller level, which themselves override global filters.</span></span> <span data-ttu-id="44232-239">Например \[маршрута\] атрибут может использоваться для создания маршрутов, контроллеров и действий.</span><span class="sxs-lookup"><span data-stu-id="44232-239">For example, the \[Route\] attribute can be used to build up routes between controllers and actions.</span></span> <span data-ttu-id="44232-240">Аналогично авторизации можно настроить на уровне контроллера и затем переопределить с помощью отдельных действий, как показано в следующем образце:</span><span class="sxs-lookup"><span data-stu-id="44232-240">Likewise, authorization can be configured at the controller level, and then overridden by individual actions, as the following sample demonstrates:</span></span>

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

<span data-ttu-id="44232-241">Первый метод, имени входа, использует фильтр AllowAnonymous (атрибут) для переопределения фильтра авторизации на уровне контроллера.</span><span class="sxs-lookup"><span data-stu-id="44232-241">The first method, Login, uses the AllowAnonymous filter (attribute) to override the Authorize filter set at the controller level.</span></span> <span data-ttu-id="44232-242">Действие забыт пароль (и другие действия в классе, который не имеет атрибута AllowAnonymous) потребуется запрос с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="44232-242">The ForgotPassword action (and any other action in the class that doesn't have an AllowAnonymous attribute) will require an authenticated request.</span></span>

<span data-ttu-id="44232-243">Можно использовать фильтры для исключения дублирования в форме распространенной ошибкой обработки политики для API-интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="44232-243">Filters can be used to eliminate duplication in the form of common error handling policies for APIs.</span></span> <span data-ttu-id="44232-244">Например типичный политики API является возврат NotFound ответа на запросы, ссылающиеся на ключи, которые не существуют, а ответ неправильный запрос при сбое проверки модели.</span><span class="sxs-lookup"><span data-stu-id="44232-244">For example, a typical API policy is to return a NotFound response to requests referencing keys that do not exist, and a BadRequest response if model validation fails.</span></span> <span data-ttu-id="44232-245">В следующем примере демонстрируется эти две политики в действии:</span><span class="sxs-lookup"><span data-stu-id="44232-245">The following example demonstrates these two policies in action:</span></span>

```csharp
[HttpPut("{id}")]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    if ((await _authorRepository.ListAsync()).All(a => a.Id != id))
    {
        return NotFound(id);
    }
    if (!ModelState.IsValid)
    {
        return BadRequest(ModelState);
    }
    author.Id = id;
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="44232-246">Запретить использование определенных методов действия для становятся переполнения условного кода следующим образом.</span><span class="sxs-lookup"><span data-stu-id="44232-246">Don't allow your action methods to become cluttered with conditional code like this.</span></span> <span data-ttu-id="44232-247">Вместо этого опроса политики в фильтры, которые могут применяться по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="44232-247">Instead, pull the policies into filters that can be applied on an as-needed basis.</span></span> <span data-ttu-id="44232-248">В этом примере проверки модели, которой должно выполняться каждый раз, когда отправляется команда API, можно заменить следующий атрибут:</span><span class="sxs-lookup"><span data-stu-id="44232-248">In this example, the model validation check, which should occur any time a command is sent to the API, can be replaced by the following attribute:</span></span>

```csharp
public class ValidateModelAttribute : ActionFilterAttribute
{
    public override void OnActionExecuting(ActionExecutingContext context)
    {
        if (!context.ModelState.IsValid)
        {
            context.Result = new BadRequestObjectResult(context.ModelState);
        }
    }
}
```

<span data-ttu-id="44232-249">Аналогичным образом фильтр можно использовать для проверки, если запись существует и возвращать код 404, перед выполнением действия, устраняя необходимость выполнения этих проверок при выполнении действия.</span><span class="sxs-lookup"><span data-stu-id="44232-249">Likewise, a filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action.</span></span> <span data-ttu-id="44232-250">После бы извлечено из общих соглашений и организованных решения для разделения инфраструктуры кода и бизнес-логики в пользовательском Интерфейсе, должен быть чрезвычайно тонкого свои методы действия MVC:</span><span class="sxs-lookup"><span data-stu-id="44232-250">Once you've pulled out common conventions and organized your solution to separate infrastructure code and business logic from your UI, your MVC action methods should be extremely thin:</span></span>

```csharp
// PUT api/authors/2/5
[HttpPut("{id}")]
[ValidateAuthorExists]
public async Task<IActionResult> Put(int id, [FromBody]Author author)
{
    await _authorRepository.UpdateAsync(author);
    return Ok();
}
```

<span data-ttu-id="44232-251">Дополнительные сведения о реализации фильтры и загрузить рабочий образец из статьи MSDN [фильтров ASP.NET MVC Core реальные World](https://msdn.microsoft.com/magazine/mt767699.aspx).</span><span class="sxs-lookup"><span data-stu-id="44232-251">You can read more about implementing filters and download a working sample from the MSDN article, [Real World ASP.NET Core MVC Filters](https://msdn.microsoft.com/magazine/mt767699.aspx).</span></span>

> ### <a name="references--structuring-applications"></a><span data-ttu-id="44232-252">Ссылки — структуризации приложений</span><span class="sxs-lookup"><span data-stu-id="44232-252">References – Structuring Applications</span></span>
> - <span data-ttu-id="44232-253">**Области**</span><span class="sxs-lookup"><span data-stu-id="44232-253">**Areas**</span></span>  
> <span data-ttu-id="44232-254"><https://docs.microsoft.com/aspnet/core/mvc/controllers/areas></span><span class="sxs-lookup"><span data-stu-id="44232-254"><https://docs.microsoft.com/aspnet/core/mvc/controllers/areas></span></span>
> - <span data-ttu-id="44232-255">**MSDN — функция срезов для основных компонентов ASP.NET MVC**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx></span><span class="sxs-lookup"><span data-stu-id="44232-255">**MSDN – Feature Slices for ASP.NET Core MVC**
<https://msdn.microsoft.com/magazine/mt763233.aspx></span></span>
> - <span data-ttu-id="44232-256">**Фильтры**</span><span class="sxs-lookup"><span data-stu-id="44232-256">**Filters**</span></span>  
> <span data-ttu-id="44232-257"><https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span><span class="sxs-lookup"><span data-stu-id="44232-257"><https://docs.microsoft.com/aspnet/core/mvc/controllers/filters></span></span>
> - <span data-ttu-id="44232-258">**MSDN — фильтры MVC ASP.NET Core реального мира**</span><span class="sxs-lookup"><span data-stu-id="44232-258">**MSDN – Real World ASP.NET Core MVC Filters**</span></span>  
> <span data-ttu-id="44232-259"><https://msdn.microsoft.com/magazine/mt767699.aspx></span><span class="sxs-lookup"><span data-stu-id="44232-259"><https://msdn.microsoft.com/magazine/mt767699.aspx></span></span>

## <a name="security"></a><span data-ttu-id="44232-260">Безопасность</span><span class="sxs-lookup"><span data-stu-id="44232-260">Security</span></span>

<span data-ttu-id="44232-261">Обеспечение безопасности веб-приложений — большой раздел, с множеством факторов.</span><span class="sxs-lookup"><span data-stu-id="44232-261">Securing web applications is a large topic, with many considerations.</span></span> <span data-ttu-id="44232-262">На самом базовом уровне безопасности предполагает, что вы знаете, кто из указанного запроса и затем гарантирует, что этот запрос имеет доступ только к ресурсам, которые следует.</span><span class="sxs-lookup"><span data-stu-id="44232-262">At its most basic level, security involves ensuring you know who a given request is coming from, and then ensuring that that request only has access to resources it should.</span></span> <span data-ttu-id="44232-263">Проверка подлинности — это процесс сравнения учетные данные, предоставленные вместе с запросом тем в хранилище доверенных данных, чтобы увидеть, если запрос должны рассматриваться как поступающие от известных сущности.</span><span class="sxs-lookup"><span data-stu-id="44232-263">Authentication is the process of comparing credentials provided with a request to those in a trusted data store, to see if the request should be treated as coming from a known entity.</span></span> <span data-ttu-id="44232-264">Авторизация является процессом, ограничения доступа к определенным ресурсам, на основе удостоверения пользователя.</span><span class="sxs-lookup"><span data-stu-id="44232-264">Authorization is the process of restricting access to certain resources based on user identity.</span></span> <span data-ttu-id="44232-265">Третий угроза безопасности обеспечивает защиту запросы от перехвата сторонними производителями, для которых следует [убедитесь, что SSL используется приложением](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).</span><span class="sxs-lookup"><span data-stu-id="44232-265">A third security concern is protecting requests from eavesdropping by third parties, for which you should at least [ensure that SSL is used by your application](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).</span></span>

### <a name="authentication"></a><span data-ttu-id="44232-266">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="44232-266">Authentication</span></span>

<span data-ttu-id="44232-267">Удостоверение ASP.NET Core является система членства, которые можно использовать для поддержки функциональных возможностей входа для приложения.</span><span class="sxs-lookup"><span data-stu-id="44232-267">ASP.NET Core Identity is a membership system you can use to support login functionality for your application.</span></span> <span data-ttu-id="44232-268">Он имеет поддержку для локальных учетных записей пользователей, а также поддержка поставщика внешнего входа поставщиков, как учетную запись Майкрософт, Twitter, Facebook, Google и многое другое.</span><span class="sxs-lookup"><span data-stu-id="44232-268">It has support for local user accounts as well as external login provider support from providers like Microsoft Account, Twitter, Facebook, Google, and more.</span></span> <span data-ttu-id="44232-269">В дополнение к ASP.NET Core Identity, приложение может использовать проверку подлинности windows или как поставщик удостоверений сторонних [удостоверение сервера](https://github.com/IdentityServer/IdentityServer4).</span><span class="sxs-lookup"><span data-stu-id="44232-269">In addition to ASP.NET Core Identity, your application can use windows authentication, or a third-party identity provider like [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span></span>

<span data-ttu-id="44232-270">Удостоверение ASP.NET Core включается в новые шаблоны проектов, если выбран параметр отдельных учетных записей пользователей.</span><span class="sxs-lookup"><span data-stu-id="44232-270">ASP.NET Core Identity is included in new project templates if the Individual User Accounts option is selected.</span></span> <span data-ttu-id="44232-271">Этот шаблон включает поддержку регистрации, имя входа, внешних имен входа, забытые пароли и дополнительные функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="44232-271">This template includes support for registration, login, external logins, forgotten passwords, and additional functionality.</span></span>

![](./media/image7-3.png)

<span data-ttu-id="44232-272">Рис. 7-3 выберите отдельные учетные записи пользователей идентификацией предварительно настроен.</span><span class="sxs-lookup"><span data-stu-id="44232-272">Figure 7-3 Select Individual User Accounts to have Identity preconfigured.</span></span>

<span data-ttu-id="44232-273">Поддержка удостоверений настраивается при запуске в ConfigureServices и настроить:</span><span class="sxs-lookup"><span data-stu-id="44232-273">Identity support is configured in Startup, both in ConfigureServices and Configure:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
    .AddEntityFrameworkStores<ApplicationDbContext>()
    .AddDefaultTokenProviders();
    services.AddMvc();
}

public void Configure(IApplicationBuilder app)
{
    app.UseStaticFiles();
    app.UseIdentity();
    app.UseMvc(routes =>
    {
        routes.MapRoute(
        name: "default",
        template: "{controller=Home}/{action=Index}/{id?}");
    });
}
```

<span data-ttu-id="44232-274">Очень важно, что UseIdentity отображаются перед UseMvc метод конфигурации.</span><span class="sxs-lookup"><span data-stu-id="44232-274">It's important that UseIdentity appear before UseMvc in the Configure method.</span></span> <span data-ttu-id="44232-275">При настройке удостоверения в ConfigureServices, вы заметите, что вызов AddDefaultTokenProviders.</span><span class="sxs-lookup"><span data-stu-id="44232-275">When configuring Identity in ConfigureServices, you'll notice a call to AddDefaultTokenProviders.</span></span> <span data-ttu-id="44232-276">Это никак не связано с маркерами, которые могут использоваться для защиты веб-соединений, но вместо относится к поставщикам, которые создают запросы, которые могут быть отправлены пользователям с помощью SMS или по электронной почте для них, чтобы подтвердить свою личность.</span><span class="sxs-lookup"><span data-stu-id="44232-276">This has nothing to do with tokens that may be used to secure web communications, but instead refers to providers that create prompts that can be sent to users via SMS or email in order for them to confirm their identity.</span></span>

<span data-ttu-id="44232-277">Дополнительные сведения о [настройки двухфакторной проверки подлинности](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) и [Включение поставщиков внешнего входа](https://docs.microsoft.com/aspnet/core/security/authentication/social/) из официальных документы ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44232-277">You can learn more about [configuring two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) and [enabling external login providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) from the official ASP.NET Core docs.</span></span>

### <a name="authorization"></a><span data-ttu-id="44232-278">Авторизация</span><span class="sxs-lookup"><span data-stu-id="44232-278">Authorization</span></span>

<span data-ttu-id="44232-279">Самая простая форма авторизации включает в себя ограничение доступа для анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="44232-279">The simplest form of authorization involves restricting access to anonymous users.</span></span> <span data-ttu-id="44232-280">Это можно сделать путем применения просто \[авторизовать\] атрибут определенных контроллеров или действий.</span><span class="sxs-lookup"><span data-stu-id="44232-280">This can be achieved by simply applying the \[Authorize\] attribute to certain controllers or actions.</span></span> <span data-ttu-id="44232-281">При использовании ролей атрибут можно дополнительно расширить для ограничения доступа к пользователям, принадлежащим к определенных ролей, как показано:</span><span class="sxs-lookup"><span data-stu-id="44232-281">If roles are being used, the attribute can be further extended to restrict access to users who belong to certain roles, as shown:</span></span>

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

<span data-ttu-id="44232-282">В этом случае пользователи, принадлежащие роли HRManager или процент (или оба) будет иметь доступ к SalaryController.</span><span class="sxs-lookup"><span data-stu-id="44232-282">In this case, users belonging to either the HRManager or Finance roles (or both) would have access to the SalaryController.</span></span> <span data-ttu-id="44232-283">Требуется пользователь принадлежит нескольким ролям (не в одной из нескольких), можно применить атрибут несколько раз, указав необходимые роли каждый раз.</span><span class="sxs-lookup"><span data-stu-id="44232-283">To require that a user belong to multiple roles (not just one of several), you can apply the attribute multiple times, specifying a required role each time.</span></span>

<span data-ttu-id="44232-284">Укажите определенные наборы ролей, как строки во многих различных контроллеров и действий может привести к нежелательным повторения.</span><span class="sxs-lookup"><span data-stu-id="44232-284">Specifying certain sets of roles as strings in many different controllers and actions can lead to undesirable repetition.</span></span> <span data-ttu-id="44232-285">Можно настроить политики авторизации, который инкапсулирует правила авторизации, и затем указать политику вместо отдельных ролей при применении \[авторизовать\] атрибута:</span><span class="sxs-lookup"><span data-stu-id="44232-285">You can configure authorization policies, which encapsulate authorization rules, and then specify the policy instead of individual roles when applying the \[Authorize\] attribute:</span></span>

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

<span data-ttu-id="44232-286">С помощью политик таким образом, можно разделить типы действий будет закрыт с конкретными ролями или правила, которые применяются к нему.</span><span class="sxs-lookup"><span data-stu-id="44232-286">Using policies in this way, you can separate the kinds of actions being restricted from the specific roles or rules that apply to it.</span></span> <span data-ttu-id="44232-287">Позже, при создании новой роли, которая должна иметь доступ к определенным ресурсам, можно просто обновить политику, а не обновлять каждый список ролей на каждый \[авторизовать\] атрибута.</span><span class="sxs-lookup"><span data-stu-id="44232-287">Later, if you create a new role that needs to have access to certain resources, you can just update a policy, rather than updating every list of roles on every \[Authorize\] attribute.</span></span>

#### <a name="claims"></a><span data-ttu-id="44232-288">Утверждения</span><span class="sxs-lookup"><span data-stu-id="44232-288">Claims</span></span>

<span data-ttu-id="44232-289">Утверждения — это пары имя-значение, представляющих свойства, прошедшего проверку подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="44232-289">Claims are name value pairs that represent properties of an authenticated user.</span></span> <span data-ttu-id="44232-290">Например можно хранить как утверждения пользователей сотрудника.</span><span class="sxs-lookup"><span data-stu-id="44232-290">For example, you might store users' employee number as a claim.</span></span> <span data-ttu-id="44232-291">Утверждения могут затем использоваться как часть политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="44232-291">Claims can then be used as part of authorization policies.</span></span> <span data-ttu-id="44232-292">Можно создать политику, называется «EmployeeOnly», требует наличия заявку под названием «Внутри открывающего», как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="44232-292">You could create a policy called "EmployeeOnly" that requires the existence of a claim called "EmployeeNumber", as shown in this example:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc();
    services.AddAuthorization(options =>
    {
        options.AddPolicy("EmployeeOnly", policy => policy.RequireClaim("EmployeeNumber"));
    });
}
```

<span data-ttu-id="44232-293">Затем можно использовать эту политику с \[авторизовать\] атрибут, чтобы защитить любой контроллер или действие, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="44232-293">This policy could then be used with the \[Authorize\] attribute to protect any controller and/or action, as described above.</span></span>

#### <a name="securing-web-apis"></a><span data-ttu-id="44232-294">Обеспечение безопасности веб-API</span><span class="sxs-lookup"><span data-stu-id="44232-294">Securing Web APIs</span></span>

<span data-ttu-id="44232-295">Большинство веб-API должен реализовывать системы проверки подлинности на основе маркеров.</span><span class="sxs-lookup"><span data-stu-id="44232-295">Most web APIs should implement a token-based authentication system.</span></span> <span data-ttu-id="44232-296">Маркер проверки подлинности без сохранения состояния и разработаны для масштабируемости.</span><span class="sxs-lookup"><span data-stu-id="44232-296">Token authentication is stateless and designed to be scalable.</span></span> <span data-ttu-id="44232-297">В системе токены проверки подлинности клиент должен сначала пройти проверку подлинности с поставщиком проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="44232-297">In a token-based authentication system, the client must first authenticate with the authentication provider.</span></span> <span data-ttu-id="44232-298">В случае успеха клиент выдает маркер, который представляет собой криптографически значимых строку символов.</span><span class="sxs-lookup"><span data-stu-id="44232-298">If successful, the client is issued a token, which is simply a cryptographically meaningful string of characters.</span></span> <span data-ttu-id="44232-299">Когда клиенту необходимо отправить запрос к API, он добавляет этот токен как заголовок запроса.</span><span class="sxs-lookup"><span data-stu-id="44232-299">When the client then needs to issue a request to an API, it adds this token as a header on the request.</span></span> <span data-ttu-id="44232-300">Затем сервер проверяет токен, найденный в заголовке запроса до завершения запроса.</span><span class="sxs-lookup"><span data-stu-id="44232-300">The server then validates the token found in the request header before completing the request.</span></span> <span data-ttu-id="44232-301">Рис. 7-4 показан этот процесс.</span><span class="sxs-lookup"><span data-stu-id="44232-301">Figure 7-4 demonstrates this process.</span></span>

![TokenAuth](./media/image7-4.png)

<span data-ttu-id="44232-303">**Рис. 7-4.**</span><span class="sxs-lookup"><span data-stu-id="44232-303">**Figure 7-4.**</span></span> <span data-ttu-id="44232-304">Токены проверки подлинности для веб-API.</span><span class="sxs-lookup"><span data-stu-id="44232-304">Token-based authentication for Web APIs.</span></span>

> ### <a name="references--security"></a><span data-ttu-id="44232-305">Ссылки — безопасности</span><span class="sxs-lookup"><span data-stu-id="44232-305">References – Security</span></span>
> - <span data-ttu-id="44232-306">**Обзор документации о безопасности**</span><span class="sxs-lookup"><span data-stu-id="44232-306">**Security Docs Overview**</span></span>  
> <span data-ttu-id="44232-307">https://docs.microsoft.com/aspnet/core/security/</span><span class="sxs-lookup"><span data-stu-id="44232-307">https://docs.microsoft.com/aspnet/core/security/</span></span>
> - <span data-ttu-id="44232-308">**Применение протокола SSL в приложении ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="44232-308">**Enforcing SSL in an ASP.NET Core App**</span></span>  
> <span data-ttu-id="44232-309"><https://docs.microsoft.com/aspnet/core/security/enforcing-ssl></span><span class="sxs-lookup"><span data-stu-id="44232-309"><https://docs.microsoft.com/aspnet/core/security/enforcing-ssl></span></span>
> - <span data-ttu-id="44232-310">**Общие сведения об Identity**</span><span class="sxs-lookup"><span data-stu-id="44232-310">**Introduction to Identity**</span></span>  
> <span data-ttu-id="44232-311"><https://docs.microsoft.com/aspnet/core/security/authentication/identity></span><span class="sxs-lookup"><span data-stu-id="44232-311"><https://docs.microsoft.com/aspnet/core/security/authentication/identity></span></span>
> - <span data-ttu-id="44232-312">**Общие сведения об авторизации**</span><span class="sxs-lookup"><span data-stu-id="44232-312">**Introduction to Authorization**</span></span>  
> <span data-ttu-id="44232-313"><https://docs.microsoft.com/aspnet/core/security/authorization/introduction></span><span class="sxs-lookup"><span data-stu-id="44232-313"><https://docs.microsoft.com/aspnet/core/security/authorization/introduction></span></span>
> - <span data-ttu-id="44232-314">**Проверка подлинности и авторизация для приложений API в службе приложений Azure**</span><span class="sxs-lookup"><span data-stu-id="44232-314">**Authentication and Authorization for API Apps in Azure App Service**</span></span>  
> <span data-ttu-id="44232-315"><https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication></span><span class="sxs-lookup"><span data-stu-id="44232-315"><https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication></span></span>

## <a name="client-communication"></a><span data-ttu-id="44232-316">Взаимодействие с клиентскими</span><span class="sxs-lookup"><span data-stu-id="44232-316">Client Communication</span></span>

<span data-ttu-id="44232-317">Помимо пересылкой страницы и отвечает на запросы к данным через веб-API, приложения ASP.NET Core могут взаимодействовать напрямую с подключенными клиентами.</span><span class="sxs-lookup"><span data-stu-id="44232-317">In addition to serving pages and responding to requests for data via web APIs, ASP.NET Core apps can communicate directly with connected clients.</span></span> <span data-ttu-id="44232-318">Это исходящей связи можно использовать широкий набор технологий транспорта наиболее распространенные выполняется WebSockets.</span><span class="sxs-lookup"><span data-stu-id="44232-318">This outbound communication can use a variety of transport technologies, the most common being WebSockets.</span></span> <span data-ttu-id="44232-319">SignalR ASP.NET Core — это библиотека, облегчающий, какие функции обмена данными в режиме реального времени сервер клиент в приложения.</span><span class="sxs-lookup"><span data-stu-id="44232-319">ASP.NET Core SignalR is a library that makes it simple to kind of real-time server-to-client communication functionality to your applications.</span></span> <span data-ttu-id="44232-320">SignalR поддерживает широкий набор технологий транспорта, включая WebSockets и выделяет дальней многие детали реализации разработчика.</span><span class="sxs-lookup"><span data-stu-id="44232-320">SignalR supports a variety of transport technologies, including WebSockets, and abstracts away many of the implementation details from the developer.</span></span>

<span data-ttu-id="44232-321">ASP.NET Core SignalR в настоящее время находится в стадии разработки и будет доступна в следующем выпуске ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44232-321">ASP.NET Core SignalR is currently under development, and will be available in the next release of ASP.NET Core.</span></span> <span data-ttu-id="44232-322">Однако другие [откройте библиотеки исходного WebSockets](https://github.com/radu-matei/websocket-manager) в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="44232-322">However, other [open source WebSockets libraries](https://github.com/radu-matei/websocket-manager) are currently available.</span></span>

<span data-ttu-id="44232-323">Соединения с клиентом в режиме реального времени, ли использование WebSockets напрямую и другие методы полезны в различных сценариях приложений.</span><span class="sxs-lookup"><span data-stu-id="44232-323">Real-time client communication, whether using WebSockets directly or other techniques, are useful in a variety of application scenarios.</span></span> <span data-ttu-id="44232-324">Ниже приведены некоторые примеры таких ситуаций.</span><span class="sxs-lookup"><span data-stu-id="44232-324">Some examples include:</span></span>

-   <span data-ttu-id="44232-325">Приложения динамической комнаты чата</span><span class="sxs-lookup"><span data-stu-id="44232-325">Live chat room applications</span></span>

-   <span data-ttu-id="44232-326">Мониторинг приложений</span><span class="sxs-lookup"><span data-stu-id="44232-326">Monitoring applications</span></span>

-   <span data-ttu-id="44232-327">Обновления хода выполнения задания</span><span class="sxs-lookup"><span data-stu-id="44232-327">Job progress updates</span></span>

-   <span data-ttu-id="44232-328">Уведомления</span><span class="sxs-lookup"><span data-stu-id="44232-328">Notifications</span></span>

-   <span data-ttu-id="44232-329">Интерактивные формы приложения</span><span class="sxs-lookup"><span data-stu-id="44232-329">Interactive forms applications</span></span>

<span data-ttu-id="44232-330">При создании связи с клиентами в приложения, обычно существуют два компонента:</span><span class="sxs-lookup"><span data-stu-id="44232-330">When building client communication into your applications, there are typically two components:</span></span>

-   <span data-ttu-id="44232-331">Диспетчер соединений серверные (концентратора SignalR, WebSocketManager WebSocketHandler)</span><span class="sxs-lookup"><span data-stu-id="44232-331">Server-side connection manager (SignalR Hub, WebSocketManager WebSocketHandler)</span></span>

-   <span data-ttu-id="44232-332">Клиентская библиотека</span><span class="sxs-lookup"><span data-stu-id="44232-332">Client-side library</span></span>

<span data-ttu-id="44232-333">Клиенты не ограничиваются браузеров — мобильных приложений, консольные приложения и других встроенных приложений может также обмениваться данными с использованием SignalR/WebSockets.</span><span class="sxs-lookup"><span data-stu-id="44232-333">Clients are not limited to browsers – mobile apps, console apps, and other native apps can also communicate using SignalR/WebSockets.</span></span> <span data-ttu-id="44232-334">Следующая простая программа отображает все содержимое, отправляемое приложения разговора в консоль как часть примера приложения WebSocketManager:</span><span class="sxs-lookup"><span data-stu-id="44232-334">The following simple program echoes all content sent to a chat application to the console, as part of a WebSocketManager sample application:</span></span>

```csharp
public class Program
{
    private static Connection _connection;
    public static void Main(string[] args)
    {
        StartConnectionAsync();
        _connection.On("receiveMessage", (arguments) =>;
        {
            Console.WriteLine(\$"{arguments\[0\]} said: {arguments\[1\]}");
        });
        Console.ReadLine();
        StopConnectionAsync();
    }
    
    public static async Task StartConnectionAsync()
    {
        _connection = new Connection();
        await _connection.StartConnectionAsync("ws://localhost:65110/chat");
    }
    
    public static async Task StopConnectionAsync()
    {
        await _connection.StopConnectionAsync();
    }
```

<span data-ttu-id="44232-335">Рассмотрите возможность столкнуться способами, в которых приложения взаимодействуют непосредственно с клиентскими приложениями и рассмотрите возможность ли обмен данными в реальном времени позволяет улучшить пользователя приложения.</span><span class="sxs-lookup"><span data-stu-id="44232-335">Consider ways in which your applications communicate directly with client applications, and consider whether real-time communication would improve your app's user experience.</span></span>

> ### <a name="references--client-communication"></a><span data-ttu-id="44232-336">Ссылки — обмена данными с клиентами</span><span class="sxs-lookup"><span data-stu-id="44232-336">References – Client Communication</span></span>
> - <span data-ttu-id="44232-337">**ASP.NET Core SignalR**</span><span class="sxs-lookup"><span data-stu-id="44232-337">**ASP.NET Core SignalR**</span></span>  
> <span data-ttu-id="44232-338"><https://github.com/aspnet/SignalR></span><span class="sxs-lookup"><span data-stu-id="44232-338"><https://github.com/aspnet/SignalR></span></span>
> - <span data-ttu-id="44232-339">**Диспетчер WebSocket**</span><span class="sxs-lookup"><span data-stu-id="44232-339">**WebSocket Manager**</span></span>  
> <span data-ttu-id="44232-340">https://github.com/radu-matei/websocket-manager</span><span class="sxs-lookup"><span data-stu-id="44232-340">https://github.com/radu-matei/websocket-manager</span></span>

## <a name="domain-driven-design--should-you-apply-it"></a><span data-ttu-id="44232-341">Домен Driven Design – следует применить ее?</span><span class="sxs-lookup"><span data-stu-id="44232-341">Domain-Driven Design – Should You Apply It?</span></span>

<span data-ttu-id="44232-342">Разработки на основе домена (DDD) является гибкий подход к разработке программного обеспечения, особое внимание уделяется сосредоточиться на *бизнес-среде*.</span><span class="sxs-lookup"><span data-stu-id="44232-342">Domain-Driven Design (DDD) is an agile approach to building software that emphasizes focusing on the *business domain*.</span></span> <span data-ttu-id="44232-343">Он помещает серьезный акцент на связь и взаимодействие с expert(s) домена предприятия, можно связать со разработчики, как работает система реального мира.</span><span class="sxs-lookup"><span data-stu-id="44232-343">It places a heavy emphasis on communication and interaction with business domain expert(s) who can relate to the developers how the real-world system works.</span></span> <span data-ttu-id="44232-344">Например при создании системе обработки биржевых руки, специалист домена может быть опытным биржевых брокера.</span><span class="sxs-lookup"><span data-stu-id="44232-344">For example, if you're building a system that handles stock trades, your domain expert might be an experienced stock broker.</span></span> <span data-ttu-id="44232-345">DDD предназначен для больших и сложных бизнес-задач и часто не подходит для приложений, меньшие, более простые, как инвестиции в понимании и моделирования домена не стоит.</span><span class="sxs-lookup"><span data-stu-id="44232-345">DDD is designed to address large, complex business problems, and is often not appropriate for smaller, simpler applications, as the investment in understanding and modeling the domain is not worth it.</span></span>

<span data-ttu-id="44232-346">При разработке программного обеспечения подходе ддд, команда (включая нетехнических заинтересованных лиц и участников) следует разработать *единый язык* для проблемной области.</span><span class="sxs-lookup"><span data-stu-id="44232-346">When building software following a DDD approach, your team (including non-technical stakeholders and contributors) should develop a *ubiquitous language* for the problem space.</span></span> <span data-ttu-id="44232-347">То есть тот же термин следует использовать для реальных понятие моделируемого, эквивалент программного обеспечения и все структуры, которые могут существовать для сохранения понятие (например, таблицы базы данных).</span><span class="sxs-lookup"><span data-stu-id="44232-347">That is, the same terminology should be used for the real-world concept being modeled, the software equivalent, and any structures that might exist to persist the concept (for example, database tables).</span></span> <span data-ttu-id="44232-348">Таким образом, основные понятия, описанные в единый язык должен образуют основу для вашего *модель домена*.</span><span class="sxs-lookup"><span data-stu-id="44232-348">Thus, the concepts described in the ubiquitous language should form the basis for your *domain model*.</span></span>

<span data-ttu-id="44232-349">Модель домена состоит из объектов, которые взаимодействуют друг с другом для представления поведение системы.</span><span class="sxs-lookup"><span data-stu-id="44232-349">Your domain model is comprised of objects that interact with one another to represent the behavior of the system.</span></span> <span data-ttu-id="44232-350">Эти объекты могут делятся на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="44232-350">These objects may fall into the following categories:</span></span>

-   <span data-ttu-id="44232-351">[Сущности](http://deviq.com/entity/), которые представляют объекты с потоком удостоверения.</span><span class="sxs-lookup"><span data-stu-id="44232-351">[Entities](http://deviq.com/entity/), which represent objects with a thread of identity.</span></span> <span data-ttu-id="44232-352">Обычно сущности сохраняются в сохраняемости с помощью ключа, с помощью которого их можно извлечь.</span><span class="sxs-lookup"><span data-stu-id="44232-352">Entities are typically stored in persistence with a key by which they can later be retrieved.</span></span>

-   <span data-ttu-id="44232-353">[Статистические функции](http://deviq.com/aggregate-pattern/), которые представляют группы объектов, которые следует сохранять как единое целое.</span><span class="sxs-lookup"><span data-stu-id="44232-353">[Aggregates](http://deviq.com/aggregate-pattern/), which represent groups of objects that should be persisted as a unit.</span></span>

-   <span data-ttu-id="44232-354">[Значение объектов](http://deviq.com/value-object/), которые представляют основные понятия, которые можно сравнивать на основе суммы значений их свойств.</span><span class="sxs-lookup"><span data-stu-id="44232-354">[Value objects](http://deviq.com/value-object/), which represent concepts that can be compared on the basis of the sum of their property values.</span></span> <span data-ttu-id="44232-355">Например, DateRange, состоящая из даты начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="44232-355">For example, DateRange consisting of a start and end date.</span></span>

-   <span data-ttu-id="44232-356">[События домена](https://martinfowler.com/eaaDev/DomainEvent.html), которые представляют происходит в системе вещей, которые представляют интерес в другие части системы.</span><span class="sxs-lookup"><span data-stu-id="44232-356">[Domain events](https://martinfowler.com/eaaDev/DomainEvent.html), which represent things happening within the system that are of interest to other parts of the system.</span></span>

<span data-ttu-id="44232-357">Обратите внимание, что модель домена DDD следует инкапсулировать сложное поведение в модели.</span><span class="sxs-lookup"><span data-stu-id="44232-357">Note that a DDD domain model should encapsulate complex behavior within the model.</span></span> <span data-ttu-id="44232-358">Сущности, в частности, не следует просто коллекции свойств.</span><span class="sxs-lookup"><span data-stu-id="44232-358">Entities, in particular, should not merely be collections of properties.</span></span> <span data-ttu-id="44232-359">Модель домена не имеет поведения, а просто представляет состояние системы, он считается [anemic модели](http://deviq.com/anemic-model/), что нежелательно в ддд.</span><span class="sxs-lookup"><span data-stu-id="44232-359">When the domain model lacks behavior and merely represents the state of the system, it is said to be an [anemic model](http://deviq.com/anemic-model/), which is undesirable in DDD.</span></span>

<span data-ttu-id="44232-360">Помимо этих типов модели DDD обычно применяет разнообразные шаблоны:</span><span class="sxs-lookup"><span data-stu-id="44232-360">In addition to these model types, DDD typically employs a variety of patterns:</span></span>

-   <span data-ttu-id="44232-361">[Репозиторий](http://deviq.com/repository-pattern/), абстракцию сохраняемости сведения.</span><span class="sxs-lookup"><span data-stu-id="44232-361">[Repository](http://deviq.com/repository-pattern/), for abstracting persistence details.</span></span>

-   <span data-ttu-id="44232-362">[Фабрика](https://en.wikipedia.org/wiki/Factory_method_pattern), для инкапсуляции создания сложных объектов.</span><span class="sxs-lookup"><span data-stu-id="44232-362">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), for encapsulating complex object creation.</span></span>

-   <span data-ttu-id="44232-363">События домена для разделения зависимых поведение срабатывания поведение.</span><span class="sxs-lookup"><span data-stu-id="44232-363">Domain events, for decoupling dependent behavior from triggering behavior.</span></span>

-   <span data-ttu-id="44232-364">[Службы](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), для инкапсуляции сложной поведение и/или сведения о реализации инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="44232-364">[Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), for encapsulating complex behavior and/or infrastructure implementation details.</span></span>

-   <span data-ttu-id="44232-365">[Команда](https://en.wikipedia.org/wiki/Command_pattern), для разделения выполнения команд и выполнении саму команду.</span><span class="sxs-lookup"><span data-stu-id="44232-365">[Command](https://en.wikipedia.org/wiki/Command_pattern), for decoupling issuing commands and executing the command itself.</span></span>

-   <span data-ttu-id="44232-366">[Спецификация](http://deviq.com/specification-pattern/), для инкапсуляции сведения о запросе.</span><span class="sxs-lookup"><span data-stu-id="44232-366">[Specification](http://deviq.com/specification-pattern/), for encapsulating query details.</span></span>

<span data-ttu-id="44232-367">DDD также даются рекомендации по использованию чистой архитектуры, описанные ранее, что обеспечивает слабую связь, инкапсуляцию и кода, которые легко могут быть проверены с помощью модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="44232-367">DDD also recommends the use of the Clean Architecture discussed previously, allowing for loose coupling, encapsulation, and code that can easily be verified using unit tests.</span></span>

### <a name="when-should-you-apply-ddd"></a><span data-ttu-id="44232-368">Когда вы применяете DDD</span><span class="sxs-lookup"><span data-stu-id="44232-368">When Should You Apply DDD</span></span>

<span data-ttu-id="44232-369">DDD хорошо подходит для больших приложений с сложности значительные бизнеса (не только о технических).</span><span class="sxs-lookup"><span data-stu-id="44232-369">DDD is well-suited to large applications with significant business (not just technical) complexity.</span></span> <span data-ttu-id="44232-370">Приложение должно требует знания специалистами в предметной области.</span><span class="sxs-lookup"><span data-stu-id="44232-370">The application should require the knowledge of domain experts.</span></span> <span data-ttu-id="44232-371">Должна существовать значительные возможности в домене самой модели, представляющий бизнес-правил и взаимодействия за пределами просто хранения и получения текущего состояния различных записей из хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="44232-371">There should be significant behavior in the domain model itself, representing business rules and interactions beyond simply storing and retrieving the current state of various records from data stores.</span></span>

### <a name="when-shouldnt-you-apply-ddd"></a><span data-ttu-id="44232-372">Когда не следует применять DDD</span><span class="sxs-lookup"><span data-stu-id="44232-372">When Shouldn't You Apply DDD</span></span>

<span data-ttu-id="44232-373">DDD подразумевает вложений для моделирования, архитектура и взаимодействие, не следует провести для небольших приложений или приложений, которые по сути являются просто CRUD (Создание и чтение, обновление и удаление).</span><span class="sxs-lookup"><span data-stu-id="44232-373">DDD involves investments in modeling, architecture, and communication that may not be warranted for smaller applications or applications that are essentially just CRUD (create/read/update/delete).</span></span> <span data-ttu-id="44232-374">Если вы решили подход приложения после ддд, но обнаруживается модель anemic с нет поведения домена, может потребоваться пересмотреть подхода.</span><span class="sxs-lookup"><span data-stu-id="44232-374">If you choose to approach your application following DDD, but find that your domain has an anemic model with no behavior, you may need to rethink your approach.</span></span> <span data-ttu-id="44232-375">Приложение не должно DDD либо обратитесь за помощью, рефакторинг для инкапсуляции бизнес-логики в модель домена, а не в вашей базе данных или в пользовательском интерфейсе приложения.</span><span class="sxs-lookup"><span data-stu-id="44232-375">Either your application may not need DDD, or you may need assistance refactoring your application to encapsulate business logic in the domain model, rather than in your database or user interface.</span></span>

<span data-ttu-id="44232-376">Гибридный подход следует использовать DDD только для области транзакций или более сложные приложения, но не для простой CRUD или частей приложения только для чтения.</span><span class="sxs-lookup"><span data-stu-id="44232-376">A hybrid approach would be to only use DDD for the transactional or more complex areas of the application, but not for simpler CRUD or read-only portions of the application.</span></span> <span data-ttu-id="44232-377">Для экземпляра не имеют ограничения статистической обработки, если выполняется запрос данных для отображения отчета или чтобы визуализировать данные для панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="44232-377">For instance, you needn't have the constraints of an Aggregate if you're querying data to display a report or to visualize data for a dashboard.</span></span> <span data-ttu-id="44232-378">Это вполне приемлемо, чтобы отдельные, более простые чтения модели для таких требований.</span><span class="sxs-lookup"><span data-stu-id="44232-378">It's perfectly acceptable to have a separate, simpler read model for such requirements.</span></span>

> ### <a name="references--domain-driven-design"></a><span data-ttu-id="44232-379">Ссылки — разработки на основе домена</span><span class="sxs-lookup"><span data-stu-id="44232-379">References – Domain-Driven Design</span></span>
> - <span data-ttu-id="44232-380">**DDD на английском (StackOverflow ответов)**</span><span class="sxs-lookup"><span data-stu-id="44232-380">**DDD in Plain English (StackOverflow Answer)**</span></span>  
> <span data-ttu-id="44232-381"><https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488></span><span class="sxs-lookup"><span data-stu-id="44232-381"><https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488></span></span>

## <a name="deployment"></a><span data-ttu-id="44232-382">Развертывание</span><span class="sxs-lookup"><span data-stu-id="44232-382">Deployment</span></span>

<span data-ttu-id="44232-383">Существуют несколько шагов, участвующих в процессе развертывания приложения ASP.NET Core, независимо от того, где будет размещен.</span><span class="sxs-lookup"><span data-stu-id="44232-383">There are a few steps involved in the process of deploying your ASP.NET Core application, regardless of where it will be hosted.</span></span> <span data-ttu-id="44232-384">Первым шагом является публикация приложения, это можно сделать с помощью dotnet опубликовать команду CLI.</span><span class="sxs-lookup"><span data-stu-id="44232-384">The first step is to publish the application, which can be done using the dotnet publish CLI command.</span></span> <span data-ttu-id="44232-385">Это будет выполняться компиляция приложения и поместить все файлы, необходимые для запуска приложения в указанной папки.</span><span class="sxs-lookup"><span data-stu-id="44232-385">This will compile the application and place all of the files needed to run the application into a designated folder.</span></span> <span data-ttu-id="44232-386">При развертывании из Visual Studio, этот шаг выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="44232-386">When you deploy from Visual Studio, this step is performed for you automatically.</span></span> <span data-ttu-id="44232-387">Папки публикации файлы .exe и .dll для приложения и его зависимостей.</span><span class="sxs-lookup"><span data-stu-id="44232-387">The publish folder contains .exe and .dll files for the application and its dependencies.</span></span> <span data-ttu-id="44232-388">Автономные приложения также будет содержать версию среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="44232-388">A self-contained application will also include a version of the .NET runtime.</span></span> <span data-ttu-id="44232-389">Файлы конфигурации, средства статического клиента и представления MVC также входят приложения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44232-389">ASP.NET Core applications will also include configuration files, static client assets, and MVC views.</span></span>

<span data-ttu-id="44232-390">Приложения ASP.NET Core являются консольными приложениями, которые должны быть запущены при загрузке сервера и перезапускается, если приложения (или сервера) аварийно завершает работу.</span><span class="sxs-lookup"><span data-stu-id="44232-390">ASP.NET Core applications are console applications that must be started when the server boots and restarted if the application (or server) crashes.</span></span> <span data-ttu-id="44232-391">Диспетчер процессов можно использовать для автоматизации этого процесса.</span><span class="sxs-lookup"><span data-stu-id="44232-391">A process manager can be used to automate this process.</span></span> <span data-ttu-id="44232-392">Наиболее распространенные менеджеров процесса ASP.NET Core являются Nginx и Apache на IIS и Linux или службы Windows в Windows.</span><span class="sxs-lookup"><span data-stu-id="44232-392">The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.</span></span>

<span data-ttu-id="44232-393">Кроме диспетчер процессов размещенных на веб-сервере Kestrel приложений ASP.NET Core необходимо использовать обратного прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="44232-393">In addition to a process manager, ASP.NET Core applications hosted in the Kestrel web server must use a reverse proxy server.</span></span> <span data-ttu-id="44232-394">Обратный прокси-сервер получает запросы HTTP из Интернета и пересылает их Kestrel после некоторой предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="44232-394">A reverse proxy server receives HTTP requests from the internet and forwards them to Kestrel after some preliminary handling.</span></span> <span data-ttu-id="44232-395">Обратного прокси-серверов Укажите уровень безопасности для приложения и необходимые для развертываний edge (открытый для трафика из Интернета).</span><span class="sxs-lookup"><span data-stu-id="44232-395">Reverse proxy servers provide a layer of security for the application, and are required for edge deployments (exposed to traffic from the Internet).</span></span> <span data-ttu-id="44232-396">Kestrel является относительно новым и еще не обеспечивают защиту от определенных атак.</span><span class="sxs-lookup"><span data-stu-id="44232-396">Kestrel is relatively new and does not yet offer defenses against certain attacks.</span></span> <span data-ttu-id="44232-397">Kestrel также не поддерживает размещение нескольких приложений на один и тот же порт, поэтому такие методы, как заголовки узлов не может использоваться с ним для параллельного размещения нескольких приложений на тот же порт и IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="44232-397">Kestrel also doesn't support hosting multiple applications on the same port, so techniques like host headers cannot be used with it to enable hosting multiple applications on the same port and IP address.</span></span>

![Kestrel для Интернета](./media/image7-5.png)

<span data-ttu-id="44232-399">Рис ASP.NET, размещенных в Kestrel за обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="44232-399">Figure 7-5 ASP.NET hosted in Kestrel behind a reverse proxy server</span></span>

<span data-ttu-id="44232-400">Другой сценарий, в котором обратного прокси-сервера может оказаться полезным является защита нескольких приложений с помощью SSL или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="44232-400">Another scenario in which a reverse proxy can be helpful is to secure multiple applications using SSL/HTTPS.</span></span> <span data-ttu-id="44232-401">В этом случае только обратного прокси-сервера необходимо иметь SSL настроен.</span><span class="sxs-lookup"><span data-stu-id="44232-401">In this case, only the reverse proxy would need to have SSL configured.</span></span> <span data-ttu-id="44232-402">Обмен данными между обратного прокси-сервера и Kestrel может выполняться по протоколу HTTP, как показано на рисунке 7-6.</span><span class="sxs-lookup"><span data-stu-id="44232-402">Communication between the reverse proxy server and Kestrel could take place over HTTP, as shown in Figure 7-6.</span></span>

![](./media/image7-6.png)

<span data-ttu-id="44232-403">Рис ASP.NET, размещенных за защитой HTTPS обратного прокси-сервер с</span><span class="sxs-lookup"><span data-stu-id="44232-403">Figure 7-6 ASP.NET hosted behind an HTTPS-secured reverse proxy server</span></span>

<span data-ttu-id="44232-404">Для размещения приложения ASP.NET Core в контейнере Docker, который затем может быть размещена локально или развертывания в Azure для размещения облачной является более популярным подходом.</span><span class="sxs-lookup"><span data-stu-id="44232-404">An increasingly popular approach is to host your ASP.NET Core application in a Docker container, which then can be hosted locally or deployed to Azure for cloud-based hosting.</span></span> <span data-ttu-id="44232-405">Контейнер Docker могут содержать код приложения, запущенного на Kestrel и будет разворачиваться за обратного прокси-сервера, как показано выше.</span><span class="sxs-lookup"><span data-stu-id="44232-405">The Docker container could contain your application code, running on Kestrel, and would be deployed behind a reverse proxy server, as shown above.</span></span>

<span data-ttu-id="44232-406">Если вы используете приложение в Azure, можно использовать как выделенное виртуальное устройство шлюза приложения Microsoft Azure для предоставления нескольких служб.</span><span class="sxs-lookup"><span data-stu-id="44232-406">If you're hosting your application on Azure, you can use Microsoft Azure Application Gateway as a dedicated virtual appliance to provide several services.</span></span> <span data-ttu-id="44232-407">Помимо выступает в качестве обратного прокси-сервера для отдельных приложений, шлюз приложений также предлагает следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="44232-407">In addition to acting as a reverse proxy for individual applications, Application Gateway can also offer the following features:</span></span>

-   <span data-ttu-id="44232-408">Балансировки нагрузки HTTP</span><span class="sxs-lookup"><span data-stu-id="44232-408">HTTP load balancing</span></span>

-   <span data-ttu-id="44232-409">Разгрузка SSL (SSL только для Интернета)</span><span class="sxs-lookup"><span data-stu-id="44232-409">SSL offload (SSL only to Internet)</span></span>

-   <span data-ttu-id="44232-410">Сквозная SSL</span><span class="sxs-lookup"><span data-stu-id="44232-410">End to End SSL</span></span>

-   <span data-ttu-id="44232-411">Маршрутизация несколькими сайтами (консолидировать до 20 узлов на один шлюз приложения)</span><span class="sxs-lookup"><span data-stu-id="44232-411">Multi-site routing (consolidate up to 20 sites on a single Application Gateway)</span></span>

-   <span data-ttu-id="44232-412">Брандмауэр веб-приложения</span><span class="sxs-lookup"><span data-stu-id="44232-412">Web application firewall</span></span>

-   <span data-ttu-id="44232-413">Поддержка WebSocket</span><span class="sxs-lookup"><span data-stu-id="44232-413">Websocket support</span></span>

-   <span data-ttu-id="44232-414">Дополнительной диагностики</span><span class="sxs-lookup"><span data-stu-id="44232-414">Advanced diagnostics</span></span>

<span data-ttu-id="44232-415">*Дополнительные сведения о параметрах развертывания Azure в главе 10.*</span><span class="sxs-lookup"><span data-stu-id="44232-415">*Learn more about Azure deployment options in Chapter 10.*</span></span>

> ### <a name="references--deployment"></a><span data-ttu-id="44232-416">Ссылки — развертывания</span><span class="sxs-lookup"><span data-stu-id="44232-416">References – Deployment</span></span>
> - <span data-ttu-id="44232-417">**Размещение и общие сведения о развертывании**</span><span class="sxs-lookup"><span data-stu-id="44232-417">**Hosting and Deployment Overview**</span></span>  
> <span data-ttu-id="44232-418"><https://docs.microsoft.com/aspnet/core/publishing/></span><span class="sxs-lookup"><span data-stu-id="44232-418"><https://docs.microsoft.com/aspnet/core/publishing/></span></span>
> - <span data-ttu-id="44232-419">Когда следует использовать Kestrel с обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="44232-419">**When to use Kestrel with a reverse proxy**</span></span>  
> <span data-ttu-id="44232-420"><https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy></span><span class="sxs-lookup"><span data-stu-id="44232-420"><https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy></span></span>
> - <span data-ttu-id="44232-421">**Узел приложения ASP.NET Core в Docker**</span><span class="sxs-lookup"><span data-stu-id="44232-421">**Host ASP.NET Core apps in Docker**</span></span>  
> <span data-ttu-id="44232-422"><https://docs.microsoft.com/aspnet/core/publishing/docker></span><span class="sxs-lookup"><span data-stu-id="44232-422"><https://docs.microsoft.com/aspnet/core/publishing/docker></span></span>
> - <span data-ttu-id="44232-423">**Знакомство с приложением шлюза приложения Azure**</span><span class="sxs-lookup"><span data-stu-id="44232-423">**Introducing Azure Application Gateway**</span></span>  
> <span data-ttu-id="44232-424"><https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction></span><span class="sxs-lookup"><span data-stu-id="44232-424"><https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="44232-425">[Предыдущие] (Общие клиент стороны web-technologies.md) [Далее] (work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="44232-425">[Previous] (common-client-side-web-technologies.md) [Next] (work-with-data-in-asp-net-core-apps.md)</span></span>
