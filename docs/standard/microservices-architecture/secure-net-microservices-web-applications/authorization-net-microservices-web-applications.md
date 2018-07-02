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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Об авторизации в веб-приложениях и микрослужбах .NET

После проверки подлинности веб-API ASP.NET Core должны авторизовать доступ. Этот процесс позволяет службе предоставлять API только избранным пользователям. [Авторизация](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) может осуществляться на базе ролей пользователя или пользовательской политики, которая может включать требования к проверке или другую эвристику.

Чтобы ограничить доступ к маршруту ASP.NET Core MVC, достаточно просто применить атрибут Authorize к методу действия (или классу контроллера, если все действия контроллера требуют авторизации). Это показано в следующем примере:

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

По умолчанию при добавлении атрибута Authorize без параметров доступ к контроллеру или действию будет открыт только пользователям, прошедшим проверку подлинности. Если вы хотите предоставлять доступ к API более ограниченной группе пользователей, этот атрибут можно дополнить, указав определенные роли или правила.

## <a name="implementing-role-based-authorization"></a>Авторизация на основе ролей

ASP.NET Core Identity имеет встроенную концепцию ролей. ASP.NET Core Identity хранит сведения не только о пользователях, но и о ролях, используемых приложением, а также отслеживает присвоенные пользователям роли. Изменить роли можно программно, используя тип RoleManager (который обновляет роли в постоянном хранилище) и тип UserManager (который может присваивать пользователям роли или отменять присвоение).

Если вы выполняете проверку подлинности с токенами носителя JWT, ПО промежуточного слоя ASP.NET Core JWT для проверки подлинности носителя запишет данные о ролях пользователя на основе утверждения на роль из токена. Чтобы предоставить доступ к контролеру или действию MVC только пользователям с определенными ролями, включите параметр Roles в заголовок Authorize, как показано в примере:

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

В этом примере только пользователи в роли Administrator или PowerUser могут получить доступ к API в контроллере панели управления (например, для выполнения действия SetTime). Доступ к API ShutDown будут иметь только пользователи в роли Administrator.

Если вы хотите, чтобы у пользователя было несколько ролей, используйте несколько атрибутов Authorize, как показано в примере:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

В этом примере для вызова API1 пользователь должен:

-   Иметь роль Administrator *или* PowerUser *и*

-   Иметь роль RemoteEmployee, *и*

-   Удовлетворять условиям пользовательского обработчика для авторизации в соответствии с политикой CustomPolicy.

## <a name="implementing-policy-based-authorization"></a>Авторизация на основе политик

Пользовательские правила авторизации могут быть записаны в виде [политик авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html). В этом разделе вы можете ознакомиться с общими сведениями. Более подробная информация доступна на [онлайн-семинаре об авторизации ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).

Пользовательские политики авторизации регистрируются в методе Startup.ConfigureServices с помощью метода service.AddAuthorization. Этот метод использует делегат, который настраивает аргумент AuthorizationOptions.

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

Как показано в примере, политики могут быть связаны с разными типами требований. После регистрации политики можно применять к действию или контроллеру, передавая имя политики в виде аргумента Policy в атрибуте Authorize (например, \[Authorize(Policy="EmployeesOnly")\]). У политик может быть сразу несколько требований (как показано в этих примерах).

В предыдущем примере первый вызов AddPolicy просто является альтернативным способом авторизации по ролям. Если применить к API \[Authorize(Policy="AdministratorsOnly")\], доступ будут иметь только пользователи в роли Administrator.

Второй вызов AddPolicy демонстрирует простой способ потребовать определенное утверждение для пользователя. Метод RequireClaim также может принимать ожидаемые значения в качестве утверждения. Если значения указаны, требование удовлетворяется только в том случае, если пользователь одновременно имеет утверждение верного типа и одно из указанных значений. Если вы используете ПО промежуточного слоя для проверки подлинности носителей JWT, все свойства JWT будут доступны как утверждения пользователя.

Самая интересная политика показана в третьем методе AddPolicy, поскольку используется пользовательское требование к авторизации. Используя пользовательские требования к авторизации, вы можете строго контролировать выполнение авторизации. Для этого необходимо реализовать следующие типы:

-   Тип Requirements, который является производным от IAuthorizationRequirement и содержит поля с указанием сведений о требовании. В примере это поле возраста с типом MinimumAgeRequirement.

-   Обработчик, применяющий AuthorizationHandler&lt;T&gt;, где T — это тип требования IAuthorizationRequirement, которое должен выполнить обработчик. Обработчик должен применить метод HandleRequirementAsync, который проверяет, удовлетворяет ли требованию заданный контекст, содержащий сведения о пользователе.

Если пользователь отвечает требованиям, вызов к context.Succeed будет указывать на авторизацию пользователя. Если пользователь может выполнить требования к авторизации несколькими способами, можно создать несколько обработчиков.

Вдобавок к регистрации пользовательских требований политики с вызовами AddPolicy вам также необходимо зарегистрировать обработчики пользовательских требований через внедрение зависимости (services.AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).

Пример пользовательских требований к авторизации и обработчику для проверки возраста пользователя (на основе утверждения DateOfBirth) приводится в [документации об авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html) для ASP.NET Core.

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Проверка подлинности в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Авторизация в ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)

-   **Авторизация на основе ролей**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)

-   **Пользовательская авторизация на основе политик**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)




>[!div class="step-by-step"]
[Назад](index.md)
[Вперед](developer-app-secrets-storage.md)
