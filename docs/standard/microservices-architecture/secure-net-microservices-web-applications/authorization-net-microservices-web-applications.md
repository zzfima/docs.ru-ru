---
title: "Об авторизации в .NET микрослужбами и веб-приложений"
description: "Архитектура Микрослужбами .NET для приложений .NET в контейнерах | Об авторизации в .NET микрослужбами и веб-приложений"
keywords: "Docker, микрослужбы, ASP.NET, контейнер"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 51adda4f5bdb28154f17b9a988ee2d887bf1d461
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="72b34-104">Об авторизации в .NET микрослужбами и веб-приложений</span><span class="sxs-lookup"><span data-stu-id="72b34-104">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="72b34-105">После проверки подлинности необходимо авторизовать доступ веб-API ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="72b34-105">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="72b34-106">Этот процесс позволяет службе с API, доступны для некоторых пользователей, прошедших проверку подлинности, но не для всех.</span><span class="sxs-lookup"><span data-stu-id="72b34-106">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="72b34-107">[Авторизация](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) по отдельным ролями пользователей или зависимости от пользовательской политики, которая может включать проверки утверждений или других эвристики.</span><span class="sxs-lookup"><span data-stu-id="72b34-107">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="72b34-108">Ограничение доступа к маршрут ASP.NET Core MVC так же легко, как применение атрибута авторизовать методу действия (или класса контроллера, если действия контроллера, требуют наличия авторизации), как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72b34-108">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

```csharp
public class AccountController : Controller
{
    public ActionResult Login()
    {
    }

    [Authorize]
    public ActionResult Logout()
    {
    }
}
```

<span data-ttu-id="72b34-109">По умолчанию Добавление атрибута авторизовать без параметров ограничивает доступ пользователям, прошедшим проверку для этого контроллера или действия.</span><span class="sxs-lookup"><span data-stu-id="72b34-109">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="72b34-110">Чтобы ограничить API доступен только для определенных пользователей, атрибут можно развернуть, чтобы указать необходимые роли или политики, пользователи должны удовлетворять.</span><span class="sxs-lookup"><span data-stu-id="72b34-110">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="72b34-111">Реализации авторизации на основе ролей</span><span class="sxs-lookup"><span data-stu-id="72b34-111">Implementing role-based authorization</span></span>

<span data-ttu-id="72b34-112">Удостоверение ASP.NET Core имеет встроенные концепция ролей.</span><span class="sxs-lookup"><span data-stu-id="72b34-112">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="72b34-113">В дополнение к пользователям ASP.NET Core удостоверения хранит сведения о различных ролях, используемых приложением и отслеживает пользователей, которым назначены роли, к которым.</span><span class="sxs-lookup"><span data-stu-id="72b34-113">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="72b34-114">Эти назначения можно изменить программным способом с типом RoleManager (которая обновляет роли в постоянное хранилище) и типа UserManager (который можно назначить или отменить назначение пользователей из ролей).</span><span class="sxs-lookup"><span data-stu-id="72b34-114">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="72b34-115">Если вы выполняете проверку подлинности с помощью маркеров JWT носителя, промежуточного по проверки подлинности носителя ASP.NET Core JWT будет заполнять роли пользователя на основе утверждений роли найдено в маркере.</span><span class="sxs-lookup"><span data-stu-id="72b34-115">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="72b34-116">Для ограничения доступа на действие MVC или контроллера для определенных ролей пользователей, можно включить параметр ролей в заголовке авторизации, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72b34-116">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
public class ControlPanelController : Controller
{
    public ActionResult SetTime()
    {
    }

    [Authorize(Roles = "Administrator")]
    public ActionResult ShutDown()
    {
    }
}
```

<span data-ttu-id="72b34-117">В этом примере только пользователей в роли администратора или PowerUser можно получить доступ к API-интерфейсы в контроллере панель управления (например, при выполнении действия SetTime).</span><span class="sxs-lookup"><span data-stu-id="72b34-117">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="72b34-118">Чтобы разрешить доступ только для пользователей в роли администратора ограничивается API завершения работы.</span><span class="sxs-lookup"><span data-stu-id="72b34-118">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="72b34-119">Требуют пользователь быть в несколько ролей, используйте несколько атрибутов Authorize, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="72b34-119">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="72b34-120">В этом примере для вызова API1, пользователь должен:</span><span class="sxs-lookup"><span data-stu-id="72b34-120">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="72b34-121">В администратор *или* роли PowerUser *и*</span><span class="sxs-lookup"><span data-stu-id="72b34-121">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="72b34-122">Входить в роль RemoteEmployee *и*</span><span class="sxs-lookup"><span data-stu-id="72b34-122">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="72b34-123">Удовлетворяет пользовательский обработчик для CustomPolicy авторизации.</span><span class="sxs-lookup"><span data-stu-id="72b34-123">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="72b34-124">Реализация на основе политики авторизации</span><span class="sxs-lookup"><span data-stu-id="72b34-124">Implementing policy-based authorization</span></span>

<span data-ttu-id="72b34-125">Пользовательская авторизация правил, также можно записать с помощью [политики авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="72b34-125">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="72b34-126">В этом разделе приводится обзор.</span><span class="sxs-lookup"><span data-stu-id="72b34-126">In this section we provide an overview.</span></span> <span data-ttu-id="72b34-127">Дополнительные сведения доступны в документации по [цеху авторизации ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="72b34-127">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="72b34-128">Пользовательских политик авторизации, регистрируются в методе Startup.ConfigureServices, с помощью службы. Метод AddAuthorization.</span><span class="sxs-lookup"><span data-stu-id="72b34-128">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="72b34-129">Этот метод принимает делегат, который настраивает AuthorizationOptions аргумента.</span><span class="sxs-lookup"><span data-stu-id="72b34-129">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

```csharp
services.AddAuthorization(options =>
{
    options.AddPolicy("AdministratorsOnly", policy =>
        policy.RequireRole("Administrator"));
    options.AddPolicy("EmployeesOnly", policy =>
        policy.RequireClaim("EmployeeNumber"));
    options.AddPolicy("Over21", policy =>
        policy.Requirements.Add(new MinimumAgeRequirement(21)));
});
```

<span data-ttu-id="72b34-130">Как показано в примере политики могут быть связаны с разными типами требований.</span><span class="sxs-lookup"><span data-stu-id="72b34-130">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="72b34-131">После регистрации политики, которые могут применяться на действие или контроллера, передав имя политики в качестве аргумента атрибута авторизовать политики (например, \[Authorize(Policy="EmployeesOnly")\]) может иметь политики несколько требований, не только одного (как показано в следующих примерах).</span><span class="sxs-lookup"><span data-stu-id="72b34-131">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="72b34-132">В предыдущем примере сначала AddPolicy вызывается только один способ авторизации по ролям.</span><span class="sxs-lookup"><span data-stu-id="72b34-132">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="72b34-133">Если \[Authorize(Policy="AdministratorsOnly")\] применяется к API, только пользователи с ролью администратора смогут получить к нему доступ.</span><span class="sxs-lookup"><span data-stu-id="72b34-133">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="72b34-134">При втором вызове AddPolicy демонстрируется простой способ требует, что определенный утверждения должны присутствовать для пользователя.</span><span class="sxs-lookup"><span data-stu-id="72b34-134">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="72b34-135">Метод RequireClaim также принимает ожидаемые значения для утверждения.</span><span class="sxs-lookup"><span data-stu-id="72b34-135">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="72b34-136">Если указаны значения, это требование выполняется только в том случае, если пользователь имеет неправильный тип утверждения и одно из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="72b34-136">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="72b34-137">При использовании проверки подлинности по промежуточного слоя JWT носителя все свойства JWT будет доступна в качестве утверждения пользователей.</span><span class="sxs-lookup"><span data-stu-id="72b34-137">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="72b34-138">Наиболее интересные политика, показанный здесь находится в третий метод AddPolicy, так как оно использует требование настраиваемой авторизации.</span><span class="sxs-lookup"><span data-stu-id="72b34-138">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="72b34-139">С помощью настраиваемой авторизации требования, может иметь высокую степень контроля над выполнением авторизации.</span><span class="sxs-lookup"><span data-stu-id="72b34-139">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="72b34-140">Чтобы это работало необходимо реализовать следующие типы:</span><span class="sxs-lookup"><span data-stu-id="72b34-140">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="72b34-141">Требования к тип, производный от IAuthorizationRequirement, которая содержит поля, определяющие сведения о требовании.</span><span class="sxs-lookup"><span data-stu-id="72b34-141">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="72b34-142">В примере это поле возраста для типа MinimumAgeRequirement образца.</span><span class="sxs-lookup"><span data-stu-id="72b34-142">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="72b34-143">Обработчик, который реализует AuthorizationHandler&lt;T&gt;, где T — тип IAuthorizationRequirement, который удовлетворяет требованиям обработчик.</span><span class="sxs-lookup"><span data-stu-id="72b34-143">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="72b34-144">Обработчик должен реализовывать метод HandleRequirementAsync, который проверяет, удовлетворяет ли заданный контекст, который содержит сведения о пользователе требование.</span><span class="sxs-lookup"><span data-stu-id="72b34-144">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="72b34-145">Если пользователь отвечает требованиям, вызов контекста. Успешно будет указывать, что пользователь авторизован.</span><span class="sxs-lookup"><span data-stu-id="72b34-145">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="72b34-146">Если существует несколько способов, что пользователь может удовлетворить требования к авторизации, можно создать несколько обработчиков.</span><span class="sxs-lookup"><span data-stu-id="72b34-146">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="72b34-147">Помимо регистрации пользовательской политики требований с вызовами AddPolicy, необходимо также зарегистрировать обработчики пользовательского требования через внедрения зависимостей (службы. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span><span class="sxs-lookup"><span data-stu-id="72b34-147">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="72b34-148">Пример настраиваемой авторизации требование и обработчик для проверки возраста пользователя (с учетом утверждений DateOfBirth) доступен в ASP.NET Core [документации авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="72b34-148">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="72b34-149">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="72b34-149">Additional resources</span></span>

-   <span data-ttu-id="72b34-150">**Проверка подлинности ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="72b34-150">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="72b34-151">**Авторизации ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="72b34-151">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="72b34-152">**Авторизация на основе ролей**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="72b34-152">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="72b34-153">**Пользовательская авторизация на основе политики**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="72b34-153">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="72b34-154">[Предыдущие] (index.md) [Далее] (разработчика app секреты storage.md)</span><span class="sxs-lookup"><span data-stu-id="72b34-154">[Previous] (index.md) [Next] (developer-app-secrets-storage.md)</span></span>
