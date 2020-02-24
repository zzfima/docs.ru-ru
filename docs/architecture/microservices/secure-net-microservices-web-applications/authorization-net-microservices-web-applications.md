---
title: Об авторизации в веб-приложениях и микрослужбах .NET
description: Безопасность в микрослужбах .NET и веб-приложениях. Ознакомьтесь с общими сведениями о параметрах авторизации на основе ролей и на основе политик в приложениях ASP.NET Core.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: f6b69faceac9a9b4819212cc04f89080f3ddad56
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501769"
---
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Об авторизации в веб-приложениях и микрослужбах .NET

После проверки подлинности веб-API ASP.NET Core должны авторизовать доступ. Этот процесс позволяет службе предоставлять API только избранным пользователям. [Авторизация](/aspnet/core/security/authorization/introduction) может осуществляться на базе ролей пользователя или пользовательской политики, которая может включать требования к проверке или другую эвристику.

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

## <a name="implement-role-based-authorization"></a>Реализация авторизации на основе ролей

ASP.NET Core Identity имеет встроенную концепцию ролей. ASP.NET Core Identity хранит сведения не только о пользователях, но и о ролях, используемых приложением, а также отслеживает присвоенные пользователям роли. Эти назначения можно изменить программными средствами с использованием типа `RoleManager`, который позволяет обновить роли в постоянном хранилище, и типа `UserManager`, который позволяет предоставить роли пользователям или отозвать их.

Если вы выполняете проверку подлинности с токенами носителя JWT, ПО промежуточного слоя ASP.NET Core JWT для проверки подлинности носителя запишет данные о ролях пользователя на основе утверждений роли из токена. Чтобы предоставить доступ к контролеру или действию MVC только пользователям с определенными ролями, включите параметр Roles в аннотацию Authorize, как показано в следующем фрагменте кода:

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

- иметь роль Administrator *или* PowerUser *и*

- Иметь роль RemoteEmployee, *и*

- Удовлетворять условиям пользовательского обработчика для авторизации в соответствии с политикой CustomPolicy.

## <a name="implement-policy-based-authorization"></a>Реализация авторизации на основе политик

Пользовательские правила авторизации могут быть записаны в виде [политик авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html). В этом разделе приводятся общие сведения. Дополнительные сведения см. в документации [семинара по авторизации ASP.NET Core](https://github.com/blowdart/AspNetAuthorizationWorkshop).

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

Как показано в примере, политики могут быть связаны с разными типами требований. После регистрации политики можно применять к действию или контроллеру, передавая имя политики в виде аргумента Policy в атрибуте Authorize (например, `[Authorize(Policy="EmployeesOnly")]`). У политик может быть сразу несколько требований (как показано в этих примерах).

В предыдущем примере первый вызов AddPolicy просто является альтернативным способом авторизации по ролям. Если применить `[Authorize(Policy="AdministratorsOnly")]` к API, доступ будут иметь только пользователи в роли Administrator.

Второй вызов <xref:Microsoft.AspNetCore.Authorization.AuthorizationOptions.AddPolicy%2A> демонстрирует простой способ потребовать определенное утверждение для пользователя. Метод <xref:Microsoft.AspNetCore.Authorization.AuthorizationPolicyBuilder.RequireClaim%2A> также может принимать ожидаемые значения в качестве утверждения. Если значения указаны, требование удовлетворяется только в том случае, если пользователь одновременно имеет утверждение верного типа и одно из указанных значений. Если вы используете ПО промежуточного слоя для проверки подлинности носителей JWT, все свойства JWT будут доступны как утверждения пользователя.

Самая интересная политика показана в третьем методе `AddPolicy`, так как применяется пользовательское требование к авторизации. Используя пользовательские требования к авторизации, вы можете строго контролировать выполнение авторизации. Для этого необходимо реализовать следующие типы:

- Тип Requirements, который является производным от <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement> и содержит поля с указанием сведений о требовании. В примере это поле возраста с типом `MinimumAgeRequirement`.

- Обработчик, применяющий <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601>, где T — это тип требования <xref:Microsoft.AspNetCore.Authorization.IAuthorizationRequirement>, которое должен выполнить обработчик. Обработчик должен применить метод <xref:Microsoft.AspNetCore.Authorization.AuthorizationHandler%601.HandleRequirementAsync%2A>, который проверяет, удовлетворяет ли требованию заданный контекст, содержащий сведения о пользователе.

Если пользователь отвечает требованиям, вызов к `context.Succeed` будет указывать на авторизацию пользователя. Если пользователь может выполнить требования к авторизации несколькими способами, можно создать несколько обработчиков.

Вдобавок к регистрации пользовательских требований политики с вызовами `AddPolicy` вам также необходимо зарегистрировать обработчики пользовательских требований, внедрив зависимости (`services.AddTransient<IAuthorizationHandler, MinimumAgeHandler>()`).

Пример пользовательских требований к авторизации и обработчика для проверки возраста пользователя (на основе утверждения `DateOfBirth`) приводится в [документации по авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html) для ASP.NET Core.

## <a name="additional-resources"></a>Дополнительные ресурсы

- **Проверка подлинности в ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **Авторизация в ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/introduction](/aspnet/core/security/authorization/introduction)

- **Авторизация на основе ролей** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/roles](/aspnet/core/security/authorization/roles)

- **Пользовательская авторизация на основе политик** \
  [https://docs.microsoft.com/aspnet/core/security/authorization/policies](/aspnet/core/security/authorization/policies)

>[!div class="step-by-step"]
>[Назад](index.md)
>[Вперед](developer-app-secrets-storage.md)
