---
title: Разработка приложений MVC ASP.NET Core
description: Разработка современных веб-приложений с помощью ASP.NET Core и Azure | Разработка приложений MVC ASP.NET Core
author: ardalis
ms.author: wiwagn
ms.date: 10/07/2017
ms.openlocfilehash: a90f88e117965aec1550a45f114cabfda5204468
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106597"
---
# <a name="develop-aspnet-core-mvc-apps"></a><span data-ttu-id="7daec-103">Разработка приложений MVC ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7daec-103">Develop ASP.NET Core MVC Apps</span></span>

> <span data-ttu-id="7daec-104">"Неважно, если что-то не получается вначале.</span><span class="sxs-lookup"><span data-stu-id="7daec-104">"It's not important to get it right the first time.</span></span> <span data-ttu-id="7daec-105">Главное, чтобы это получилось в конце".</span><span class="sxs-lookup"><span data-stu-id="7daec-105">It's vitally important to get it right the last time."</span></span>  
> <span data-ttu-id="7daec-106">_— Эндрю Хант (Andrew Hunt) и Дэвид Томас (David Thomas)_</span><span class="sxs-lookup"><span data-stu-id="7daec-106">_- Andrew Hunt and David Thomas_</span></span>

## <a name="summary"></a><span data-ttu-id="7daec-107">Сводка</span><span class="sxs-lookup"><span data-stu-id="7daec-107">Summary</span></span>

<span data-ttu-id="7daec-108">ASP.NET Core является кроссплатформенной средой с открытым исходным кодом для создания современных приложений, оптимизированных для работы в облаке.</span><span class="sxs-lookup"><span data-stu-id="7daec-108">ASP.NET Core is a cross-platform, open-source framework for building modern cloud-optimized web applications.</span></span> <span data-ttu-id="7daec-109">Приложения ASP.NET Core отличаются простотой и модульностью, а также реализуют встроенную поддержку внедрения зависимостей, что позволяет расширить возможности тестирования и сопровождения.</span><span class="sxs-lookup"><span data-stu-id="7daec-109">ASP.NET Core apps are lightweight and modular, with built-in support for dependency injection, enabling in greater testability and maintainability.</span></span> <span data-ttu-id="7daec-110">В сочетании с моделью MVC, которая поддерживает создание современных веб-API в дополнение к приложениям на основе представлений, ASP.NET Core представляет собой эффективную платформу для разработки веб-приложений корпоративного уровня.</span><span class="sxs-lookup"><span data-stu-id="7daec-110">Combined with MVC, which supports building modern web APIs in addition to view-based apps, ASP.NET Core is a powerful framework with which to build enterprise web applications.</span></span>

## <a name="mapping-requests-to-responses"></a><span data-ttu-id="7daec-111">Сопоставление запросов с ответами</span><span class="sxs-lookup"><span data-stu-id="7daec-111">Mapping Requests to Responses</span></span>

<span data-ttu-id="7daec-112">Суть приложений ASP.NET Core заключается в сопоставлении входящих запросов с исходящими ответами.</span><span class="sxs-lookup"><span data-stu-id="7daec-112">At its heart, ASP.NET Core apps map incoming requests to outgoing responses.</span></span> <span data-ttu-id="7daec-113">На низком уровне это реализуется за счет ПО промежуточного слоя, и простые приложения и микрослужбы ASP.NET Core могут полностью состоять из пользовательского ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7daec-113">At a low level, this is done with middleware, and simple ASP.NET Core apps and microservices may be comprised solely of custom middleware.</span></span> <span data-ttu-id="7daec-114">При использовании модели MVC ASP.NET Core вы можете работать на более высоком уровне на основе *маршрутов*, *контроллеров* и *действий*.</span><span class="sxs-lookup"><span data-stu-id="7daec-114">When using ASP.NET Core MVC, you can work at a somewhat higher level, thinking in terms of *routes*, *controllers*, and *actions*.</span></span> <span data-ttu-id="7daec-115">Каждый входящий запрос сравнивается с таблицей маршрутизации приложения. При обнаружении подходящего маршрута для обработки запроса вызывается связанный метод действия, который принадлежит контроллеру.</span><span class="sxs-lookup"><span data-stu-id="7daec-115">Each incoming request is compared with the application's routing table, and if a matching route is found, the associated action method (belonging to a controller) is called to handle the request.</span></span> <span data-ttu-id="7daec-116">Если подходящий маршрут не обнаружен, вызывается обработчик ошибок (в этом случае он возвращает результат NotFound).</span><span class="sxs-lookup"><span data-stu-id="7daec-116">If no matching route is found, an error handler (in this case, returning a NotFound result) is called.</span></span>

<span data-ttu-id="7daec-117">Приложения MVC ASP.NET Core могут использовать обычные маршруты, маршруты с атрибутами или оба вида маршрутов.</span><span class="sxs-lookup"><span data-stu-id="7daec-117">ASP.NET Core MVC apps can use conventional routes, attribute routes, or both.</span></span> <span data-ttu-id="7daec-118">Обычные маршруты определяются в коде путем указания *соглашений* о маршрутизации с использованием показанного в следующем примере синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="7daec-118">Conventional routes are defined in code, specifying routing *conventions* using syntax like in the example below:</span></span>

```csharp
app.UseMvc(routes =>;
{
    routes.MapRoute("default","{controller=Home}/{action=Index}/{id?}");
});
```

<span data-ttu-id="7daec-119">В этом примере в таблицу маршрутизации добавлен маршрут "default".</span><span class="sxs-lookup"><span data-stu-id="7daec-119">In this example, a route named "default" has been added to the routing table.</span></span> <span data-ttu-id="7daec-120">Он определяет шаблон маршрута с заполнителями *controller*, *action* и *id*. Для заполнителей контроллера и действия задаются значения по умолчанию ("Home" и "Index" соответственно). Заполнитель идентификатора является необязательным (для этого к нему применяется знак "?").</span><span class="sxs-lookup"><span data-stu-id="7daec-120">It defines a route template with placeholders for *controller*, *action*, and *id*. The controller and action placeholders have default specified ("Home" and "Index", respectively), and the id placeholder is optional (by virtue of a "?" applied to it).</span></span> <span data-ttu-id="7daec-121">В определенных здесь соглашениях указывается, что первая часть запроса должна соответствовать имени контроллера, вторая часть — действию, а третья (если требуется) представляет параметр идентификатора.</span><span class="sxs-lookup"><span data-stu-id="7daec-121">The convention defined here states that the first part of a request should correspond to the name of the controller, the second part to the action, and then if necessary a third part will represent an id parameter.</span></span> <span data-ttu-id="7daec-122">Обычные маршруты, как правило, определяются в одном месте приложения, например в методе Configure класса Startup.</span><span class="sxs-lookup"><span data-stu-id="7daec-122">Conventional routes are typically defined in one place for the application, such as in the Configure method in the Startup class.</span></span>

<span data-ttu-id="7daec-123">Маршруты с атрибутами применяются напрямую к контроллерам и действиям, а не задаются глобально.</span><span class="sxs-lookup"><span data-stu-id="7daec-123">Attribute routes are applied to controllers and actions directly, rather than specified globally.</span></span> <span data-ttu-id="7daec-124">Это делает их более доступными для обнаружения в рамках конкретного метода, однако при этом сведения о маршрутизации могут храниться в разных местах в приложении.</span><span class="sxs-lookup"><span data-stu-id="7daec-124">This has the advantage of making them much more discoverable when you're looking at a particular method, but does mean that routing information is not kept in one place in the application.</span></span> <span data-ttu-id="7daec-125">С помощью маршрутов с атрибутами можно с легкостью задавать несколько маршрутов для конкретного действия, а также комбинировать маршруты между контроллерами и действиями.</span><span class="sxs-lookup"><span data-stu-id="7daec-125">With attribute routes, you can easily specify multiple routes for a given action, as well as combine routes between controllers and actions.</span></span> <span data-ttu-id="7daec-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="7daec-126">For example:</span></span>

```csharp
[Route("Home")]
public class HomeController : Controller
{
    [Route("")] // Combines to define the route template "Home"
    [Route("Index")] // Combines to define route template "Home/Index"
    [Route("/")] // Does not combine, defines the route template ""
    public IActionResult Index() {}
```

<span data-ttu-id="7daec-127">Маршруты можно задать с использованием [HttpGet] и схожих атрибутов, что позволяет отказаться от добавления отдельных атрибутов [Route\].</span><span class="sxs-lookup"><span data-stu-id="7daec-127">Routes can be specified on [HttpGet] and similar attributes, avoiding the need to add separate [Route\] attributes.</span></span> <span data-ttu-id="7daec-128">Маршруты с атрибутами также могут использовать маркеры, что позволяет сократить объем использования имен контроллера или действия, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="7daec-128">Attribute routes can also use tokens to reduce the need to repeat controller or action names, as shown below:</span></span>

```csharp
[Route("[controller\]")]
public class ProductsController : Controller
{
    [Route("")] // Matches 'Products'
    [Route("Index")] // Matches 'Products/Index'
    public IActionResult Index()
}
```

<span data-ttu-id="7daec-129">После того как нужный запрос сопоставлен с маршрутом, но до вызова метода действия, модель MVC ASP.NET Core выполняет [привязку](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) и [проверку](https://docs.microsoft.com/aspnet/core/mvc/models/validation) модели по запросу.</span><span class="sxs-lookup"><span data-stu-id="7daec-129">Once a given request has been matched to a route, but before the action method is called, ASP.NET Core MVC will perform [model binding](https://docs.microsoft.com/aspnet/core/mvc/models/model-binding) and [model validation](https://docs.microsoft.com/aspnet/core/mvc/models/validation) on the request.</span></span> <span data-ttu-id="7daec-130">Привязка модели необходима для преобразования входящих данных HTTP в типы .NET, которые задаются в виде параметров вызываемого метода действия.</span><span class="sxs-lookup"><span data-stu-id="7daec-130">Model binding is responsible for converting incoming HTTP data into the .NET types specified as parameters of the action method to be called.</span></span> <span data-ttu-id="7daec-131">Например, если метод действия требует целочисленный параметр идентификатора, привязка модели попытается получить этот параметр из значения, предоставленного в рамках запроса.</span><span class="sxs-lookup"><span data-stu-id="7daec-131">For example, if the action method expects an int id parameter, model binding will attempt to provide this parameter from a value provided as part of the request.</span></span> <span data-ttu-id="7daec-132">Для этого привязка модели будет искать значения в опубликованной форме, в самом маршруте, а также в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="7daec-132">To do so, model binding looks for values in a posted form, values in the route itself, and query string values.</span></span> <span data-ttu-id="7daec-133">Найденное предполагаемое значение идентификатора преобразуется в целочисленный формат, после чего передается в метод действия.</span><span class="sxs-lookup"><span data-stu-id="7daec-133">Assuming an id value is found, it will be converted to an integer before being passed into the action method.</span></span>

<span data-ttu-id="7daec-134">После привязки модели, но перед вызовом метода действия выполняется проверка модели.</span><span class="sxs-lookup"><span data-stu-id="7daec-134">After binding the model but before calling the action method, model validation occurs.</span></span> <span data-ttu-id="7daec-135">При проверке используются необязательные атрибуты типа модели, что позволяет убедиться, что предоставленный объект модели соответствует определенным требованиям к данным.</span><span class="sxs-lookup"><span data-stu-id="7daec-135">Model validation uses optional attributes on the model type, and can help ensure that the provided model object conforms to certain data requirements.</span></span> <span data-ttu-id="7daec-136">Некоторые значения могут задаваться как обязательные или иметь ограниченную длину, диапазон и т. д. Если заданы атрибуты проверки, но модель не соответствует их требованиям, свойству ModelState.IsValid присваивается значение false, и готовится набор правил проверки, завершившихся с ошибкой, которые будут отправлены клиенту, выполнившему запрос.</span><span class="sxs-lookup"><span data-stu-id="7daec-136">Certain values may be specified as required, or limited to a certain length or numeric range, etc. If validation attributes are specified but the model does not conform to their requirements, the property ModelState.IsValid will be false, and the set of failing validation rules will be available to send to the client making the request.</span></span>

<span data-ttu-id="7daec-137">Если вы используете проверку модели, необходимо всегда проверять допустимость модели, прежде чем выполнять какие-либо изменяющие состояние команды. Это позволит предотвратить повреждение приложения из-за недопустимых данных.</span><span class="sxs-lookup"><span data-stu-id="7daec-137">If you are using model validation, you should be sure to always check that the model is valid before performing any state-altering commands, to ensure your app is not corrupted by invalid data.</span></span> <span data-ttu-id="7daec-138">Чтобы не добавлять соответствующий код в каждое действие, можно использовать [фильтр](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters).</span><span class="sxs-lookup"><span data-stu-id="7daec-138">You can use a [filter](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) to avoid the need to add code for this in every action.</span></span> <span data-ttu-id="7daec-139">Фильтры MVC ASP.NET Core предназначены для перехвата групп запросов с той целью, чтобы применить к ним общие политики или сквозную функциональность.</span><span class="sxs-lookup"><span data-stu-id="7daec-139">ASP.NET Core MVC filters offer a way of intercepting groups of requests, so that common policies and cross-cutting concerns can be applied on a targeted basis.</span></span> <span data-ttu-id="7daec-140">Фильтры могут применяться к отдельным действиям, ко всему контроллеру или глобально на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="7daec-140">Filters can be applied to individual actions, whole controllers, or globally for an application.</span></span>

<span data-ttu-id="7daec-141">Для веб-API модель MVC ASP.NET Core поддерживает [*согласование содержимого*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), что позволяет указывать в запросах требуемый формат ответа.</span><span class="sxs-lookup"><span data-stu-id="7daec-141">For web APIs, ASP.NET Core MVC supports [*content negotiation*](https://docs.microsoft.com/aspnet/core/mvc/models/formatting), allowing requests to specify how responses should be formatted.</span></span> <span data-ttu-id="7daec-142">На основании представленных в запросе заголовков действия, возвращающие данные, будут использовать для ответа XML, JSON или другой поддерживаемый формат.</span><span class="sxs-lookup"><span data-stu-id="7daec-142">Based on headers provided in the request, actions returning data will format the response in XML, JSON, or another supported format.</span></span> <span data-ttu-id="7daec-143">Эта возможность позволяет использовать один и тот же API нескольким клиентам с разными требованиями к формату.</span><span class="sxs-lookup"><span data-stu-id="7daec-143">This feature enables the same API to be used by multiple clients with different data format requirements.</span></span>

> ### <a name="references--mapping-requests-to-responses"></a><span data-ttu-id="7daec-144">Ссылки — сопоставление запросов с ответами</span><span class="sxs-lookup"><span data-stu-id="7daec-144">References – Mapping Requests to Responses</span></span>
> - <span data-ttu-id="7daec-145">**Маршрутизация к действиям контроллера**
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span><span class="sxs-lookup"><span data-stu-id="7daec-145">**Routing to Controller Actions**
<https://docs.microsoft.com/aspnet/core/mvc/controllers/routing></span></span>
> - <span data-ttu-id="7daec-146">**Привязка модели** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span><span class="sxs-lookup"><span data-stu-id="7daec-146">**Model Binding** https://docs.microsoft.com/aspnet/core/mvc/models/model-binding</span></span>
> - <span data-ttu-id="7daec-147">**Проверка модели**
> <https://docs.microsoft.com/aspnet/core/mvc/models/validation></span><span class="sxs-lookup"><span data-stu-id="7daec-147">**Model Validation**
<https://docs.microsoft.com/aspnet/core/mvc/models/validation></span></span>
> - <span data-ttu-id="7daec-148">**Фильтры** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span><span class="sxs-lookup"><span data-stu-id="7daec-148">**Filters** https://docs.microsoft.com/aspnet/core/mvc/controllers/filters</span></span>

## <a name="working-with-dependencies"></a><span data-ttu-id="7daec-149">Работа с зависимостями</span><span class="sxs-lookup"><span data-stu-id="7daec-149">Working with Dependencies</span></span>

<span data-ttu-id="7daec-150">ASP.NET Core реализует встроенную поддержку и использование методики [внедрения зависимостей](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span><span class="sxs-lookup"><span data-stu-id="7daec-150">ASP.NET Core has built-in support for and internally makes use of a technique known as [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection).</span></span> <span data-ttu-id="7daec-151">Методика внедрения зависимостей позволяет обеспечить слабую связанность между разными частями приложения.</span><span class="sxs-lookup"><span data-stu-id="7daec-151">Dependency injection is a technique that enabled loose coupling between different parts of an application.</span></span> <span data-ttu-id="7daec-152">Такая реализация является желательной, поскольку упрощает изоляцию частей приложения, что делает их тестирование или замену более эффективными.</span><span class="sxs-lookup"><span data-stu-id="7daec-152">Looser coupling is desirable because it makes it easier to isolate parts of the application, allowing for testing or replacement.</span></span> <span data-ttu-id="7daec-153">Кроме того, в этом случае снижается вероятность того, что изменения в одной части приложения будут иметь непредвиденное влияние на какую-либо другую часть.</span><span class="sxs-lookup"><span data-stu-id="7daec-153">It also makes it less likely that a change in one part of the application will have an unexpected impact somewhere else in the application.</span></span> <span data-ttu-id="7daec-154">Внедрение зависимостей осуществляется на основе принципа инверсии зависимостей и часто является основным фактором, определяющим соблюдение принципа открытости/закрытости.</span><span class="sxs-lookup"><span data-stu-id="7daec-154">Dependency injection is based on the dependency inversion principle, and is often key to achieving the open/closed principle.</span></span> <span data-ttu-id="7daec-155">При оценке того, как ваше приложение работает с зависимостями, следует учитывать риск возникновения проблем со [статическим сцеплением](http://deviq.com/static-cling/) кода и помнить о том, что [ключевое слово new является "клеем" для вашего приложения](https://ardalis.com/new-is-glue).</span><span class="sxs-lookup"><span data-stu-id="7daec-155">When evaluating how your application works with its dependencies, beware of the [static cling](http://deviq.com/static-cling/) code smell, and remember the aphorism "[new is glue](https://ardalis.com/new-is-glue)."</span></span>

<span data-ttu-id="7daec-156">Статическое сцепление происходит тогда, когда классы вызывают статические методы или обращаются к статическим свойствам, в результате чего в инфраструктуре возникают побочные эффекты или зависимости.</span><span class="sxs-lookup"><span data-stu-id="7daec-156">Static cling occurs when your classes make calls to static methods, or access static properties, which have side effects or dependencies on infrastructure.</span></span> <span data-ttu-id="7daec-157">Например, если вы используете метод, который вызывает статический метод, осуществляющий запись в базу данных, ваш метод будет тесно связан с базой.</span><span class="sxs-lookup"><span data-stu-id="7daec-157">For example, if you have a method that calls a static method, which in turn writes to a database, your method is tightly coupled to the database.</span></span> <span data-ttu-id="7daec-158">В таком случае любой сбой в вызове базы данных приведет к нарушению работы вашего метода.</span><span class="sxs-lookup"><span data-stu-id="7daec-158">Anything that breaks that database call will break your method.</span></span> <span data-ttu-id="7daec-159">Тестирование этих методов представляет собой серьезную проблему, поскольку для проведения таких тестов требуется, чтобы коммерческие библиотеки макетирования имитировали статические вызовы. Иначе подобную проверку можно провести только при наличии тестовой базы данных.</span><span class="sxs-lookup"><span data-stu-id="7daec-159">Testing such methods is notoriously difficult, since such tests either require commercial mocking libraries to mock the static calls, or can only be tested with a test database in place.</span></span> <span data-ttu-id="7daec-160">Статические вызовы, которые не имеют зависимостей от инфраструктуры, особенно полностью не поддерживающие отслеживание состояния, можно вызывать без опаски, поскольку они не влияют на степень связанности или возможности тестирования (помимо связанности самого кода со статическим вызовом).</span><span class="sxs-lookup"><span data-stu-id="7daec-160">Static calls that don't have any dependence on infrastructure, especially those that are completely stateless, are fine to call and have no impact on coupling or testability (beyond coupling code to the static call itself).</span></span>

<span data-ttu-id="7daec-161">Многие разработчики осознают риски статического сцепления и глобального состояния, однако по-прежнему допускают связанность кода с конкретными реализациями из-за прямого создания экземпляров.</span><span class="sxs-lookup"><span data-stu-id="7daec-161">Many developers understand the risks of static cling and global state, but will still tightly couple their code to specific implementations through direct instantiation.</span></span> <span data-ttu-id="7daec-162">Об этом напоминает принцип, что ключевое слово new является "клеем" для вашего приложения. Однако это ни в коем случае не значит, что от слова new следует полностью отказаться.</span><span class="sxs-lookup"><span data-stu-id="7daec-162">"New is glue" is meant to be a reminder of this coupling, and not a general condemnation of the use of the new keyword.</span></span> <span data-ttu-id="7daec-163">Как и в случае с вызовами статических методов, создание новых экземпляров типов, не имеющих внешних зависимостей, как правило, не приводит к тесной привязке кода к деталям реализации и не усложняет тестирование.</span><span class="sxs-lookup"><span data-stu-id="7daec-163">Just as with static method calls, new instances of types that have no external dependencies typically do not tightly couple code to implementation details or make testing more difficult.</span></span> <span data-ttu-id="7daec-164">Однако каждый раз, когда создается экземпляр класса, следует задуматься о том, имеет ли смысл жесткая привязка этого экземпляра к конкретному месту или эффективнее будет реализовать запрос этого экземпляра в качестве зависимости.</span><span class="sxs-lookup"><span data-stu-id="7daec-164">But each time a class is instantiated, take just a brief moment to consider whether it makes sense to hard-code that specific instance in that particular location, or if it would be a better design to request that instance as a dependency.</span></span>

### <a name="declare-your-dependencies"></a><span data-ttu-id="7daec-165">Объявление зависимостей</span><span class="sxs-lookup"><span data-stu-id="7daec-165">Declare Your Dependencies</span></span>

<span data-ttu-id="7daec-166">В основе ASP.NET Core лежит принцип объявления методами и классами собственных зависимостей посредством их запроса в виде аргументов.</span><span class="sxs-lookup"><span data-stu-id="7daec-166">ASP.NET Core is built around having methods and classes declare their dependencies, requesting them as arguments.</span></span> <span data-ttu-id="7daec-167">Настройка приложений ASP.NET обычно выполняется в классе Startup, конфигурация которого обеспечивает поддержку внедрения зависимостей в нескольких точках.</span><span class="sxs-lookup"><span data-stu-id="7daec-167">ASP.NET applications are typically set up in a Startup class, which itself is configured to support dependency injection at several points.</span></span> <span data-ttu-id="7daec-168">Если у вашего класса Startup есть конструктор, с его помощью могут запрашиваться зависимости. Например, это может выглядеть так:</span><span class="sxs-lookup"><span data-stu-id="7daec-168">If your Startup class has a constructor, it can request dependencies through the constructor, like so:</span></span>

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

<span data-ttu-id="7daec-169">Класс Startup интересен тем, что для него не определены явные требования к типу.</span><span class="sxs-lookup"><span data-stu-id="7daec-169">The Startup class is interesting in that there are no explicit type requirements for it.</span></span> <span data-ttu-id="7daec-170">Он не наследуется от конкретного базового класса Startup и не реализует какой-либо конкретный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="7daec-170">It doesn't inherit from a special Startup base class, nor does it implement any particular interface.</span></span> <span data-ttu-id="7daec-171">Он может иметь конструктор, для которого вы можете задать любое число параметров, однако при необходимости от конструктора можно отказаться.</span><span class="sxs-lookup"><span data-stu-id="7daec-171">You can give it a constructor, or not, and you can specify as many parameters on the constructor as you want.</span></span> <span data-ttu-id="7daec-172">При запуске веб-узла, который вы настроили для своего приложения, вызывается указанный вами класс Startup, в результате чего все требуемые классом Startup зависимости заполняются посредством внедрения зависимостей.</span><span class="sxs-lookup"><span data-stu-id="7daec-172">When the web host you've configured for your application starts, it will call the Startup class you've told it to use, and will use dependency injection to populate any dependencies the Startup class requires.</span></span> <span data-ttu-id="7daec-173">Естественно, если запросить параметры, которые не были настроены в контейнере служб, используемом ASP.NET Core, будет возвращено исключение. Тем не менее, если вы работаете с известными контейнеру зависимостями, вы можете запрашивать все, что угодно.</span><span class="sxs-lookup"><span data-stu-id="7daec-173">Of course, if you request parameters that aren't configured in the services container used by ASP.NET Core, you'll get an exception, but as long as you stick to dependencies the container knows about, you can request anything you want.</span></span>

<span data-ttu-id="7daec-174">Ваше приложение ASP.NET Core будет поддерживать внедрение зависимостей с самого начала с момента создания экземпляра Startup.</span><span class="sxs-lookup"><span data-stu-id="7daec-174">Dependency injection is built into your ASP.NET Core apps right from the start, when you create the Startup instance.</span></span> <span data-ttu-id="7daec-175">Этим поддержка для класса Startup не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="7daec-175">It doesn't stop there for the Startup class.</span></span> <span data-ttu-id="7daec-176">Вы также можете запрашивать зависимости в методе Configure:</span><span class="sxs-lookup"><span data-stu-id="7daec-176">You can also request dependencies in the Configure method:</span></span>

```csharp
public void Configure(IApplicationBuilder app,
    IHostingEnvironment env,
    ILoggerFactory loggerFactory)
{

}
```

<span data-ttu-id="7daec-177">Исключением является метод ConfigureServices, который принимает всего один параметр типа IServiceCollection.</span><span class="sxs-lookup"><span data-stu-id="7daec-177">The ConfigureServices method is the exception to this behavior; it must take just one parameter of type IServiceCollection.</span></span> <span data-ttu-id="7daec-178">В этом методе поддержка внедрения зависимостей не требуется, поскольку, с одной стороны, он отвечает за добавление объектов в контейнер служб, а с другой — имеет доступ ко всем настроенным в данный момент службам посредством параметра IServiceCollection.</span><span class="sxs-lookup"><span data-stu-id="7daec-178">It doesn't really need to support dependency injection, since on the one hand it is responsible for adding objects to the services container, and on the other it has access to all currently configured services via the IServiceCollection parameter.</span></span> <span data-ttu-id="7daec-179">Таким образом, вы можете работать с зависимостями, определенными в коллекции служб ASP.NET Core, в любой части класса Startup, запрашивая необходимую службу в виде параметра или используя параметр IServiceCollection метода ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="7daec-179">Thus, you can work with dependencies defined in the ASP.NET Core services collection in every part of the Startup class, either by requesting the needed service as a parameter or by working with the IServiceCollection in ConfigureServices.</span></span>

> [!NOTE]
> <span data-ttu-id="7daec-180">Если вам необходимо гарантировать доступность определенных служб для класса Startup, вы можете настроить их с помощью WebHostBuilder и его метода ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="7daec-180">If you need to ensure certain services are available to your Startup class, you can configure them using WebHostBuilder and its ConfigureServices method.</span></span>

<span data-ttu-id="7daec-181">Класс Startup выступает в качестве модели, определяющей требуемую структуру для других частей вашего приложения ASP.NET Core, включая контроллеры, ПО промежуточного слоя, фильтры и ваши собственные службы.</span><span class="sxs-lookup"><span data-stu-id="7daec-181">The Startup class is a model for how you should structure other parts of your ASP.NET Core application, from Controllers to Middleware to Filters to your own Services.</span></span> <span data-ttu-id="7daec-182">В каждом случае необходимо соблюдать [принцип явных зависимостей](http://deviq.com/explicit-dependencies-principle/) и запрашивать зависимости, а не создавать их. Для этих целей в приложении следует использовать внедрение зависимостей.</span><span class="sxs-lookup"><span data-stu-id="7daec-182">In each case, you should follow the [Explicit Dependencies Principle](http://deviq.com/explicit-dependencies-principle/), requesting your dependencies rather than directly creating them, and leveraging dependency injection throughout your application.</span></span> <span data-ttu-id="7daec-183">Обращайте внимание на то, где и как осуществляется прямое создание экземпляров реализаций, особенно для служб и объектов, которые работают с инфраструктурой или имеют побочные эффекты.</span><span class="sxs-lookup"><span data-stu-id="7daec-183">Be careful of where and how you directly instantiate implementations, especially services and objects that work with infrastructure or have side effects.</span></span> <span data-ttu-id="7daec-184">Отдавайте предпочтение работе с абстракциями, которые определены в ядре приложения и передаются в качестве аргументов, и не увлекайтесь жестким определением ссылок на конкретные типы реализации.</span><span class="sxs-lookup"><span data-stu-id="7daec-184">Prefer working with abstractions defined in your application core and passed in as arguments to hardcoding references to specific implementation types.</span></span>

## <a name="structuring-the-application"></a><span data-ttu-id="7daec-185">Структурирование приложения</span><span class="sxs-lookup"><span data-stu-id="7daec-185">Structuring the Application</span></span>

<span data-ttu-id="7daec-186">Монолитные приложения обычно имеют одну точку входа.</span><span class="sxs-lookup"><span data-stu-id="7daec-186">Monolithic applications typically have a single entry point.</span></span> <span data-ttu-id="7daec-187">Для веб-приложения ASP.NET Core точкой входа служит веб-проект ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7daec-187">In the case of an ASP.NET Core web application, the entry point will be the ASP.NET Core web project.</span></span> <span data-ttu-id="7daec-188">Тем не менее это не означает, что решение обязательно должно состоять из одного проекта.</span><span class="sxs-lookup"><span data-stu-id="7daec-188">However, that doesn't mean the solution should consist of just a single project.</span></span> <span data-ttu-id="7daec-189">В соответствии с принципом разделения задач рекомендуется разбивать приложение на слои.</span><span class="sxs-lookup"><span data-stu-id="7daec-189">It's useful to break up the application into different layers in order to follow separation of concerns.</span></span> <span data-ttu-id="7daec-190">После этого следует рассмотреть возможность разделения проектов по папкам, что позволит достичь более эффективной инкапсуляции.</span><span class="sxs-lookup"><span data-stu-id="7daec-190">Once broken up into layers, it's helpful to go beyond folders to separate projects, which can help achieve better encapsulation.</span></span> <span data-ttu-id="7daec-191">Оптимальным способом достичь этих целей в приложении ASP.NET Core является использование варианта чистой архитектуры, которая обсуждается в главе 5.</span><span class="sxs-lookup"><span data-stu-id="7daec-191">The best approach to achieve these goals with an ASP.NET Core application is a variation of the Clean Architecture discussed in chapter 5.</span></span> <span data-ttu-id="7daec-192">При таком подходе решение приложения должно состоять из отдельных библиотек для пользовательского интерфейса, инфраструктуры и ядра приложения.</span><span class="sxs-lookup"><span data-stu-id="7daec-192">Following this approach, the application's solution will be comprised of separate libraries for the UI, Infrastructure, and ApplicationCore.</span></span>

<span data-ttu-id="7daec-193">В дополнение к этим проектам также включаются отдельные тестовые проекты (тестирование обсуждается в главе 9).</span><span class="sxs-lookup"><span data-stu-id="7daec-193">In addition to these projects, separate test projects are included as well (Testing is discussed in Chapter 9).</span></span>

<span data-ttu-id="7daec-194">Объектная модель и интерфейсы приложения должны располагаться в проекте ядра приложения.</span><span class="sxs-lookup"><span data-stu-id="7daec-194">The application's object model and interfaces should be placed in the ApplicationCore project.</span></span> <span data-ttu-id="7daec-195">Этот проект будет иметь минимально возможное количество зависимостей, и на него будут ссылаться другие проекты решения.</span><span class="sxs-lookup"><span data-stu-id="7daec-195">This project will have as few dependencies as possible, and the other projects in the solution will reference it.</span></span> <span data-ttu-id="7daec-196">Необходимые бизнес-сущности определяются в проекте ядра приложения, как и службы, которые не зависят напрямую от инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7daec-196">Business entities that need to be persisted are defined in the ApplicationCore project, as are services that do not directly depend on infrastructure.</span></span>

<span data-ttu-id="7daec-197">Детали реализации, в том числе способ реализации сохраняемости или отправки уведомлений пользователю, определяются в проекте инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7daec-197">Implementation details, such as how persistence is performed or how notifications might be sent to a user, are kept in the Infrastructure project.</span></span> <span data-ttu-id="7daec-198">Этот проект будет ссылаться на зависящие от реализации пакеты, например Entity Framework Core, однако не должен предоставлять детали таких реализаций за пределы проекта.</span><span class="sxs-lookup"><span data-stu-id="7daec-198">This project will reference implementation-specific packages such as Entity Framework Core, but should not expose details about these implementations outside of the project.</span></span> <span data-ttu-id="7daec-199">Службы и репозитории инфраструктуры должны реализовывать интерфейсы, которые определены в проекте ядра приложения, а ее реализации сохраняемости обеспечивают извлечение и хранение сущностей, определенных в ядре приложения.</span><span class="sxs-lookup"><span data-stu-id="7daec-199">Infrastructure services and repositories should implement interfaces that are defined in the ApplicationCore project, and its persistence implementations are responsible for retrieving and storing entities defined in ApplicationCore.</span></span>

<span data-ttu-id="7daec-200">Проект пользовательского интерфейса ASP.NET Core отвечает за выполнение задач уровня пользовательского интерфейса, но не должен включать детали бизнес-логики или инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7daec-200">The ASP.NET Core UI project is responsible for any UI level concerns, but should not include business logic or infrastructure details.</span></span> <span data-ttu-id="7daec-201">Фактически, в идеальном случае он не должен иметь зависимостей от проекта инфраструктуры, что позволяет исключить случайное появление зависимостей между этими двумя проектами.</span><span class="sxs-lookup"><span data-stu-id="7daec-201">In fact, ideally it shouldn't even have a dependency on the Infrastructure project, which will help ensure no dependency between the two projects is introduced accidentally.</span></span> <span data-ttu-id="7daec-202">Для этого может использоваться сторонний контейнер внедрения зависимостей, например StructureMap, который позволяет определять правила внедрения зависимостей в классах реестра в каждом проекте.</span><span class="sxs-lookup"><span data-stu-id="7daec-202">This can be achieved using a third-party DI container like StructureMap, which allows you to define DI rules in Registry classes in each project.</span></span>

<span data-ttu-id="7daec-203">Другой подход к ослаблению связанности приложения с деталями реализации заключается в вызове из приложения микрослужб, которые могут быть развернуты в отдельных контейнерах Docker.</span><span class="sxs-lookup"><span data-stu-id="7daec-203">Another approach to decoupling the application from implementation details is to have the application call microservices, perhaps deployed in individual Docker containers.</span></span> <span data-ttu-id="7daec-204">Таким образом обеспечивается дополнительное разделение задач и ослабление связанности по сравнению с внедрением зависимостей между двумя проектами, однако такой подход связан с определенными сложностями.</span><span class="sxs-lookup"><span data-stu-id="7daec-204">This provides even greater separation of concerns and decoupling than leveraging DI between two projects, but has additional complexity.</span></span>

### <a name="feature-organization"></a><span data-ttu-id="7daec-205">Организация компонентов</span><span class="sxs-lookup"><span data-stu-id="7daec-205">Feature Organization</span></span>

<span data-ttu-id="7daec-206">По умолчанию структура папок приложения ASP.NET Core включает контроллеры, представления и зачастую модели представлений.</span><span class="sxs-lookup"><span data-stu-id="7daec-206">By default, ASP.NET Core applications organize their folder structure to include Controllers and Views, and frequently ViewModels.</span></span> <span data-ttu-id="7daec-207">Код на стороне клиента, обеспечивающий поддержку таких структур на стороне сервера, как правило, хранится отдельно в папке wwwroot.</span><span class="sxs-lookup"><span data-stu-id="7daec-207">Client-side code to support these server-side structures is typically stored separately in the wwwroot folder.</span></span> <span data-ttu-id="7daec-208">Тем не менее в крупных приложениях при такой организации могут возникать проблемы, поскольку для работы с конкретным компонентом может потребоваться переход между этими папками.</span><span class="sxs-lookup"><span data-stu-id="7daec-208">However, large applications may encounter problems with this organization, since working on any given feature often requires jumping between these folders.</span></span> <span data-ttu-id="7daec-209">С увеличением числа файлов и вложенных папок в каждой папке сложности только возрастают, в связи с чем приходится тратить дополнительное время на просмотр в обозревателе решений.</span><span class="sxs-lookup"><span data-stu-id="7daec-209">This gets more and more difficult as the number of files and subfolders in each folder grows, resulting in a great deal of scrolling through Solution Explorer.</span></span> <span data-ttu-id="7daec-210">Одним из решений этой проблемы может стать упорядочение кода приложения по *компонентам*, а не по типу файлов.</span><span class="sxs-lookup"><span data-stu-id="7daec-210">One solution to this problem is to organize application code by *feature* instead of by file type.</span></span> <span data-ttu-id="7daec-211">Такой стиль организации обычно называется папками или срезами компонентов (см. также статью [Вертикальные срезы](http://deviq.com/vertical-slices/)).</span><span class="sxs-lookup"><span data-stu-id="7daec-211">This organizational style is typically referred to as feature folders or feature slices (see also: [Vertical Slices](http://deviq.com/vertical-slices/)).</span></span>

<span data-ttu-id="7daec-212">Для этой цели в модели MVC ASP.NET Core поддерживаются области.</span><span class="sxs-lookup"><span data-stu-id="7daec-212">ASP.NET Core MVC supports Areas for this purpose.</span></span> <span data-ttu-id="7daec-213">С помощью областей можно создавать отдельные наборы папок контролеров и представлений (а также связанных с ними моделей) в каждой папке области.</span><span class="sxs-lookup"><span data-stu-id="7daec-213">Using areas, you can create separate sets of Controllers and Views folders (as well as any associated models) in each Area folder.</span></span> <span data-ttu-id="7daec-214">На рис. 7-1 показан пример структуры папок, в которой используются области.</span><span class="sxs-lookup"><span data-stu-id="7daec-214">Figure 7-1 shows an example folder structure, using Areas.</span></span>

![](./media/image7-1.png)

<span data-ttu-id="7daec-215">Рис. 7-1. Пример организации областей</span><span class="sxs-lookup"><span data-stu-id="7daec-215">Figure 7-1 Sample Area Organization</span></span>

<span data-ttu-id="7daec-216">При работе с областями необходимо использовать атрибуты, чтобы декорировать контроллеры с указанием имени области, которой они принадлежат:</span><span class="sxs-lookup"><span data-stu-id="7daec-216">When using Areas, you must use attributes to decorate your controllers with the name of the area to which they belong:</span></span>

```csharp
[Area("Catalog")]
public class HomeController
{}
```

<span data-ttu-id="7daec-217">Также необходимо добавить поддержку областей для маршрутов:</span><span class="sxs-lookup"><span data-stu-id="7daec-217">You also need to add area support to your routes:</span></span>

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

<span data-ttu-id="7daec-218">Помимо встроенной поддержки областей, вы можете использовать собственную структуру папок и соглашения вместо атрибутов и настраиваемых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="7daec-218">In addition to the built-in support for Areas, you can also use your own folder structure, and conventions in place of attributes and custom routes.</span></span> <span data-ttu-id="7daec-219">В этом случае у вас будут папки компонентов, не содержащие отдельных папок для представлений, контроллеров и т. д., благодаря чему иерархия будет иметь меньше уровней, что позволит упростить поиск всех файлов для конкретного компонента в одном месте.</span><span class="sxs-lookup"><span data-stu-id="7daec-219">This would allow you to have feature folders that didn't include separate folders for Views, Controllers, etc., keeping the hierarchy flatter and making it easier to see all related files in a single place for each feature.</span></span>

<span data-ttu-id="7daec-220">В ASP.NET Core это поведение реализуется с использованием встроенных типов соглашений.</span><span class="sxs-lookup"><span data-stu-id="7daec-220">ASP.NET Core uses built-in convention types to control its behavior.</span></span> <span data-ttu-id="7daec-221">При необходимости эти соглашения можно изменить или заменить.</span><span class="sxs-lookup"><span data-stu-id="7daec-221">You can modify or replace these conventions.</span></span> <span data-ttu-id="7daec-222">Например, вы можете определить соглашение, по которому имя компонента для указанного контроллера будет получаться автоматически на основе его пространства имен (оно обычно связано с папкой, в которой располагается контроллер):</span><span class="sxs-lookup"><span data-stu-id="7daec-222">For example, you can create a convention that will automatically get the feature name for a given controller based on its namespace (which typically correlates to the folder in which the controller is located):</span></span>

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

<span data-ttu-id="7daec-223">Затем это соглашение указывается в качестве варианта при добавлении поддержки модели MVC для приложения в ConfigureServices:</span><span class="sxs-lookup"><span data-stu-id="7daec-223">You then specify this convention as an option when you add support for MVC to your application in ConfigureServices:</span></span>

```csharp
services.AddMvc(o => o.Conventions.Add(new FeatureConvention()));
```

<span data-ttu-id="7daec-224">Модель MVC ASP.NET Core также использует соглашение для поиска представлений.</span><span class="sxs-lookup"><span data-stu-id="7daec-224">ASP.NET Core MVC also uses a convention to locate views.</span></span> <span data-ttu-id="7daec-225">Вы можете переопределить его с использованием настраиваемого соглашения, чтобы задать поиск представлений в папках компонентов (будет использоваться имя компонента, предоставленное ранее с помощью FeatureConvention).</span><span class="sxs-lookup"><span data-stu-id="7daec-225">You can override it with a custom convention so that views will be located in your feature folders (using the feature name provided by the FeatureConvention, above).</span></span> <span data-ttu-id="7daec-226">Узнать больше об этом подходе и скачать рабочий пример можно в статье MSDN, посвященной [срезам компонентов для модели MVC ASP.NET Core](https://msdn.microsoft.com/magazine/mt763233.aspx).</span><span class="sxs-lookup"><span data-stu-id="7daec-226">You can learn more about this approach and download a working sample from the MSDN article, [Feature Slices for ASP.NET Core MVC](https://msdn.microsoft.com/magazine/mt763233.aspx).</span></span>

### <a name="cross-cutting-concerns"></a><span data-ttu-id="7daec-227">Сквозная функциональность</span><span class="sxs-lookup"><span data-stu-id="7daec-227">Cross-Cutting Concerns</span></span>

<span data-ttu-id="7daec-228">По мере расширения приложения все большую важность приобретает вопрос вынесения сквозной функциональности, что позволяет исключить дублирование и обеспечить согласованность.</span><span class="sxs-lookup"><span data-stu-id="7daec-228">As applications grow, it becomes increasingly important to factor out cross-cutting concerns to eliminate duplication and maintain consistency.</span></span> <span data-ttu-id="7daec-229">В качестве примеров сквозной функциональности в приложениях ASP.NET Core можно привести задачи проверки подлинности, правила проверки моделей, кэширование вывода и обработку ошибок.</span><span class="sxs-lookup"><span data-stu-id="7daec-229">Some examples of cross-cutting concerns in ASP.NET Core applications are authentication, model validation rules, output caching, and error handling, though there are many others.</span></span> <span data-ttu-id="7daec-230">[Фильтры](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) в ASP.NET Core MVC позволяют выполнять код до или после определенных стадий в конвейере обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="7daec-230">ASP.NET Core MVC [filters](https://docs.microsoft.com/aspnet/core/mvc/controllers/filters) allow you to run code before or after certain steps in the request processing pipeline.</span></span> <span data-ttu-id="7daec-231">Например, фильтр можно выполнять до и после привязки модели, выполнения действия или получения результата действия.</span><span class="sxs-lookup"><span data-stu-id="7daec-231">For instance, a filter can run before and after model binding, before and after an action, or before and after an action's result.</span></span> <span data-ttu-id="7daec-232">Кроме того, с помощью фильтра авторизации можно управлять доступом к оставшейся части конвейера.</span><span class="sxs-lookup"><span data-stu-id="7daec-232">You can also use an authorization filter to control access to the rest of the pipeline.</span></span> <span data-ttu-id="7daec-233">На рис. 7-2 показан поток выполнения запроса через настроенные фильтры.</span><span class="sxs-lookup"><span data-stu-id="7daec-233">Figures 7-2 shows how request execution flows through filters, if configured.</span></span>

![Запрос обрабатывается посредством фильтров авторизации, фильтров ресурсов, привязки модели, фильтров действий, выполнения действия и преобразования результата действия, фильтров исключений, фильтров результатов и выполнения результатов.](./media/image7-2.png)

<span data-ttu-id="7daec-236">Рис. 7-2. Выполнение запроса через фильтры и конвейер обработки запросов.</span><span class="sxs-lookup"><span data-stu-id="7daec-236">Figure 7-2 Request execution through filters and request pipeline.</span></span>

<span data-ttu-id="7daec-237">Фильтры обычно реализуются в виде атрибутов, поэтому их можно применять к контроллерам или действиям.</span><span class="sxs-lookup"><span data-stu-id="7daec-237">Filters are usually implemented as attributes, so you can apply them controllers or actions.</span></span> <span data-ttu-id="7daec-238">При добавлении таким способом фильтры, задаваемые на уровне действия, переопределяют (или используют в качестве основы) фильтры уровня контроллера, которые, в свою очередь, переопределяют глобальные фильтры.</span><span class="sxs-lookup"><span data-stu-id="7daec-238">When added in this fashion, filters specified at the action level override or build upon filters specified at the controller level, which themselves override global filters.</span></span> <span data-ttu-id="7daec-239">Например, атрибут \[Route\] может использоваться для создания маршрутов между контроллерами и действиями.</span><span class="sxs-lookup"><span data-stu-id="7daec-239">For example, the \[Route\] attribute can be used to build up routes between controllers and actions.</span></span> <span data-ttu-id="7daec-240">Аналогичным образом можно настроить авторизацию на уровне контроллера и затем переопределить ее для отдельных действий, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7daec-240">Likewise, authorization can be configured at the controller level, and then overridden by individual actions, as the following sample demonstrates:</span></span>

```csharp
[Authorize]
public class AccountController : Controller

{
    [AllowAnonymous]
    public async Task<IActionResult> Login() {}
    public async Task<IActionResult> ForgotPassword() {}
}
```

<span data-ttu-id="7daec-241">Первый метод, Login, использует фильтр AllowAnonymous (атрибут) для переопределения фильтра Authorize, заданного на уровне контроллера.</span><span class="sxs-lookup"><span data-stu-id="7daec-241">The first method, Login, uses the AllowAnonymous filter (attribute) to override the Authorize filter set at the controller level.</span></span> <span data-ttu-id="7daec-242">Действие ForgotPassword (и любое другое действие в классе без атрибута AllowAnonymous) потребует запрос с проверкой подлинности.</span><span class="sxs-lookup"><span data-stu-id="7daec-242">The ForgotPassword action (and any other action in the class that doesn't have an AllowAnonymous attribute) will require an authenticated request.</span></span>

<span data-ttu-id="7daec-243">С помощью фильтров можно исключить дублирование, выражаемое общими политиками обработки ошибок для API.</span><span class="sxs-lookup"><span data-stu-id="7daec-243">Filters can be used to eliminate duplication in the form of common error handling policies for APIs.</span></span> <span data-ttu-id="7daec-244">Например, типовая политика API предусматривает возврат ответа NotFound для запросов, ссылающихся на несуществующие ключи, а также ответа BadRequest в случае сбоя при проверке модели.</span><span class="sxs-lookup"><span data-stu-id="7daec-244">For example, a typical API policy is to return a NotFound response to requests referencing keys that do not exist, and a BadRequest response if model validation fails.</span></span> <span data-ttu-id="7daec-245">Действие этих двух политик демонстрируется в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="7daec-245">The following example demonstrates these two policies in action:</span></span>

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

<span data-ttu-id="7daec-246">Не перегружайте свои методы действия подобным условным кодом.</span><span class="sxs-lookup"><span data-stu-id="7daec-246">Don't allow your action methods to become cluttered with conditional code like this.</span></span> <span data-ttu-id="7daec-247">Вместо этого следует вынести политики в фильтры, которые будут применяться по необходимости.</span><span class="sxs-lookup"><span data-stu-id="7daec-247">Instead, pull the policies into filters that can be applied on an as-needed basis.</span></span> <span data-ttu-id="7daec-248">В этом примере проверку модели, которая должна выполняться каждый раз при отправке команды в API, можно заменить следующим атрибутом:</span><span class="sxs-lookup"><span data-stu-id="7daec-248">In this example, the model validation check, which should occur any time a command is sent to the API, can be replaced by the following attribute:</span></span>

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

<span data-ttu-id="7daec-249">Аналогичным образом с помощью фильтра можно проверить факт существования записи и вернуть ошибку 404 до выполнения действия. Это позволит исключить необходимость выполнять такие проверки в самом действии.</span><span class="sxs-lookup"><span data-stu-id="7daec-249">Likewise, a filter can be used to check if a record exists and return a 404 before the action is executed, eliminating the need to perform these checks in the action.</span></span> <span data-ttu-id="7daec-250">После вынесения общих соглашений и организации решения таким образом, чтобы отделить код инфраструктуры и бизнес-логики от пользовательского интерфейса, метод действия MVC будет иметь минимальный размер:</span><span class="sxs-lookup"><span data-stu-id="7daec-250">Once you've pulled out common conventions and organized your solution to separate infrastructure code and business logic from your UI, your MVC action methods should be extremely thin:</span></span>

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

<span data-ttu-id="7daec-251">Узнать больше о реализации фильтров и скачать рабочий пример можно в статье MSDN, посвященной [применению фильтров MVC для ASP.NET Core в реальном мире](https://msdn.microsoft.com/magazine/mt767699.aspx).</span><span class="sxs-lookup"><span data-stu-id="7daec-251">You can read more about implementing filters and download a working sample from the MSDN article, [Real World ASP.NET Core MVC Filters](https://msdn.microsoft.com/magazine/mt767699.aspx).</span></span>

> ### <a name="references--structuring-applications"></a><span data-ttu-id="7daec-252">Ссылки — структурирование приложений</span><span class="sxs-lookup"><span data-stu-id="7daec-252">References – Structuring Applications</span></span>
> - <span data-ttu-id="7daec-253">**Области**</span><span class="sxs-lookup"><span data-stu-id="7daec-253">**Areas**</span></span>  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/areas>
> - <span data-ttu-id="7daec-254">**MSDN — срезы функций для ASP.NET Core MVC**
>  <https://msdn.microsoft.com/magazine/mt763233.aspx></span><span class="sxs-lookup"><span data-stu-id="7daec-254">**MSDN – Feature Slices for ASP.NET Core MVC**
<https://msdn.microsoft.com/magazine/mt763233.aspx></span></span>
> - <span data-ttu-id="7daec-255">**Фильтры**</span><span class="sxs-lookup"><span data-stu-id="7daec-255">**Filters**</span></span>  
> <https://docs.microsoft.com/aspnet/core/mvc/controllers/filters>
> - <span data-ttu-id="7daec-256">**MSDN — фильтры MVC для ASP.NET Core в реальном мире**</span><span class="sxs-lookup"><span data-stu-id="7daec-256">**MSDN – Real World ASP.NET Core MVC Filters**</span></span>  
> <https://msdn.microsoft.com/magazine/mt767699.aspx>

## <a name="security"></a><span data-ttu-id="7daec-257">Безопасность</span><span class="sxs-lookup"><span data-stu-id="7daec-257">Security</span></span>

<span data-ttu-id="7daec-258">Обеспечение безопасности веб-приложений — это серьезная проблема, требующая решения множества задач.</span><span class="sxs-lookup"><span data-stu-id="7daec-258">Securing web applications is a large topic, with many considerations.</span></span> <span data-ttu-id="7daec-259">На базовом уровне обеспечение безопасности подразумевает знание источника запроса и предоставление запросу доступа только к необходимым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="7daec-259">At its most basic level, security involves ensuring you know who a given request is coming from, and then ensuring that that request only has access to resources it should.</span></span> <span data-ttu-id="7daec-260">Процесс проверки подлинности предусматривает сравнение предоставленных в запросе учетных данных с теми, которые находятся в хранилище доверенных данных. Это позволяет определить, является ли источник запроса известной сущностью.</span><span class="sxs-lookup"><span data-stu-id="7daec-260">Authentication is the process of comparing credentials provided with a request to those in a trusted data store, to see if the request should be treated as coming from a known entity.</span></span> <span data-ttu-id="7daec-261">Процесс авторизации предусматривает ограничение доступа к определенным ресурсам на основе удостоверения пользователя.</span><span class="sxs-lookup"><span data-stu-id="7daec-261">Authorization is the process of restricting access to certain resources based on user identity.</span></span> <span data-ttu-id="7daec-262">Еще одна задача заключается в защите от перехвата запросов третьими лицами. Для этого в приложении как минимум [должен использоваться протокол SSL](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).</span><span class="sxs-lookup"><span data-stu-id="7daec-262">A third security concern is protecting requests from eavesdropping by third parties, for which you should at least [ensure that SSL is used by your application](https://docs.microsoft.com/aspnet/core/security/enforcing-ssl).</span></span>

### <a name="authentication"></a><span data-ttu-id="7daec-263">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="7daec-263">Authentication</span></span>

<span data-ttu-id="7daec-264">Удостоверение ASP.NET Core — это система членства, с помощью которой обеспечивается поддержка функций входа в ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="7daec-264">ASP.NET Core Identity is a membership system you can use to support login functionality for your application.</span></span> <span data-ttu-id="7daec-265">Благодаря этому поддерживаются учетные записи локальных пользователей, а также внешние поставщики служб входа, включая учетные записи Майкрософт, Twitter, Facebook, Google и многие другие.</span><span class="sxs-lookup"><span data-stu-id="7daec-265">It has support for local user accounts as well as external login provider support from providers like Microsoft Account, Twitter, Facebook, Google, and more.</span></span> <span data-ttu-id="7daec-266">В дополнение к удостоверению ASP.NET Core в приложении может использоваться проверка подлинности Windows или сторонний поставщик служб проверки подлинности, например [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span><span class="sxs-lookup"><span data-stu-id="7daec-266">In addition to ASP.NET Core Identity, your application can use windows authentication, or a third-party identity provider like [Identity Server](https://github.com/IdentityServer/IdentityServer4).</span></span>

<span data-ttu-id="7daec-267">Удостоверение ASP.NET Core включается в шаблоны новых проектов в том случае, если выбран параметр "Учетные записи отдельных пользователей".</span><span class="sxs-lookup"><span data-stu-id="7daec-267">ASP.NET Core Identity is included in new project templates if the Individual User Accounts option is selected.</span></span> <span data-ttu-id="7daec-268">Этот шаблон включает поддержку регистрации, входа, внешних имен входа, забытых паролей и других дополнительных функций.</span><span class="sxs-lookup"><span data-stu-id="7daec-268">This template includes support for registration, login, external logins, forgotten passwords, and additional functionality.</span></span>

![](./media/image7-3.png)

<span data-ttu-id="7daec-269">Рис. 7-3. Выбор параметра "Учетные записи отдельных пользователей" для использования предварительного настроенного удостоверения.</span><span class="sxs-lookup"><span data-stu-id="7daec-269">Figure 7-3 Select Individual User Accounts to have Identity preconfigured.</span></span>

<span data-ttu-id="7daec-270">Поддержка удостоверения реализуется в классе Startup в методах ConfigureServices и Configure:</span><span class="sxs-lookup"><span data-stu-id="7daec-270">Identity support is configured in Startup, both in ConfigureServices and Configure:</span></span>

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

<span data-ttu-id="7daec-271">В методе Configure UseIdentity обязательно должно указываться раньше, чем UseMvc.</span><span class="sxs-lookup"><span data-stu-id="7daec-271">It's important that UseIdentity appear before UseMvc in the Configure method.</span></span> <span data-ttu-id="7daec-272">При настройке удостоверения в ConfigureServices вы можете обратить внимание на вызов AddDefaultTokenProviders.</span><span class="sxs-lookup"><span data-stu-id="7daec-272">When configuring Identity in ConfigureServices, you'll notice a call to AddDefaultTokenProviders.</span></span> <span data-ttu-id="7daec-273">Этот вызов не связан с маркерами, которые могут использоваться для защиты веб-соединений. Он относится к поставщикам, создающим запросы, которые могут направляться пользователям в сообщениях электронной почты или SMS для подтверждения их личности.</span><span class="sxs-lookup"><span data-stu-id="7daec-273">This has nothing to do with tokens that may be used to secure web communications, but instead refers to providers that create prompts that can be sent to users via SMS or email in order for them to confirm their identity.</span></span>

<span data-ttu-id="7daec-274">Дополнительные сведения о [настройке двухфакторной проверки подлинности](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) и [использовании внешних поставщиков служб входа](https://docs.microsoft.com/aspnet/core/security/authentication/social/) см. в официальной документации по ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7daec-274">You can learn more about [configuring two-factor authentication](https://docs.microsoft.com/aspnet/core/security/authentication/2fa) and [enabling external login providers](https://docs.microsoft.com/aspnet/core/security/authentication/social/) from the official ASP.NET Core docs.</span></span>

### <a name="authorization"></a><span data-ttu-id="7daec-275">Авторизация</span><span class="sxs-lookup"><span data-stu-id="7daec-275">Authorization</span></span>

<span data-ttu-id="7daec-276">Простейшая форма авторизации предусматривает запрет на доступ анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="7daec-276">The simplest form of authorization involves restricting access to anonymous users.</span></span> <span data-ttu-id="7daec-277">Чтобы реализовать это, достаточно применить атрибут \[Authorize\] к определенным контроллерам и действиям.</span><span class="sxs-lookup"><span data-stu-id="7daec-277">This can be achieved by simply applying the \[Authorize\] attribute to certain controllers or actions.</span></span> <span data-ttu-id="7daec-278">При использовании ролей этот атрибут можно расширить, ограничив доступ для пользователей с определенными ролями, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="7daec-278">If roles are being used, the attribute can be further extended to restrict access to users who belong to certain roles, as shown:</span></span>

```csharp
[Authorize(Roles = "HRManager,Finance")]
public class SalaryController : Controller
{

}
```

<span data-ttu-id="7daec-279">В этом случае доступ к контроллеру SalaryController будут иметь пользователи, которым назначены роли HRManager или Finance (или одновременно обе эти роли).</span><span class="sxs-lookup"><span data-stu-id="7daec-279">In this case, users belonging to either the HRManager or Finance roles (or both) would have access to the SalaryController.</span></span> <span data-ttu-id="7daec-280">Если пользователь должен иметь одновременно несколько ролей, этот атрибут можно применить несколько раз, в каждом случае указывая нужную роль.</span><span class="sxs-lookup"><span data-stu-id="7daec-280">To require that a user belong to multiple roles (not just one of several), you can apply the attribute multiple times, specifying a required role each time.</span></span>

<span data-ttu-id="7daec-281">Если наборы ролей указываются в виде строк в различных контроллерах и действиях, это может привести к нежелательному дублированию.</span><span class="sxs-lookup"><span data-stu-id="7daec-281">Specifying certain sets of roles as strings in many different controllers and actions can lead to undesirable repetition.</span></span> <span data-ttu-id="7daec-282">Вместо применения отдельных ролей с помощью атрибута \[Authorize\] можно настроить политики авторизации, которые будут инкапсулировать правила авторизации:</span><span class="sxs-lookup"><span data-stu-id="7daec-282">You can configure authorization policies, which encapsulate authorization rules, and then specify the policy instead of individual roles when applying the \[Authorize\] attribute:</span></span>

```csharp
[Authorize(Policy = "CanViewPrivateReport")]
public IActionResult ExecutiveSalaryReport()
{
    return View();
}
```

<span data-ttu-id="7daec-283">Такой подход к применению политик позволяет разделить виды действий, доступ к которым ограничивается на основе ролей или применяемых правил.</span><span class="sxs-lookup"><span data-stu-id="7daec-283">Using policies in this way, you can separate the kinds of actions being restricted from the specific roles or rules that apply to it.</span></span> <span data-ttu-id="7daec-284">Впоследствии при создании новой роли, которой требуется доступ к определенным ресурсам, достаточно просто обновить политику вместо того, чтобы обновлять все списки ролей для каждого атрибута \[Authorize\].</span><span class="sxs-lookup"><span data-stu-id="7daec-284">Later, if you create a new role that needs to have access to certain resources, you can just update a policy, rather than updating every list of roles on every \[Authorize\] attribute.</span></span>

#### <a name="claims"></a><span data-ttu-id="7daec-285">Утверждения</span><span class="sxs-lookup"><span data-stu-id="7daec-285">Claims</span></span>

<span data-ttu-id="7daec-286">Утверждения — это пары имен и значений, которые представляют свойства прошедшего проверку подлинности пользователя.</span><span class="sxs-lookup"><span data-stu-id="7daec-286">Claims are name value pairs that represent properties of an authenticated user.</span></span> <span data-ttu-id="7daec-287">Например, в виде утверждения могут храниться номера сотрудников.</span><span class="sxs-lookup"><span data-stu-id="7daec-287">For example, you might store users' employee number as a claim.</span></span> <span data-ttu-id="7daec-288">Утверждения могут использоваться в рамках политик авторизации.</span><span class="sxs-lookup"><span data-stu-id="7daec-288">Claims can then be used as part of authorization policies.</span></span> <span data-ttu-id="7daec-289">Например, вы можете создать политику EmployeeOnly, которая требует наличия утверждения с названием EmployeeNumber, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="7daec-289">You could create a policy called "EmployeeOnly" that requires the existence of a claim called "EmployeeNumber", as shown in this example:</span></span>

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

<span data-ttu-id="7daec-290">Эту политику можно использовать совместно с атрибутом \[Authorize\] для защиты любых контроллеров и действий, как описывается выше.</span><span class="sxs-lookup"><span data-stu-id="7daec-290">This policy could then be used with the \[Authorize\] attribute to protect any controller and/or action, as described above.</span></span>

#### <a name="securing-web-apis"></a><span data-ttu-id="7daec-291">Защита веб-API</span><span class="sxs-lookup"><span data-stu-id="7daec-291">Securing Web APIs</span></span>

<span data-ttu-id="7daec-292">В большинстве веб-API должна применяться система проверки подлинности на основе маркеров.</span><span class="sxs-lookup"><span data-stu-id="7daec-292">Most web APIs should implement a token-based authentication system.</span></span> <span data-ttu-id="7daec-293">Проверка подлинности на основе маркеров реализуется без сохранения сведений о состоянии и предусматривает возможность масштабирования.</span><span class="sxs-lookup"><span data-stu-id="7daec-293">Token authentication is stateless and designed to be scalable.</span></span> <span data-ttu-id="7daec-294">В системе на основе маркеров клиент сначала должен пройти проверку подлинности с использованием соответствующего поставщика.</span><span class="sxs-lookup"><span data-stu-id="7daec-294">In a token-based authentication system, the client must first authenticate with the authentication provider.</span></span> <span data-ttu-id="7daec-295">В случае успешного прохождения проверки клиент получает маркер, который представляет собой зашифрованную значащую строку символов.</span><span class="sxs-lookup"><span data-stu-id="7daec-295">If successful, the client is issued a token, which is simply a cryptographically meaningful string of characters.</span></span> <span data-ttu-id="7daec-296">Впоследствии при отправке запроса к API клиент добавляет этот маркер в заголовок запроса.</span><span class="sxs-lookup"><span data-stu-id="7daec-296">When the client then needs to issue a request to an API, it adds this token as a header on the request.</span></span> <span data-ttu-id="7daec-297">Перед выполнением запроса сервер проверяет маркер, указанный в его заголовке.</span><span class="sxs-lookup"><span data-stu-id="7daec-297">The server then validates the token found in the request header before completing the request.</span></span> <span data-ttu-id="7daec-298">Этот процесс показан на рис. 7-4.</span><span class="sxs-lookup"><span data-stu-id="7daec-298">Figure 7-4 demonstrates this process.</span></span>

![Проверка подлинности на основе маркеров](./media/image7-4.png)

<span data-ttu-id="7daec-300">**Рис. 7-4.**</span><span class="sxs-lookup"><span data-stu-id="7daec-300">**Figure 7-4.**</span></span> <span data-ttu-id="7daec-301">Проверка подлинности на основе маркеров для веб-API.</span><span class="sxs-lookup"><span data-stu-id="7daec-301">Token-based authentication for Web APIs.</span></span>

> ### <a name="references--security"></a><span data-ttu-id="7daec-302">Ссылки — безопасность</span><span class="sxs-lookup"><span data-stu-id="7daec-302">References – Security</span></span>
> - <span data-ttu-id="7daec-303">**Обзор документации по безопасности**</span><span class="sxs-lookup"><span data-stu-id="7daec-303">**Security Docs Overview**</span></span>  
> https://docs.microsoft.com/aspnet/core/security/
> - <span data-ttu-id="7daec-304">**Принудительное применение протокола SSL в приложениях ASP.NET Core**</span><span class="sxs-lookup"><span data-stu-id="7daec-304">**Enforcing SSL in an ASP.NET Core App**</span></span>  
> <https://docs.microsoft.com/aspnet/core/security/enforcing-ssl>
> - <span data-ttu-id="7daec-305">**Общие сведения об Identity**</span><span class="sxs-lookup"><span data-stu-id="7daec-305">**Introduction to Identity**</span></span>  
> <https://docs.microsoft.com/aspnet/core/security/authentication/identity>
> - <span data-ttu-id="7daec-306">**Общие сведения об авторизации**</span><span class="sxs-lookup"><span data-stu-id="7daec-306">**Introduction to Authorization**</span></span>  
> <https://docs.microsoft.com/aspnet/core/security/authorization/introduction>
> - <span data-ttu-id="7daec-307">**Проверка подлинности и авторизация для приложений API в службах приложений Azure**</span><span class="sxs-lookup"><span data-stu-id="7daec-307">**Authentication and Authorization for API Apps in Azure App Service**</span></span>  
> <https://docs.microsoft.com/azure/app-service-api/app-service-api-authentication>

## <a name="client-communication"></a><span data-ttu-id="7daec-308">Взаимодействие с клиентом</span><span class="sxs-lookup"><span data-stu-id="7daec-308">Client Communication</span></span>

<span data-ttu-id="7daec-309">Помимо обслуживания страниц и ответа на запросы данных через веб-API, приложения ASP.NET Core могут напрямую взаимодействовать с подключенными клиентами.</span><span class="sxs-lookup"><span data-stu-id="7daec-309">In addition to serving pages and responding to requests for data via web APIs, ASP.NET Core apps can communicate directly with connected clients.</span></span> <span data-ttu-id="7daec-310">Для исходящего обмена данными в этом случае могут использоваться самые разные транспортные технологии, однако самое широкое распространение получила технология WebSockets.</span><span class="sxs-lookup"><span data-stu-id="7daec-310">This outbound communication can use a variety of transport technologies, the most common being WebSockets.</span></span> <span data-ttu-id="7daec-311">Библиотека ASP.NET Core SignalR упрощает реализацию функций взаимодействия между клиентом и сервером в реальном времени в вашем приложении.</span><span class="sxs-lookup"><span data-stu-id="7daec-311">ASP.NET Core SignalR is a library that makes it simple to add real-time server-to-client communication functionality to your applications.</span></span> <span data-ttu-id="7daec-312">SignalR поддерживает широкий спектр транспортных технологий, в том числе WebSockets, и абстрагирует многие детали реализации, освобождая от этого труда разработчика.</span><span class="sxs-lookup"><span data-stu-id="7daec-312">SignalR supports a variety of transport technologies, including WebSockets, and abstracts away many of the implementation details from the developer.</span></span>

<span data-ttu-id="7daec-313">Библиотека ASP.NET Core SignalR на данный момент находится на стадии разработки и будет представлена в следующем выпуске ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7daec-313">ASP.NET Core SignalR is currently under development, and will be available in the next release of ASP.NET Core.</span></span> <span data-ttu-id="7daec-314">При необходимости вы можете использовать другие доступные на данный момент [библиотеки WebSockets с открытым исходным кодом](https://github.com/radu-matei/websocket-manager).</span><span class="sxs-lookup"><span data-stu-id="7daec-314">However, other [open source WebSockets libraries](https://github.com/radu-matei/websocket-manager) are currently available.</span></span>

<span data-ttu-id="7daec-315">Взаимодействие с клиентом в реальном времени с использованием WebSockets или других технологий применяется в самых разных сценариях.</span><span class="sxs-lookup"><span data-stu-id="7daec-315">Real-time client communication, whether using WebSockets directly or other techniques, are useful in a variety of application scenarios.</span></span> <span data-ttu-id="7daec-316">Ниже приведены некоторые примеры таких ситуаций.</span><span class="sxs-lookup"><span data-stu-id="7daec-316">Some examples include:</span></span>

-   <span data-ttu-id="7daec-317">Приложения комнаты чата в реальном времени</span><span class="sxs-lookup"><span data-stu-id="7daec-317">Live chat room applications</span></span>

-   <span data-ttu-id="7daec-318">Приложения мониторинга</span><span class="sxs-lookup"><span data-stu-id="7daec-318">Monitoring applications</span></span>

-   <span data-ttu-id="7daec-319">Обновления хода выполнения заданий</span><span class="sxs-lookup"><span data-stu-id="7daec-319">Job progress updates</span></span>

-   <span data-ttu-id="7daec-320">Уведомления</span><span class="sxs-lookup"><span data-stu-id="7daec-320">Notifications</span></span>

-   <span data-ttu-id="7daec-321">Приложения интерактивных форм</span><span class="sxs-lookup"><span data-stu-id="7daec-321">Interactive forms applications</span></span>

<span data-ttu-id="7daec-322">При реализации взаимодействия с клиентом в приложениях обычно используются два компонента:</span><span class="sxs-lookup"><span data-stu-id="7daec-322">When building client communication into your applications, there are typically two components:</span></span>

-   <span data-ttu-id="7daec-323">Диспетчер подключений на стороне сервера (SignalR Hub, WebSocketManager WebSocketHandler)</span><span class="sxs-lookup"><span data-stu-id="7daec-323">Server-side connection manager (SignalR Hub, WebSocketManager WebSocketHandler)</span></span>

-   <span data-ttu-id="7daec-324">Библиотека на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="7daec-324">Client-side library</span></span>

<span data-ttu-id="7daec-325">В качестве клиентов могут выступать не только браузеры, но также мобильные, консольные и другие встроенные приложения, которые поддерживают SignalR/WebSockets.</span><span class="sxs-lookup"><span data-stu-id="7daec-325">Clients are not limited to browsers – mobile apps, console apps, and other native apps can also communicate using SignalR/WebSockets.</span></span> <span data-ttu-id="7daec-326">Следующая простая программа, входящая в пример приложения WebSocketManager, выводит на консоль все содержимое, передаваемое в приложение чата:</span><span class="sxs-lookup"><span data-stu-id="7daec-326">The following simple program echoes all content sent to a chat application to the console, as part of a WebSocketManager sample application:</span></span>

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

<span data-ttu-id="7daec-327">Рассмотрите способы обеспечения взаимодействия с клиентом напрямую из приложений и оцените, насколько возможность взаимодействия в реальном времени позволит улучшить ваше приложение.</span><span class="sxs-lookup"><span data-stu-id="7daec-327">Consider ways in which your applications communicate directly with client applications, and consider whether real-time communication would improve your app's user experience.</span></span>

> ### <a name="references--client-communication"></a><span data-ttu-id="7daec-328">Ссылки — взаимодействие с клиентом</span><span class="sxs-lookup"><span data-stu-id="7daec-328">References – Client Communication</span></span>
> - <span data-ttu-id="7daec-329">**Библиотека ASP.NET Core SignalR**</span><span class="sxs-lookup"><span data-stu-id="7daec-329">**ASP.NET Core SignalR**</span></span>  
> <https://github.com/aspnet/SignalR>
> - <span data-ttu-id="7daec-330">**WebSocket Manager**</span><span class="sxs-lookup"><span data-stu-id="7daec-330">**WebSocket Manager**</span></span>  
> https://github.com/radu-matei/websocket-manager

## <a name="domain-driven-design--should-you-apply-it"></a><span data-ttu-id="7daec-331">Следует ли применять проблемно-ориентированное проектирование?</span><span class="sxs-lookup"><span data-stu-id="7daec-331">Domain-Driven Design – Should You Apply It?</span></span>

<span data-ttu-id="7daec-332">Проблемно-ориентированное проектирование предусматривает гибкий подход к разработке программного обеспечения с учетом особенностей *области бизнеса*.</span><span class="sxs-lookup"><span data-stu-id="7daec-332">Domain-Driven Design (DDD) is an agile approach to building software that emphasizes focusing on the *business domain*.</span></span> <span data-ttu-id="7daec-333">При таком подходе особое внимание уделяется взаимодействию с экспертами в конкретных областях бизнеса, которые предоставляют разработчикам информацию о работе систем в реальном мире.</span><span class="sxs-lookup"><span data-stu-id="7daec-333">It places a heavy emphasis on communication and interaction with business domain expert(s) who can relate to the developers how the real-world system works.</span></span> <span data-ttu-id="7daec-334">Например, при разработке системы биржевых торгов вам может потребоваться консультация со стороны эксперта в этой области.</span><span class="sxs-lookup"><span data-stu-id="7daec-334">For example, if you're building a system that handles stock trades, your domain expert might be an experienced stock broker.</span></span> <span data-ttu-id="7daec-335">Проблемно-ориентированное проектирование рассчитано на решение сложных бизнес-проблем и зачастую не подходит для небольших простых приложений, поскольку затраты на понимание и моделирование предметной области попросту не могут окупиться.</span><span class="sxs-lookup"><span data-stu-id="7daec-335">DDD is designed to address large, complex business problems, and is often not appropriate for smaller, simpler applications, as the investment in understanding and modeling the domain is not worth it.</span></span>

<span data-ttu-id="7daec-336">При разработке программного обеспечения с соблюдением принципов проблемно-ориентированного проектирования ваша команда (включая нетехнических специалистов и участников) должна использовать *единый язык* для общего понимания предметной области.</span><span class="sxs-lookup"><span data-stu-id="7daec-336">When building software following a DDD approach, your team (including non-technical stakeholders and contributors) should develop a *ubiquitous language* for the problem space.</span></span> <span data-ttu-id="7daec-337">Это значит, что необходимо использовать единую терминологию для описания моделируемых концепций реального мира, их программных эквивалентов и любых структур, которые могут применяться для сохранения концепций (например, таблиц баз данных).</span><span class="sxs-lookup"><span data-stu-id="7daec-337">That is, the same terminology should be used for the real-world concept being modeled, the software equivalent, and any structures that might exist to persist the concept (for example, database tables).</span></span> <span data-ttu-id="7daec-338">Таким образом, описываемые на едином языке концепции должны стать основой для вашей *модели предметной области*.</span><span class="sxs-lookup"><span data-stu-id="7daec-338">Thus, the concepts described in the ubiquitous language should form the basis for your *domain model*.</span></span>

<span data-ttu-id="7daec-339">Модель предметной области состоит из объектов, которые взаимодействуют друг с другом, моделируя поведения системы.</span><span class="sxs-lookup"><span data-stu-id="7daec-339">Your domain model is comprised of objects that interact with one another to represent the behavior of the system.</span></span> <span data-ttu-id="7daec-340">Эти объекты можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="7daec-340">These objects may fall into the following categories:</span></span>

-   <span data-ttu-id="7daec-341">[Сущности](http://deviq.com/entity/), которые представляют объекты с потоком удостоверений.</span><span class="sxs-lookup"><span data-stu-id="7daec-341">[Entities](http://deviq.com/entity/), which represent objects with a thread of identity.</span></span> <span data-ttu-id="7daec-342">Для сущностей обычно применяется сохраняемость по ключу, по которому они могут быть впоследствии извлечены.</span><span class="sxs-lookup"><span data-stu-id="7daec-342">Entities are typically stored in persistence with a key by which they can later be retrieved.</span></span>

-   <span data-ttu-id="7daec-343">[Агрегаты](http://deviq.com/aggregate-pattern/), представляющие группы объектов, которые должны сохраняться как единое целое.</span><span class="sxs-lookup"><span data-stu-id="7daec-343">[Aggregates](http://deviq.com/aggregate-pattern/), which represent groups of objects that should be persisted as a unit.</span></span>

-   <span data-ttu-id="7daec-344">[Объекты значений](http://deviq.com/value-object/), представляющие концепции, которые могут сравниваться на основании суммы значений их свойств.</span><span class="sxs-lookup"><span data-stu-id="7daec-344">[Value objects](http://deviq.com/value-object/), which represent concepts that can be compared on the basis of the sum of their property values.</span></span> <span data-ttu-id="7daec-345">Например, диапазон дат определяется датами начала и окончания.</span><span class="sxs-lookup"><span data-stu-id="7daec-345">For example, DateRange consisting of a start and end date.</span></span>

-   <span data-ttu-id="7daec-346">[События предметной области](https://martinfowler.com/eaaDev/DomainEvent.html), которые представляют происходящие в системе события, интересующие другие части системы.</span><span class="sxs-lookup"><span data-stu-id="7daec-346">[Domain events](https://martinfowler.com/eaaDev/DomainEvent.html), which represent things happening within the system that are of interest to other parts of the system.</span></span>

<span data-ttu-id="7daec-347">Обратите внимание, что модель предметной области при проблемно-ориентированном проектировании должна инкапсулировать комплексное поведение в рамках модели.</span><span class="sxs-lookup"><span data-stu-id="7daec-347">Note that a DDD domain model should encapsulate complex behavior within the model.</span></span> <span data-ttu-id="7daec-348">В частности, сущности должны представлять собой не просто коллекции свойств.</span><span class="sxs-lookup"><span data-stu-id="7daec-348">Entities, in particular, should not merely be collections of properties.</span></span> <span data-ttu-id="7daec-349">Модель предметной области, которая не определяет поведение и представляет лишь состояние системы, будет [слабой](http://deviq.com/anemic-model/), что при проблемно-ориентированном проектировании крайне нежелательно.</span><span class="sxs-lookup"><span data-stu-id="7daec-349">When the domain model lacks behavior and merely represents the state of the system, it is said to be an [anemic model](http://deviq.com/anemic-model/), which is undesirable in DDD.</span></span>

<span data-ttu-id="7daec-350">Помимо этих типов моделей, при проблемно-ориентированном проектировании применяются другие шаблоны:</span><span class="sxs-lookup"><span data-stu-id="7daec-350">In addition to these model types, DDD typically employs a variety of patterns:</span></span>

-   <span data-ttu-id="7daec-351">[Репозиторий](http://deviq.com/repository-pattern/) обеспечивает абстрагирование сведений о сохраняемости.</span><span class="sxs-lookup"><span data-stu-id="7daec-351">[Repository](http://deviq.com/repository-pattern/), for abstracting persistence details.</span></span>

-   <span data-ttu-id="7daec-352">[Фабрика](https://en.wikipedia.org/wiki/Factory_method_pattern) служит для инкапсуляции создания сложных объектов.</span><span class="sxs-lookup"><span data-stu-id="7daec-352">[Factory](https://en.wikipedia.org/wiki/Factory_method_pattern), for encapsulating complex object creation.</span></span>

-   <span data-ttu-id="7daec-353">События домена позволяют отделить зависимое поведение от инициирующих его действий и событий.</span><span class="sxs-lookup"><span data-stu-id="7daec-353">Domain events, for decoupling dependent behavior from triggering behavior.</span></span>

-   <span data-ttu-id="7daec-354">[Службы](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/) инкапсулируют сложное поведение и (или) детали реализации инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="7daec-354">[Services](http://gorodinski.com/blog/2012/04/14/services-in-domain-driven-design-ddd/), for encapsulating complex behavior and/or infrastructure implementation details.</span></span>

-   <span data-ttu-id="7daec-355">[Команда](https://en.wikipedia.org/wiki/Command_pattern) обеспечивает разделение выдачи и выполнения команд.</span><span class="sxs-lookup"><span data-stu-id="7daec-355">[Command](https://en.wikipedia.org/wiki/Command_pattern), for decoupling issuing commands and executing the command itself.</span></span>

-   <span data-ttu-id="7daec-356">[Спецификация](http://deviq.com/specification-pattern/) инкапсулирует детали запроса.</span><span class="sxs-lookup"><span data-stu-id="7daec-356">[Specification](http://deviq.com/specification-pattern/), for encapsulating query details.</span></span>

<span data-ttu-id="7daec-357">При проблемно-ориентированном проектировании также рекомендуется применять ранее описываемую чистую архитектуру, благодаря которой обеспечиваются слабая связанность, инкапсуляция и простота проверки кода с использованием модульных тестов.</span><span class="sxs-lookup"><span data-stu-id="7daec-357">DDD also recommends the use of the Clean Architecture discussed previously, allowing for loose coupling, encapsulation, and code that can easily be verified using unit tests.</span></span>

### <a name="when-should-you-apply-ddd"></a><span data-ttu-id="7daec-358">В каких случаях следует применять проблемно-ориентированное проектирование</span><span class="sxs-lookup"><span data-stu-id="7daec-358">When Should You Apply DDD</span></span>

<span data-ttu-id="7daec-359">Проблемно-ориентированное проектирование оптимально подходит для крупных приложений, разработка которых связана с решением как серьезных технических трудностей, так и сложных бизнес-задач.</span><span class="sxs-lookup"><span data-stu-id="7daec-359">DDD is well-suited to large applications with significant business (not just technical) complexity.</span></span> <span data-ttu-id="7daec-360">В таких сценариях при разработке приложения требуются знания экспертов в предметной области.</span><span class="sxs-lookup"><span data-stu-id="7daec-360">The application should require the knowledge of domain experts.</span></span> <span data-ttu-id="7daec-361">При этом требуется значительный объем работы над поведением в самой модели предметной области, что позволяет представить бизнес-правила и взаимодействия в дополнение к возможностям хранения и извлечения текущего состояния различных записей с применением хранилищ данных.</span><span class="sxs-lookup"><span data-stu-id="7daec-361">There should be significant behavior in the domain model itself, representing business rules and interactions beyond simply storing and retrieving the current state of various records from data stores.</span></span>

### <a name="when-shouldnt-you-apply-ddd"></a><span data-ttu-id="7daec-362">В каких случаях не следует применять проблемно-ориентированное проектирование</span><span class="sxs-lookup"><span data-stu-id="7daec-362">When Shouldn't You Apply DDD</span></span>

<span data-ttu-id="7daec-363">Проблемно-ориентированное проектирование предусматривает инвестиции в моделирование, разработку архитектуры и взаимодействия, которые могут быть необоснованно велики для небольших приложений или решений, предназначенных только для создания, чтения, обновления и удаления данных.</span><span class="sxs-lookup"><span data-stu-id="7daec-363">DDD involves investments in modeling, architecture, and communication that may not be warranted for smaller applications or applications that are essentially just CRUD (create/read/update/delete).</span></span> <span data-ttu-id="7daec-364">Если вы выбрали этот вариант, но при этом обнаружили слабость модели предметной области (то есть отсутствие поведения), возможно, следует пересмотреть выбранный подход.</span><span class="sxs-lookup"><span data-stu-id="7daec-364">If you choose to approach your application following DDD, but find that your domain has an anemic model with no behavior, you may need to rethink your approach.</span></span> <span data-ttu-id="7daec-365">Возможно, в таком случае для вашего приложения не требуется применять проблемно-ориентированное проектирование либо вам может потребоваться помощь в рефакторинге приложения с тем, чтобы инкапсулировать бизнес-логику в модели предметной области, а не в базе данных или пользовательском интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="7daec-365">Either your application may not need DDD, or you may need assistance refactoring your application to encapsulate business logic in the domain model, rather than in your database or user interface.</span></span>

<span data-ttu-id="7daec-366">Возможен гибридный подход, при котором проблемно-ориентированное проектирование применяется только в отношении транзакционных или более сложных частей приложения, а не для реализации простых функций создания, чтения, обновления и удаления данных.</span><span class="sxs-lookup"><span data-stu-id="7daec-366">A hybrid approach would be to only use DDD for the transactional or more complex areas of the application, but not for simpler CRUD or read-only portions of the application.</span></span> <span data-ttu-id="7daec-367">Например, если вы запрашиваете данные для вывода отчета или визуализации данных в панели мониторинга, вам не нужны ограничения агрегата.</span><span class="sxs-lookup"><span data-stu-id="7daec-367">For instance, you needn't have the constraints of an Aggregate if you're querying data to display a report or to visualize data for a dashboard.</span></span> <span data-ttu-id="7daec-368">В этом случае вполне подойдет использование более простой модели чтения.</span><span class="sxs-lookup"><span data-stu-id="7daec-368">It's perfectly acceptable to have a separate, simpler read model for such requirements.</span></span>

> ### <a name="references--domain-driven-design"></a><span data-ttu-id="7daec-369">Ссылки — проблемно-ориентированное проектирование</span><span class="sxs-lookup"><span data-stu-id="7daec-369">References – Domain-Driven Design</span></span>
> - <span data-ttu-id="7daec-370">**Проблемно-ориентированное проектирование простыми словами (ответ с веб-сайта StackOverflow)**</span><span class="sxs-lookup"><span data-stu-id="7daec-370">**DDD in Plain English (StackOverflow Answer)**</span></span>  
> <https://stackoverflow.com/questions/1222392/can-someone-explain-domain-driven-design-ddd-in-plain-english-please/1222488#1222488>

## <a name="deployment"></a><span data-ttu-id="7daec-371">Развертывание</span><span class="sxs-lookup"><span data-stu-id="7daec-371">Deployment</span></span>

<span data-ttu-id="7daec-372">Независимо от того, где будет размещено ваше приложение ASP.NET Core, процесс его развертывания будет состоять из нескольких шагов.</span><span class="sxs-lookup"><span data-stu-id="7daec-372">There are a few steps involved in the process of deploying your ASP.NET Core application, regardless of where it will be hosted.</span></span> <span data-ttu-id="7daec-373">В первую очередь выполняется публикация приложения, например с помощью команды dotnet publish интерфейса командной строки.</span><span class="sxs-lookup"><span data-stu-id="7daec-373">The first step is to publish the application, which can be done using the dotnet publish CLI command.</span></span> <span data-ttu-id="7daec-374">На этом этапе приложение компилируется, а все необходимые для его работы файлы помещаются в указанную папку.</span><span class="sxs-lookup"><span data-stu-id="7daec-374">This will compile the application and place all of the files needed to run the application into a designated folder.</span></span> <span data-ttu-id="7daec-375">При развертывании из Visual Studio эти действия выполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="7daec-375">When you deploy from Visual Studio, this step is performed for you automatically.</span></span> <span data-ttu-id="7daec-376">В папке публикации содержатся EXE- и DLL-файлы приложения, а также его зависимости.</span><span class="sxs-lookup"><span data-stu-id="7daec-376">The publish folder contains .exe and .dll files for the application and its dependencies.</span></span> <span data-ttu-id="7daec-377">Автономное приложение также будет включать версию среды выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="7daec-377">A self-contained application will also include a version of the .NET runtime.</span></span> <span data-ttu-id="7daec-378">Приложения ASP.NET Core также включают файлы конфигурации, статические ресурсы клиента и представления MVC.</span><span class="sxs-lookup"><span data-stu-id="7daec-378">ASP.NET Core applications will also include configuration files, static client assets, and MVC views.</span></span>

<span data-ttu-id="7daec-379">Приложения ASP.NET Core являются консольными приложениями и должны запускаться при загрузке или перезагрузке сервера в случае сбоя приложения (или сервера).</span><span class="sxs-lookup"><span data-stu-id="7daec-379">ASP.NET Core applications are console applications that must be started when the server boots and restarted if the application (or server) crashes.</span></span> <span data-ttu-id="7daec-380">Для автоматизации этого процесса может использоваться диспетчер процессов.</span><span class="sxs-lookup"><span data-stu-id="7daec-380">A process manager can be used to automate this process.</span></span> <span data-ttu-id="7daec-381">Чаще всего для ASP.NET Core используются такие диспетчеры запросов, как Nginx и Apache в Linux, а также IIS или Windows Service в Windows.</span><span class="sxs-lookup"><span data-stu-id="7daec-381">The most common process managers for ASP.NET Core are Nginx and Apache on Linux and IIS or Windows Service on Windows.</span></span>

<span data-ttu-id="7daec-382">Помимо диспетчера процессов, приложения ASP.NET Core, размещаемые на веб-сервере Kestrel, должны использовать обратный прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="7daec-382">In addition to a process manager, ASP.NET Core applications hosted in the Kestrel web server must use a reverse proxy server.</span></span> <span data-ttu-id="7daec-383">Обратный прокси-сервер получает HTTP-запросы из Интернета и пересылает их в Kestrel после определенной предварительной обработки.</span><span class="sxs-lookup"><span data-stu-id="7daec-383">A reverse proxy server receives HTTP requests from the internet and forwards them to Kestrel after some preliminary handling.</span></span> <span data-ttu-id="7daec-384">Обратный прокси-сервер реализует слой безопасности приложения и необходим для пограничных развертываний (открытых для трафика из Интернета).</span><span class="sxs-lookup"><span data-stu-id="7daec-384">Reverse proxy servers provide a layer of security for the application, and are required for edge deployments (exposed to traffic from the Internet).</span></span> <span data-ttu-id="7daec-385">Решение Kestrel является относительно новым и на данный момент не обеспечивает защиту от определенных видов атак.</span><span class="sxs-lookup"><span data-stu-id="7daec-385">Kestrel is relatively new and does not yet offer defenses against certain attacks.</span></span> <span data-ttu-id="7daec-386">Кроме того, Kestrel не поддерживает размещение нескольких приложений на одном порту и по одному IP-адресу, поэтому такие сценарии нельзя использовать заголовки узла и другие подобные технологии.</span><span class="sxs-lookup"><span data-stu-id="7daec-386">Kestrel also doesn't support hosting multiple applications on the same port, so techniques like host headers cannot be used with it to enable hosting multiple applications on the same port and IP address.</span></span>

![Kestrel для Интернета](./media/image7-5.png)

<span data-ttu-id="7daec-388">Рис. 7-5. Приложение ASP.NET, размещенное на сервере Kestrel позади обратного прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="7daec-388">Figure 7-5 ASP.NET hosted in Kestrel behind a reverse proxy server</span></span>

<span data-ttu-id="7daec-389">Кроме того, обратный прокси-сервер может применяться для защиты нескольких приложений с использованием протокола SSL/HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7daec-389">Another scenario in which a reverse proxy can be helpful is to secure multiple applications using SSL/HTTPS.</span></span> <span data-ttu-id="7daec-390">В этом случае настраивать SSL необходимо только на обратном прокси-сервере.</span><span class="sxs-lookup"><span data-stu-id="7daec-390">In this case, only the reverse proxy would need to have SSL configured.</span></span> <span data-ttu-id="7daec-391">Взаимодействие между обратным прокси-сервером и Kestrel может осуществляться по протоколу HTTP, как показано на рис. 7-6.</span><span class="sxs-lookup"><span data-stu-id="7daec-391">Communication between the reverse proxy server and Kestrel could take place over HTTP, as shown in Figure 7-6.</span></span>

![](./media/image7-6.png)

<span data-ttu-id="7daec-392">Рис. 7-6. Приложение ASP.NET, размещенное позади обратного прокси-сервера, защищенного с помощью протокола HTTPS</span><span class="sxs-lookup"><span data-stu-id="7daec-392">Figure 7-6 ASP.NET hosted behind an HTTPS-secured reverse proxy server</span></span>

<span data-ttu-id="7daec-393">Также набирает популярность подход с размещением приложений ASP.NET Core в контейнере Docker, который, в свою очередь, может размещаться локально или развертываться в облачной среде Azure.</span><span class="sxs-lookup"><span data-stu-id="7daec-393">An increasingly popular approach is to host your ASP.NET Core application in a Docker container, which then can be hosted locally or deployed to Azure for cloud-based hosting.</span></span> <span data-ttu-id="7daec-394">Контейнер Docker может содержать код приложения и выполняться на сервере Kestrel (в этом случае необходимо развертывание позади обратного прокси-сервера, как показано выше).</span><span class="sxs-lookup"><span data-stu-id="7daec-394">The Docker container could contain your application code, running on Kestrel, and would be deployed behind a reverse proxy server, as shown above.</span></span>

<span data-ttu-id="7daec-395">Если вы размещаете приложение в Azure, можно использовать шлюз приложений Microsoft Azure в качестве выделенного виртуального устройства для предоставления определенных служб.</span><span class="sxs-lookup"><span data-stu-id="7daec-395">If you're hosting your application on Azure, you can use Microsoft Azure Application Gateway as a dedicated virtual appliance to provide several services.</span></span> <span data-ttu-id="7daec-396">Шлюз приложений не только выступает в качестве обратного прокси-сервера для отдельных приложений, но и реализует следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="7daec-396">In addition to acting as a reverse proxy for individual applications, Application Gateway can also offer the following features:</span></span>

-   <span data-ttu-id="7daec-397">Балансировка нагрузки HTTP</span><span class="sxs-lookup"><span data-stu-id="7daec-397">HTTP load balancing</span></span>

-   <span data-ttu-id="7daec-398">Разгрузка SSL (SSL только для Интернета)</span><span class="sxs-lookup"><span data-stu-id="7daec-398">SSL offload (SSL only to Internet)</span></span>

-   <span data-ttu-id="7daec-399">Сквозное шифрование SSL</span><span class="sxs-lookup"><span data-stu-id="7daec-399">End to End SSL</span></span>

-   <span data-ttu-id="7daec-400">Распределенная маршрутизация (консолидация до 20 сайтов на одном шлюзе приложений)</span><span class="sxs-lookup"><span data-stu-id="7daec-400">Multi-site routing (consolidate up to 20 sites on a single Application Gateway)</span></span>

-   <span data-ttu-id="7daec-401">Брандмауэр веб-приложения</span><span class="sxs-lookup"><span data-stu-id="7daec-401">Web application firewall</span></span>

-   <span data-ttu-id="7daec-402">Поддержка WebSocket</span><span class="sxs-lookup"><span data-stu-id="7daec-402">Websocket support</span></span>

-   <span data-ttu-id="7daec-403">Расширенная диагностика</span><span class="sxs-lookup"><span data-stu-id="7daec-403">Advanced diagnostics</span></span>

<span data-ttu-id="7daec-404">*Дополнительные сведения о вариантах развертывания Azure см. в главе 10.*</span><span class="sxs-lookup"><span data-stu-id="7daec-404">*Learn more about Azure deployment options in Chapter 10.*</span></span>

> ### <a name="references--deployment"></a><span data-ttu-id="7daec-405">Ссылки — развертывание</span><span class="sxs-lookup"><span data-stu-id="7daec-405">References – Deployment</span></span>
> - <span data-ttu-id="7daec-406">**Общие сведения о размещении и развертывании**</span><span class="sxs-lookup"><span data-stu-id="7daec-406">**Hosting and Deployment Overview**</span></span>  
> <https://docs.microsoft.com/aspnet/core/publishing/>
> - <span data-ttu-id="7daec-407">**Условия использования Kestrel с обратным прокси-сервером**</span><span class="sxs-lookup"><span data-stu-id="7daec-407">**When to use Kestrel with a reverse proxy**</span></span>  
> <https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel#when-to-use-kestrel-with-a-reverse-proxy>
> - <span data-ttu-id="7daec-408">**Размещение приложений ASP.NET Core в контейнерах Docker**</span><span class="sxs-lookup"><span data-stu-id="7daec-408">**Host ASP.NET Core apps in Docker**</span></span>  
> <https://docs.microsoft.com/aspnet/core/publishing/docker>
> - <span data-ttu-id="7daec-409">**Общие сведения о шлюзе приложений Azure**</span><span class="sxs-lookup"><span data-stu-id="7daec-409">**Introducing Azure Application Gateway**</span></span>  
> <https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction>

>[!div class="step-by-step"]
<span data-ttu-id="7daec-410">[Назад](common-client-side-web-technologies.md)
[Вперед](work-with-data-in-asp-net-core-apps.md)</span><span class="sxs-lookup"><span data-stu-id="7daec-410">[Previous](common-client-side-web-technologies.md)
[Next](work-with-data-in-asp-net-core-apps.md)</span></span>
