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
# <a name="about-authorization-in-net-microservices-and-web-applications"></a>Об авторизации в .NET микрослужбами и веб-приложений

После проверки подлинности необходимо авторизовать доступ веб-API ASP.NET Core. Этот процесс позволяет службе с API, доступны для некоторых пользователей, прошедших проверку подлинности, но не для всех. [Авторизация](https://docs.microsoft.com/aspnet/core/security/authorization/introduction) по отдельным ролями пользователей или зависимости от пользовательской политики, которая может включать проверки утверждений или других эвристики.

Ограничение доступа к маршрут ASP.NET Core MVC так же легко, как применение атрибута авторизовать методу действия (или класса контроллера, если действия контроллера, требуют наличия авторизации), как показано в следующем примере:

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

По умолчанию Добавление атрибута авторизовать без параметров ограничивает доступ пользователям, прошедшим проверку для этого контроллера или действия. Чтобы ограничить API доступен только для определенных пользователей, атрибут можно развернуть, чтобы указать необходимые роли или политики, пользователи должны удовлетворять.

## <a name="implementing-role-based-authorization"></a>Реализации авторизации на основе ролей

Удостоверение ASP.NET Core имеет встроенные концепция ролей. В дополнение к пользователям ASP.NET Core удостоверения хранит сведения о различных ролях, используемых приложением и отслеживает пользователей, которым назначены роли, к которым. Эти назначения можно изменить программным способом с типом RoleManager (которая обновляет роли в постоянное хранилище) и типа UserManager (который можно назначить или отменить назначение пользователей из ролей).

Если вы выполняете проверку подлинности с помощью маркеров JWT носителя, промежуточного по проверки подлинности носителя ASP.NET Core JWT будет заполнять роли пользователя на основе утверждений роли найдено в маркере. Для ограничения доступа на действие MVC или контроллера для определенных ролей пользователей, можно включить параметр ролей в заголовке авторизации, как показано в следующем примере:

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

В этом примере только пользователей в роли администратора или PowerUser можно получить доступ к API-интерфейсы в контроллере панель управления (например, при выполнении действия SetTime). Чтобы разрешить доступ только для пользователей в роли администратора ограничивается API завершения работы.

Требуют пользователь быть в несколько ролей, используйте несколько атрибутов Authorize, как показано в следующем примере:

```csharp
[Authorize(Roles = "Administrator, PowerUser")]
[Authorize(Roles = "RemoteEmployee ")]
[Authorize(Policy = "CustomPolicy")]
public ActionResult API1 ()
{
}
```

В этом примере для вызова API1, пользователь должен:

-   В администратор *или* роли PowerUser *и*

-   Входить в роль RemoteEmployee *и*

-   Удовлетворяет пользовательский обработчик для CustomPolicy авторизации.

## <a name="implementing-policy-based-authorization"></a>Реализация на основе политики авторизации

Пользовательская авторизация правил, также можно записать с помощью [политики авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html). В этом разделе приводится обзор. Дополнительные сведения доступны в документации по [цеху авторизации ASP.NET](https://github.com/blowdart/AspNetAuthorizationWorkshop).

Пользовательских политик авторизации, регистрируются в методе Startup.ConfigureServices, с помощью службы. Метод AddAuthorization. Этот метод принимает делегат, который настраивает AuthorizationOptions аргумента.

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

Как показано в примере политики могут быть связаны с разными типами требований. После регистрации политики, которые могут применяться на действие или контроллера, передав имя политики в качестве аргумента атрибута авторизовать политики (например, \[Authorize(Policy="EmployeesOnly")\]) может иметь политики несколько требований, не только одного (как показано в следующих примерах).

В предыдущем примере сначала AddPolicy вызывается только один способ авторизации по ролям. Если \[Authorize(Policy="AdministratorsOnly")\] применяется к API, только пользователи с ролью администратора смогут получить к нему доступ.

При втором вызове AddPolicy демонстрируется простой способ требует, что определенный утверждения должны присутствовать для пользователя. Метод RequireClaim также принимает ожидаемые значения для утверждения. Если указаны значения, это требование выполняется только в том случае, если пользователь имеет неправильный тип утверждения и одно из указанных значений. При использовании проверки подлинности по промежуточного слоя JWT носителя все свойства JWT будет доступна в качестве утверждения пользователей.

Наиболее интересные политика, показанный здесь находится в третий метод AddPolicy, так как оно использует требование настраиваемой авторизации. С помощью настраиваемой авторизации требования, может иметь высокую степень контроля над выполнением авторизации. Чтобы это работало необходимо реализовать следующие типы:

-   Требования к тип, производный от IAuthorizationRequirement, которая содержит поля, определяющие сведения о требовании. В примере это поле возраста для типа MinimumAgeRequirement образца.

-   Обработчик, который реализует AuthorizationHandler&lt;T&gt;, где T — тип IAuthorizationRequirement, который удовлетворяет требованиям обработчик. Обработчик должен реализовывать метод HandleRequirementAsync, который проверяет, удовлетворяет ли заданный контекст, который содержит сведения о пользователе требование.

Если пользователь отвечает требованиям, вызов контекста. Успешно будет указывать, что пользователь авторизован. Если существует несколько способов, что пользователь может удовлетворить требования к авторизации, можно создать несколько обработчиков.

Помимо регистрации пользовательской политики требований с вызовами AddPolicy, необходимо также зарегистрировать обработчики пользовательского требования через внедрения зависимостей (службы. AddTransient&lt;IAuthorizationHandler, MinimumAgeHandler&gt;()).

Пример настраиваемой авторизации требование и обработчик для проверки возраста пользователя (с учетом утверждений DateOfBirth) доступен в ASP.NET Core [документации авторизации](https://docs.asp.net/en/latest/security/authorization/policies.html).

## <a name="additional-resources"></a>Дополнительные ресурсы

-   **Проверка подлинности ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Авторизации ASP.NET Core**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/introduction*](https://docs.microsoft.com/aspnet/core/security/authorization/introduction)

-   **Авторизация на основе ролей**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/roles*](https://docs.microsoft.com/aspnet/core/security/authorization/roles)

-   **Пользовательская авторизация на основе политики**
    [*https://docs.microsoft.com/aspnet/core/security/authorization/policies*](https://docs.microsoft.com/aspnet/core/security/authorization/policies)




>[!div class="step-by-step"]
[Предыдущие] (index.md) [Далее] (разработчика app секреты storage.md)
