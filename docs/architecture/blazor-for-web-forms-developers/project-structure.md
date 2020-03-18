---
title: Структура проекта для приложений Blazor
description: Узнайте, как сравниваются проектные структуры ASP.NET веб-форм и проектов Blazor.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401745"
---
# <a name="project-structure-for-blazor-apps"></a>Структура проекта для приложений Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Несмотря на значительные различия в структуре проекта, ASP.NET Web Forms и Blazor имеют много похожих концепций. Здесь мы рассмотрим структуру проекта Blazor и сравним его с проектом ASP.NET web forms.

Чтобы создать свое первое приложение Blazor, следуйте инструкциям в [Blazor, начинающимся шагам.](/aspnet/core/blazor/get-started) Вы можете следовать инструкциям по созданию приложения Blazor Server или приложения Blazor WebAssembly, размещенного в ASP.NET Core. За исключением логики, предназначенной для хостинг-модели, большая часть кода в обоих проектах одинакова.

## <a name="project-file"></a>Файл проекта

Приложения Blazor Server являются основными проектами .NET. Файл проекта для приложения Blazor Server настолько прост, насколько это возможно:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

Файл проекта для приложения Blazor WebAssembly выглядит немного более вовлеченным (точные номера версий могут варьироваться):

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <RazorLangVersion>3.0</RazorLangVersion>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.AspNetCore.Blazor" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.Build" Version="3.1.0" PrivateAssets="all" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.HttpClient" Version="3.1.0" />
    <PackageReference Include="Microsoft.AspNetCore.Blazor.DevServer" Version="3.1.0" PrivateAssets="all" />
  </ItemGroup>

  <ItemGroup>
    <ProjectReference Include="..\Shared\BlazorWebAssemblyApp1.Shared.csproj" />
  </ItemGroup>

</Project>
```

Проекты Blazor WebAssembly нацелены на .NET Standard вместо .NET Core, поскольку они работают в браузере на основе WebAssembly .NET. Вы не можете установить .NET в веб-браузер, как вы можете на сервере или машине разработчика. Следовательно, проект ссылается на платформу Blazor с использованием индивидуальных ссылок пакетов.

Для сравнения, проект ASP.NET Web Forms по умолчанию включает в себя почти 300 строк XML в *файле .csproj,* большинство из которых явно перечисляют различные файлы кода и содержимого в проекте. Многие из упрощения в проектах .NET Core и .NET Standard происходят из целей по умолчанию и свойств, импортируемых ссылками на `Microsoft.NET.Sdk.Web` SDK, часто именуемых просто Web SDK. Веб-SDK включает в себя подстановочные знаки и другие удобства, которые упрощают включение файлов кода и содержимого в проект. Вам не нужно перечислять файлы явно. При таргетинге на ядро .NET Web SDK также добавляет ссылки на рамки как для .NET Core, так и для ASP.NET основных общих инфраструктур. Платформы видны из узла**инфраструктуры** **зависимостей** > в окне **Solution Explorer.** Общие фреймы представляют коллекции сборок, которые были установлены на машине при установке .NET Core.

Несмотря на поддержку, индивидуальные ссылки на сборку менее распространены в проектах .NET Core. Большинство зависимостей проекта обрабатываются в виде ссылок на пакетЫ NuGet. Вам нужно только ссылки на верхние зависимости пакетов в проектах .NET Core. Транзитные зависимости включаются автоматически. Вместо использования файла *packages.config,* обычно встречающегося в проектах ASP.NET Web Forms, в `<PackageReference>` справочные пакеты добавляются ссылки на пакеты с использованием элемента.

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a>Точка входа

Точка входа приложения Blazor Server определена в *Program.cs* файле, как вы могли бы видеть в приложении Console. Когда приложение выполняет, оно создает и запускает экземпляр веб-хостинга, используя специфические для веб-приложений значения по умолчанию. Веб-хостинг управляет жизненным циклом приложения Blazor Server и настраивает службы на уровне хоста. Примерами таких служб являются конфигурация, журналирование, инъекция зависимости и сервер HTTP. Этот код в основном шаблоник и часто остается неизменным.

```csharp
public class Program
{
    public static void Main(string[] args)
    {
        CreateHostBuilder(args).Build().Run();
    }

    public static IHostBuilder CreateHostBuilder(string[] args) =>
        Host.CreateDefaultBuilder(args)
            .ConfigureWebHostDefaults(webBuilder =>
            {
                webBuilder.UseStartup<Startup>();
            });
}
```

Blazor WebAssembly приложения также определить точку входа в *Program.cs*. Код выглядит немного иначе. Код аналогичен тому, что он настраивает хост приложения для предоставления приложения тех же услуг уровня хоста. Однако хост приложения WebAssembly не настраивает сервер HTTP, поскольку он выполняется непосредственно в браузере.

Приложения Blazor `Startup` имеют класс вместо файла *Global.asax* для определения логики запуска приложения. Класс `Startup` используется для настройки приложения и любых служб, связанных с приложением. В приложении Blazor `Startup` Server класс используется для настройки конечных точек для подключения Blazor в режиме реального времени между браузерами клиентов и сервером. В приложении Blazor WebAssembly `Startup` класс определяет корневые компоненты приложения и место их визуализации. Мы рассмотрим `Startup` класс в разделе Стартап [App](./app-startup.md) подробнее.

## <a name="static-files"></a>Статические файлы

В отличие от ASP.NET проектов Web Forms, не все файлы в проекте Blazor могут быть запрошены в качестве статических файлов. Только файлы в папке *wwwroot* являются веб-адресными. Эта папка относится к "веб-корню" приложения. Все, что не связано с веб-корнем приложения, *не является* веб-адресом. Эта настройка обеспечивает дополнительный уровень безопасности, который предотвращает случайное разоблачение файлов проекта через Интернет.

## <a name="configuration"></a>Конфигурация

Конфигурация в приложениях ASP.NET web-форм обычно обрабатывается с помощью одного или нескольких файлов *web.config.* Приложения Blazor обычно не имеют *файлов web..config.* В этом случае файл используется только для настройки параметров IIS при размещении на IIS. Вместо этого приложения Blazor Server используют абстракции конфигурации ASP.NET Core (приложения Blazor WebAssembly в настоящее время не поддерживают те же абстракции конфигурации, но это может быть функция, добавленная в будущем). Например, приложение Blazor Server по умолчанию хранит некоторые настройки в *appsettings.json.*

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    }
  },
  "AllowedHosts": "*"
}
```

Подробнее о конфигурации мы узнаем в ASP.NET основных проектах в разделе [Конфигурация.](./config.md)

## <a name="razor-components"></a>Компоненты Razor

Большинство файлов в проектах Blazor являются *файлами .razor.* Razor — это шаблонный язык, основанный на HTML и C,, который используется для динамического генерирования веб-uI. Файлы *.razor* определяют компоненты, составляющие uI приложения. По большей части компоненты идентичны как для приложений Blazor Server, так и для WebAssembly Blazor. Компоненты blazor аналогичны элементам управления пользователями в ASP.NET веб-формах.

Каждый файл компонента Razor компилируется в класс .NET при построении проекта. Сгенерированный класс отражает состояние компонента, визуализацию логики, методов жизненного цикла, обработчиков событий и другую логику. Мы рассмотрим авторские компоненты в [многоразовом компонентах uI Building с](./components.md) разделом Blazor.

Файлы *_Imports.razor* не являются файлами компонентов Razor. Вместо этого они определяют набор директив Razor для импорта в другие файлы *.razor* в той же папке и в субфандрах. Например, файл *_Imports.razor* — это `using` обычный способ добавления инструкций для часто используемых пространств имен:

```razor
@using System.Net.Http
@using Microsoft.AspNetCore.Authorization
@using Microsoft.AspNetCore.Components.Authorization
@using Microsoft.AspNetCore.Components.Forms
@using Microsoft.AspNetCore.Components.Routing
@using Microsoft.AspNetCore.Components.Web
@using Microsoft.JSInterop
@using BlazorApp1
@using BlazorApp1.Shared
```

## <a name="pages"></a>Страницы

Где страницы в приложениях Blazor? Blazor не определяет отдельное расширение файлов для адресных страниц, таких как файлы *.aspx* в приложениях web-форм ASP.NET. Вместо этого страницы определяются путем присвоения маршрутов компонентам. Маршрут обычно назначается с `@page` помощью директивы Razor. Например, `Counter` компонент, автор из файла *Pages/Counter.razor,* определяет следующий маршрут:

```razor
@page "/counter"
```

Реутинг в Blazor обрабатывается на стороне клиента, а не на сервере. Когда пользователь перемещается в браузере, Blazor перехватывает навигацию, а затем отображает компонент с соответствующим маршрутом.

Маршруты компонентов в настоящее время не выведены расположением файла компонента, как на страницах *.aspx.* Эта функция может быть добавлена в будущем. Каждый маршрут должен быть четко указан на компоненте. Хранение компонентов в папке *Страницы* не имеет особого значения и является чисто конвенцией.

Мы рассмотрим более подробно на разгромва в Blazor в [разделе Страницы, трассировки и макетов.](./pages-routing-layouts.md)

## <a name="layout"></a>Макет

В ASP.NET веб-приложений, общий макет страницы обрабатывается с помощью мастер-страниц (*Site.Master*). В приложениях Blazor макет страницы обрабатывается с помощью компонентов макета *(Shared/MainLayout.razor*). Компоненты макета будут более подробно обсуждаться в разделе [Страница, трассировка и макеты.](./pages-routing-layouts.md)

## <a name="bootstrap-blazor"></a>Bootstrap Блазор

Для загрузки Blazor, приложение должно:

- Укажите, где на странице должен быть отображан корневой компонент *(App.Razor).*
- Добавьте соответствующий сценарий рамок Blazor.

В приложении Blazor Server страница хоста корневого компонента определяется в файле *_Host.cshtml.* Этот файл определяет страницу Razor, а не компонент. Razor Pages используют синтаксис Razor для определения адресной страницы сервера, очень похожей на страницу *.aspx.* Метод `Html.RenderComponentAsync<TComponent>(RenderMode)` используется для определения того, где следует визуализировать компонент корневого уровня. Параметр `RenderMode` указывает способ визуализации компонента. В следующей таблице `RenderMode` излагаются поддерживаемые варианты.

|Параметр                        |Описание       |
|------------------------------|------------------|
|`RenderMode.Server`           |Внепланируется в интерактивном режиме после установления связи с браузером|
|`RenderMode.ServerPrerendered`|Сначала prerendered, а затем визуализированы интерактивно|
|`RenderMode.Static`           |Рентаемые как статическое содержимое|

Ссылка на *_framework/blazor.server.js* устанавливает подключение в режиме реального времени с сервером, а затем касается всех пользовательских взаимодействий и обновлений пользовательского интерфейса.

```razor
@page "/"
@namespace BlazorApp1.Pages
@addTagHelper *, Microsoft.AspNetCore.Mvc.TagHelpers

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>BlazorApp1</title>
    <base href="~/" />
    <link rel="stylesheet" href="css/bootstrap/bootstrap.min.css" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>
        @(await Html.RenderComponentAsync<App>(RenderMode.ServerPrerendered))
    </app>

    <script src="_framework/blazor.server.js"></script>
</body>
</html>
```

В приложении Blazor WebAssembly страница хоста представляет собой простой статический HTML-файл *под wwwroot/index.html.* Элемент `<app>` используется для указания того, где должен быть отрисован корневой компонент.

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>BlazorApp2</title>
    <base href="/" />
    <link href="css/bootstrap/bootstrap.min.css" rel="stylesheet" />
    <link href="css/site.css" rel="stylesheet" />
</head>
<body>
    <app>Loading...</app>

    <script src="_framework/blazor.webassembly.js"></script>
</body>
</html>
```

Конкретный компонент для визуализации настроен в `Startup.Configure` методе приложения с соответствующим селектораcs CSS с указанием, где компонент должен быть визуализирован.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
    }

    public void Configure(IComponentsApplicationBuilder app)
    {
        app.AddComponent<App>("app");
    }
}
```

## <a name="build-output"></a>Выходные данные при создании

При построении проекта Blazor все компоненты Razor и файлы кода компилируются в единую сборку. В отличие от проектов ASP.NET веб-форм, Blazor не поддерживает компиляцию времени выполнения логики uI.

## <a name="run-the-app"></a>Запустите приложение

Чтобы запустить приложение Blazor `F5` Server, нажмите в Visual Studio. Приложения Blazor не поддерживают компиляцию времени выполнения. Чтобы увидеть результаты изменений разметки кода и компонентов, перестроить и перезапустить приложение с прикрепленным отладчиком. Если вы работаете без прилагаемого отладчика ( ),`Ctrl+F5`Visual Studio часы для изменения файлов и перезапускает приложение по мере внесения изменений. Вы вручную обновляете браузер по мере внесения изменений.

Чтобы запустить приложение Blazor WebAssembly, выберите один из следующих подходов:

- Запустите клиентский проект непосредственно с помощью сервера разработки.
- Запустите проект сервера при размещении приложения с ASP.NET Core.

Приложения Blazor WebAssembly не поддерживают отладку с помощью Visual Studio. Чтобы запустить приложение, `Ctrl+F5` используйте вместо `F5`. Вместо этого вы можете отладить приложения Blazor WebAssembly непосредственно в браузере. Подробности смотрите в подробностях [ASP.NET Core Blazor.](/aspnet/core/blazor/debug)

>[!div class="step-by-step"]
>[Предыдущий](hosting-models.md)
>[Следующий](app-startup.md)
