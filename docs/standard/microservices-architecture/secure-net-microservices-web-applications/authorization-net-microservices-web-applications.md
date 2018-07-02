---
title: Об авторизации в веб-приложениях и микрослужбах .NET
description: Архитектура микрослужб .NET для упакованных в контейнеры приложений .NET | Об авторизации в веб-приложениях и микрослужбах .NET
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 7b2981579f28c083a31d7af6ae42f4e3ca8bbd88
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105505"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a><span data-ttu-id="48ef7-103">Об авторизации в веб-приложениях и микрослужбах .NET</span><span class="sxs-lookup"><span data-stu-id="48ef7-103">About authorization in .NET microservices and web applications</span></span>

<span data-ttu-id="48ef7-104">После проверки подлинности веб-API ASP.NET Core должны авторизовать доступ.</span><span class="sxs-lookup"><span data-stu-id="48ef7-104">After authentication, ASP.NET Core Web APIs need to authorize access.</span></span> <span data-ttu-id="48ef7-105">Этот процесс позволяет службе предоставлять API только избранным пользователям.</span><span class="sxs-lookup"><span data-stu-id="48ef7-105">This process allows a service to make APIs available to some authenticated users, but not to all.</span></span> <span data-ttu-id="48ef7-106">[Авторизация](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) может осуществляться на базе ролей пользователя или пользовательской политики, которая может включать требования к проверке или другую эвристику.</span><span class="sxs-lookup"><span data-stu-id="48ef7-106">[Authorization](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) can be done based on users’ roles or based on custom policy, which might include inspecting claims or other heuristics.</span></span>

<span data-ttu-id="48ef7-107">Чтобы ограничить доступ к маршруту ASP.NET Core MVC, достаточно просто применить атрибут Authorize к методу действия (или классу контроллера, если все действия контроллера требуют авторизации). Это показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="48ef7-107">Restricting access to an ASP.NET Core MVC route is as easy as applying an Authorize attribute to the action method (or to the controller’s class if all the controller’s actions require authorization), as shown in following example:</span></span>

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

<span data-ttu-id="48ef7-108">По умолчанию при добавлении атрибута Authorize без параметров доступ к контроллеру или действию будет открыт только пользователям, прошедшим проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="48ef7-108">By default, adding an Authorize attribute without parameters will limit access to authenticated users for that controller or action.</span></span> <span data-ttu-id="48ef7-109">Если вы хотите предоставлять доступ к API более ограниченной группе пользователей, этот атрибут можно дополнить, указав определенные роли или правила.</span><span class="sxs-lookup"><span data-stu-id="48ef7-109">To further restrict an API to be available for only specific users, the attribute can be expanded to specify required roles or policies that users must satisfy.</span></span>

## <a name="implementing-role-based-authorization"></a><span data-ttu-id="48ef7-110">Авторизация на основе ролей</span><span class="sxs-lookup"><span data-stu-id="48ef7-110">Implementing role-based authorization</span></span>

<span data-ttu-id="48ef7-111">ASP.NET Core Identity имеет встроенную концепцию ролей.</span><span class="sxs-lookup"><span data-stu-id="48ef7-111">ASP.NET Core Identity has a built-in concept of roles.</span></span> <span data-ttu-id="48ef7-112">ASP.NET Core Identity хранит сведения не только о пользователях, но и о ролях, используемых приложением, а также отслеживает присвоенные пользователям роли.</span><span class="sxs-lookup"><span data-stu-id="48ef7-112">In addition to users, ASP.NET Core Identity stores information about different roles used by the application and keeps track of which users are assigned to which roles.</span></span> <span data-ttu-id="48ef7-113">Изменить роли можно программно, используя тип RoleManager (который обновляет роли в постоянном хранилище) и тип UserManager (который может присваивать пользователям роли или отменять присвоение).</span><span class="sxs-lookup"><span data-stu-id="48ef7-113">These assignments can be changed programmatically with the RoleManager type (which updates roles in persisted storage) and UserManager type (which can assign or unassign users from roles).</span></span>

<span data-ttu-id="48ef7-114">Если вы выполняете проверку подлинности с токенами носителя JWT, ПО промежуточного слоя ASP.NET Core JWT для проверки подлинности носителя запишет данные о ролях пользователя на основе утверждения на роль из токена.</span><span class="sxs-lookup"><span data-stu-id="48ef7-114">If you are authenticating with JWT bearer tokens, the ASP.NET Core JWT bearer authentication middleware will populate a user’s roles based on role claims found in the token.</span></span> <span data-ttu-id="48ef7-115">Чтобы предоставить доступ к контролеру или действию MVC только пользователям с определенными ролями, включите параметр Roles в заголовок Authorize, как показано в примере:</span><span class="sxs-lookup"><span data-stu-id="48ef7-115">To limit access to an MVC action or controller to users in specific roles, you can include a Roles parameter in the Authorize header, as shown in the following example:</span></span>

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

<span data-ttu-id="48ef7-116">В этом примере только пользователи в роли Administrator или PowerUser могут получить доступ к API в контроллере панели управления (например, для выполнения действия SetTime).</span><span class="sxs-lookup"><span data-stu-id="48ef7-116">In this example, only users in the Administrator or PowerUser roles can access APIs in the ControlPanel controller (such as executing the SetTime action).</span></span> <span data-ttu-id="48ef7-117">Доступ к API ShutDown будут иметь только пользователи в роли Administrator.</span><span class="sxs-lookup"><span data-stu-id="48ef7-117">The ShutDown API is further restricted to allow access only to users in the Administrator role.</span></span>

<span data-ttu-id="48ef7-118">Если вы хотите, чтобы у пользователя было несколько ролей, используйте несколько атрибутов Authorize, как показано в примере:</span><span class="sxs-lookup"><span data-stu-id="48ef7-118">To require a user be in multiple roles, you use multiple Authorize attributes, as shown in the following example:</span></span>

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

<span data-ttu-id="48ef7-119">В этом примере для вызова API1 пользователь должен:</span><span class="sxs-lookup"><span data-stu-id="48ef7-119">In this example, to call API1, a user must:</span></span>

-   <span data-ttu-id="48ef7-120">Иметь роль Administrator *или* PowerUser *и*</span><span class="sxs-lookup"><span data-stu-id="48ef7-120">Be in the Adminstrator *or* PowerUser role, *and*</span></span>

-   <span data-ttu-id="48ef7-121">Иметь роль RemoteEmployee, *и*</span><span class="sxs-lookup"><span data-stu-id="48ef7-121">Be in the RemoteEmployee role, *and*</span></span>

-   <span data-ttu-id="48ef7-122">Удовлетворять условиям пользовательского обработчика для авторизации в соответствии с политикой CustomPolicy.</span><span class="sxs-lookup"><span data-stu-id="48ef7-122">Satisfy a custom handler for CustomPolicy authorization.</span></span>

## <a name="implementing-policy-based-authorization"></a><span data-ttu-id="48ef7-123">Авторизация на основе политик</span><span class="sxs-lookup"><span data-stu-id="48ef7-123">Implementing policy-based authorization</span></span>

<span data-ttu-id="48ef7-124">Пользовательские правила авторизации могут быть записаны в виде [политик авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html).</span><span class="sxs-lookup"><span data-stu-id="48ef7-124">Custom authorization rules can also be written using [authorization policies](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span> <span data-ttu-id="48ef7-125">В этом разделе вы можете ознакомиться с общими сведениями.</span><span class="sxs-lookup"><span data-stu-id="48ef7-125">In this section we provide an overview.</span></span> <span data-ttu-id="48ef7-126">Более подробная информация доступна на [онлайн-семинаре об авторизации ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span><span class="sxs-lookup"><span data-stu-id="48ef7-126">More detail is available in the online [ASP.NET Authorization Workshop](https://github.com/blowdart/AspNetAuthorizationWorkshop).</span></span>

<span data-ttu-id="48ef7-127">Пользовательские политики авторизации регистрируются в методе Startup.ConfigureServices с помощью метода service.AddAuthorization.</span><span class="sxs-lookup"><span data-stu-id="48ef7-127">Custom authorization policies are registered in the Startup.ConfigureServices method using the service.AddAuthorization method.</span></span> <span data-ttu-id="48ef7-128">Этот метод использует делегат, который настраивает аргумент AuthorizationOptions.</span><span class="sxs-lookup"><span data-stu-id="48ef7-128">This method takes a delegate that configures an AuthorizationOptions argument.</span></span>

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

<span data-ttu-id="48ef7-129">Как показано в примере, политики могут быть связаны с разными типами требований.</span><span class="sxs-lookup"><span data-stu-id="48ef7-129">As shown in the example, policies can be associated with different types of requirements.</span></span> <span data-ttu-id="48ef7-130">После регистрации политики можно применять к действию или контроллеру, передавая имя политики в виде аргумента Policy в атрибуте Authorize (например, \[Authorize(Policy="EmployeesOnly")\]). У политик может быть сразу несколько требований (как показано в этих примерах).</span><span class="sxs-lookup"><span data-stu-id="48ef7-130">After the policies are registered, they can be applied to an action or controller by passing the policy’s name as the Policy argument of the Authorize attribute (for example, \[Authorize(Policy="EmployeesOnly")\]) Policies can have multiple requirements, not just one (as shown in these examples).</span></span>

<span data-ttu-id="48ef7-131">В предыдущем примере первый вызов AddPolicy просто является альтернативным способом авторизации по ролям.</span><span class="sxs-lookup"><span data-stu-id="48ef7-131">In the previous example, the first AddPolicy call is just an alternative way of authorizing by role.</span></span> <span data-ttu-id="48ef7-132">Если применить к API \[Authorize(Policy="AdministratorsOnly")\], доступ будут иметь только пользователи в роли Administrator.</span><span class="sxs-lookup"><span data-stu-id="48ef7-132">If \[Authorize(Policy="AdministratorsOnly")\] is applied to an API, only users in the Administrator role will be able to access it.</span></span>

<span data-ttu-id="48ef7-133">Второй вызов AddPolicy демонстрирует простой способ потребовать определенное утверждение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="48ef7-133">The second AddPolicy call demonstrates an easy way to require that a particular claim should be present for the user.</span></span> <span data-ttu-id="48ef7-134">Метод RequireClaim также может принимать ожидаемые значения в качестве утверждения.</span><span class="sxs-lookup"><span data-stu-id="48ef7-134">The RequireClaim method also optionally takes expected values for the claim.</span></span> <span data-ttu-id="48ef7-135">Если значения указаны, требование удовлетворяется только в том случае, если пользователь одновременно имеет утверждение верного типа и одно из указанных значений.</span><span class="sxs-lookup"><span data-stu-id="48ef7-135">If values are specified, the requirement is met only if the user has both a claim of the correct type and one of the specified values.</span></span> <span data-ttu-id="48ef7-136">Если вы используете ПО промежуточного слоя для проверки подлинности носителей JWT, все свойства JWT будут доступны как утверждения пользователя.</span><span class="sxs-lookup"><span data-stu-id="48ef7-136">If you are using the JWT bearer authentication middleware, all JWT properties will be available as user claims.</span></span>

<span data-ttu-id="48ef7-137">Самая интересная политика показана в третьем методе AddPolicy, поскольку используется пользовательское требование к авторизации.</span><span class="sxs-lookup"><span data-stu-id="48ef7-137">The most interesting policy shown here is in the third AddPolicy method, because it uses a custom authorization requirement.</span></span> <span data-ttu-id="48ef7-138">Используя пользовательские требования к авторизации, вы можете строго контролировать выполнение авторизации.</span><span class="sxs-lookup"><span data-stu-id="48ef7-138">By using custom authorization requirements, you can have a great deal of control over how authorization is performed.</span></span> <span data-ttu-id="48ef7-139">Для этого необходимо реализовать следующие типы:</span><span class="sxs-lookup"><span data-stu-id="48ef7-139">For this to work, you must implement these types:</span></span>

-   <span data-ttu-id="48ef7-140">Тип Requirements, который является производным от IAuthorizationRequirement и содержит поля с указанием сведений о требовании.</span><span class="sxs-lookup"><span data-stu-id="48ef7-140">A Requirements type that derives from IAuthorizationRequirement and that contains fields specifying the details of the requirement.</span></span> <span data-ttu-id="48ef7-141">В примере это поле возраста с типом MinimumAgeRequirement.</span><span class="sxs-lookup"><span data-stu-id="48ef7-141">In the example, this is an age field for the sample MinimumAgeRequirement type.</span></span>

-   <span data-ttu-id="48ef7-142">Обработчик, применяющий AuthorizationHandler&lt;T&gt;, где T — это тип требования IAuthorizationRequirement, которое должен выполнить обработчик.</span><span class="sxs-lookup"><span data-stu-id="48ef7-142">A handler that implements AuthorizationHandler&lt;T&gt;, where T is the type of IAuthorizationRequirement that the handler can satisfy.</span></span> <span data-ttu-id="48ef7-143">Обработчик должен применить метод HandleRequirementAsync, который проверяет, удовлетворяет ли требованию заданный контекст, содержащий сведения о пользователе.</span><span class="sxs-lookup"><span data-stu-id="48ef7-143">The handler must implement the HandleRequirementAsync method, which checks whether a specified context that contains information about the user satisfies the requirement.</span></span>

<span data-ttu-id="48ef7-144">Если пользователь отвечает требованиям, вызов к context.Succeed будет указывать на авторизацию пользователя.</span><span class="sxs-lookup"><span data-stu-id="48ef7-144">If the user meets the requirement, a call to context.Succeed will indicate that the user is authorized.</span></span> <span data-ttu-id="48ef7-145">Если пользователь может выполнить требования к авторизации несколькими способами, можно создать несколько обработчиков.</span><span class="sxs-lookup"><span data-stu-id="48ef7-145">If there are multiple ways that a user might satisfy an authorization requirement, multiple handlers can be created.</span></span>

<span data-ttu-id="48ef7-146">Вдобавок к регистрации пользовательских требований политики с вызовами AddPolicy вам также необходимо зарегистрировать обработчики пользовательских требований через внедрение зависимости (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span><span class="sxs-lookup"><span data-stu-id="48ef7-146">In addition to registering custom policy requirements with AddPolicy calls, you also need to register custom requirement handlers via Dependency Injection (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).</span></span>

<span data-ttu-id="48ef7-147">Пример пользовательских требований к авторизации и обработчику для проверки возраста пользователя (на основе утверждения DateOfBirth) приводится в [документации об авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html) для ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="48ef7-147">An example of a custom authorization requirement and handler for checking a user’s age (based on a DateOfBirth claim) is available in the ASP.NET Core [authorization documentation](https://docs.asp.net/en/latest/security/authorization/policies.html).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48ef7-148">Дополнительные ресурсы</span><span class="sxs-lookup"><span data-stu-id="48ef7-148">Additional resources</span></span>

-   <span data-ttu-id="48ef7-149">**Проверка подлинности в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span><span class="sxs-lookup"><span data-stu-id="48ef7-149">**ASP.NET Core Authentication**
[*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)</span></span>

-   <span data-ttu-id="48ef7-150">**Авторизация в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span><span class="sxs-lookup"><span data-stu-id="48ef7-150">**ASP.NET Core Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)</span></span>

-   <span data-ttu-id="48ef7-151">**Авторизация на основе ролей**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span><span class="sxs-lookup"><span data-stu-id="48ef7-151">**Role based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)</span></span>

-   <span data-ttu-id="48ef7-152">**Пользовательская авторизация на основе политик**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span><span class="sxs-lookup"><span data-stu-id="48ef7-152">**Custom Policy-Based Authorization**
[*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="48ef7-153">[Назад](index.md)
[Вперед](developer-app-secrets-storage.md)</span><span class="sxs-lookup"><span data-stu-id="48ef7-153">[Previous](index.md)
[Next](developer-app-secrets-storage.md)</span></span>
