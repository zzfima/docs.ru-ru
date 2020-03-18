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
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="e1848-103">Структура проекта для приложений Blazor</span><span class="sxs-lookup"><span data-stu-id="e1848-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e1848-104">Несмотря на значительные различия в структуре проекта, ASP.NET Web Forms и Blazor имеют много похожих концепций.</span><span class="sxs-lookup"><span data-stu-id="e1848-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="e1848-105">Здесь мы рассмотрим структуру проекта Blazor и сравним его с проектом ASP.NET web forms.</span><span class="sxs-lookup"><span data-stu-id="e1848-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="e1848-106">Чтобы создать свое первое приложение Blazor, следуйте инструкциям в [Blazor, начинающимся шагам.](/aspnet/core/blazor/get-started)</span><span class="sxs-lookup"><span data-stu-id="e1848-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="e1848-107">Вы можете следовать инструкциям по созданию приложения Blazor Server или приложения Blazor WebAssembly, размещенного в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1848-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="e1848-108">За исключением логики, предназначенной для хостинг-модели, большая часть кода в обоих проектах одинакова.</span><span class="sxs-lookup"><span data-stu-id="e1848-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="e1848-109">Файл проекта</span><span class="sxs-lookup"><span data-stu-id="e1848-109">Project file</span></span>

<span data-ttu-id="e1848-110">Приложения Blazor Server являются основными проектами .NET.</span><span class="sxs-lookup"><span data-stu-id="e1848-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="e1848-111">Файл проекта для приложения Blazor Server настолько прост, насколько это возможно:</span><span class="sxs-lookup"><span data-stu-id="e1848-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="e1848-112">Файл проекта для приложения Blazor WebAssembly выглядит немного более вовлеченным (точные номера версий могут варьироваться):</span><span class="sxs-lookup"><span data-stu-id="e1848-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="e1848-113">Проекты Blazor WebAssembly нацелены на .NET Standard вместо .NET Core, поскольку они работают в браузере на основе WebAssembly .NET.</span><span class="sxs-lookup"><span data-stu-id="e1848-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="e1848-114">Вы не можете установить .NET в веб-браузер, как вы можете на сервере или машине разработчика.</span><span class="sxs-lookup"><span data-stu-id="e1848-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="e1848-115">Следовательно, проект ссылается на платформу Blazor с использованием индивидуальных ссылок пакетов.</span><span class="sxs-lookup"><span data-stu-id="e1848-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="e1848-116">Для сравнения, проект ASP.NET Web Forms по умолчанию включает в себя почти 300 строк XML в *файле .csproj,* большинство из которых явно перечисляют различные файлы кода и содержимого в проекте.</span><span class="sxs-lookup"><span data-stu-id="e1848-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="e1848-117">Многие из упрощения в проектах .NET Core и .NET Standard происходят из целей по умолчанию и свойств, импортируемых ссылками на `Microsoft.NET.Sdk.Web` SDK, часто именуемых просто Web SDK.</span><span class="sxs-lookup"><span data-stu-id="e1848-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="e1848-118">Веб-SDK включает в себя подстановочные знаки и другие удобства, которые упрощают включение файлов кода и содержимого в проект.</span><span class="sxs-lookup"><span data-stu-id="e1848-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="e1848-119">Вам не нужно перечислять файлы явно.</span><span class="sxs-lookup"><span data-stu-id="e1848-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="e1848-120">При таргетинге на ядро .NET Web SDK также добавляет ссылки на рамки как для .NET Core, так и для ASP.NET основных общих инфраструктур.</span><span class="sxs-lookup"><span data-stu-id="e1848-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="e1848-121">Платформы видны из узла**инфраструктуры** **зависимостей** > в окне **Solution Explorer.**</span><span class="sxs-lookup"><span data-stu-id="e1848-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="e1848-122">Общие фреймы представляют коллекции сборок, которые были установлены на машине при установке .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1848-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="e1848-123">Несмотря на поддержку, индивидуальные ссылки на сборку менее распространены в проектах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1848-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="e1848-124">Большинство зависимостей проекта обрабатываются в виде ссылок на пакетЫ NuGet.</span><span class="sxs-lookup"><span data-stu-id="e1848-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="e1848-125">Вам нужно только ссылки на верхние зависимости пакетов в проектах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1848-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="e1848-126">Транзитные зависимости включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="e1848-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="e1848-127">Вместо использования файла *packages.config,* обычно встречающегося в проектах ASP.NET Web Forms, в `<PackageReference>` справочные пакеты добавляются ссылки на пакеты с использованием элемента.</span><span class="sxs-lookup"><span data-stu-id="e1848-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="e1848-128">Точка входа</span><span class="sxs-lookup"><span data-stu-id="e1848-128">Entry point</span></span>

<span data-ttu-id="e1848-129">Точка входа приложения Blazor Server определена в *Program.cs* файле, как вы могли бы видеть в приложении Console.</span><span class="sxs-lookup"><span data-stu-id="e1848-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="e1848-130">Когда приложение выполняет, оно создает и запускает экземпляр веб-хостинга, используя специфические для веб-приложений значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e1848-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="e1848-131">Веб-хостинг управляет жизненным циклом приложения Blazor Server и настраивает службы на уровне хоста.</span><span class="sxs-lookup"><span data-stu-id="e1848-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="e1848-132">Примерами таких служб являются конфигурация, журналирование, инъекция зависимости и сервер HTTP.</span><span class="sxs-lookup"><span data-stu-id="e1848-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="e1848-133">Этот код в основном шаблоник и часто остается неизменным.</span><span class="sxs-lookup"><span data-stu-id="e1848-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="e1848-134">Blazor WebAssembly приложения также определить точку входа в *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="e1848-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="e1848-135">Код выглядит немного иначе.</span><span class="sxs-lookup"><span data-stu-id="e1848-135">The code looks slightly different.</span></span> <span data-ttu-id="e1848-136">Код аналогичен тому, что он настраивает хост приложения для предоставления приложения тех же услуг уровня хоста.</span><span class="sxs-lookup"><span data-stu-id="e1848-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="e1848-137">Однако хост приложения WebAssembly не настраивает сервер HTTP, поскольку он выполняется непосредственно в браузере.</span><span class="sxs-lookup"><span data-stu-id="e1848-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="e1848-138">Приложения Blazor `Startup` имеют класс вместо файла *Global.asax* для определения логики запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="e1848-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="e1848-139">Класс `Startup` используется для настройки приложения и любых служб, связанных с приложением.</span><span class="sxs-lookup"><span data-stu-id="e1848-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="e1848-140">В приложении Blazor `Startup` Server класс используется для настройки конечных точек для подключения Blazor в режиме реального времени между браузерами клиентов и сервером.</span><span class="sxs-lookup"><span data-stu-id="e1848-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="e1848-141">В приложении Blazor WebAssembly `Startup` класс определяет корневые компоненты приложения и место их визуализации.</span><span class="sxs-lookup"><span data-stu-id="e1848-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="e1848-142">Мы рассмотрим `Startup` класс в разделе Стартап [App](./app-startup.md) подробнее.</span><span class="sxs-lookup"><span data-stu-id="e1848-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="e1848-143">Статические файлы</span><span class="sxs-lookup"><span data-stu-id="e1848-143">Static files</span></span>

<span data-ttu-id="e1848-144">В отличие от ASP.NET проектов Web Forms, не все файлы в проекте Blazor могут быть запрошены в качестве статических файлов.</span><span class="sxs-lookup"><span data-stu-id="e1848-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="e1848-145">Только файлы в папке *wwwroot* являются веб-адресными.</span><span class="sxs-lookup"><span data-stu-id="e1848-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="e1848-146">Эта папка относится к "веб-корню" приложения.</span><span class="sxs-lookup"><span data-stu-id="e1848-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="e1848-147">Все, что не связано с веб-корнем приложения, *не является* веб-адресом.</span><span class="sxs-lookup"><span data-stu-id="e1848-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="e1848-148">Эта настройка обеспечивает дополнительный уровень безопасности, который предотвращает случайное разоблачение файлов проекта через Интернет.</span><span class="sxs-lookup"><span data-stu-id="e1848-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="e1848-149">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e1848-149">Configuration</span></span>

<span data-ttu-id="e1848-150">Конфигурация в приложениях ASP.NET web-форм обычно обрабатывается с помощью одного или нескольких файлов *web.config.*</span><span class="sxs-lookup"><span data-stu-id="e1848-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="e1848-151">Приложения Blazor обычно не имеют *файлов web..config.*</span><span class="sxs-lookup"><span data-stu-id="e1848-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="e1848-152">В этом случае файл используется только для настройки параметров IIS при размещении на IIS.</span><span class="sxs-lookup"><span data-stu-id="e1848-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="e1848-153">Вместо этого приложения Blazor Server используют абстракции конфигурации ASP.NET Core (приложения Blazor WebAssembly в настоящее время не поддерживают те же абстракции конфигурации, но это может быть функция, добавленная в будущем).</span><span class="sxs-lookup"><span data-stu-id="e1848-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="e1848-154">Например, приложение Blazor Server по умолчанию хранит некоторые настройки в *appsettings.json.*</span><span class="sxs-lookup"><span data-stu-id="e1848-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="e1848-155">Подробнее о конфигурации мы узнаем в ASP.NET основных проектах в разделе [Конфигурация.](./config.md)</span><span class="sxs-lookup"><span data-stu-id="e1848-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="e1848-156">Компоненты Razor</span><span class="sxs-lookup"><span data-stu-id="e1848-156">Razor components</span></span>

<span data-ttu-id="e1848-157">Большинство файлов в проектах Blazor являются *файлами .razor.*</span><span class="sxs-lookup"><span data-stu-id="e1848-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="e1848-158">Razor — это шаблонный язык, основанный на HTML и C,, который используется для динамического генерирования веб-uI.</span><span class="sxs-lookup"><span data-stu-id="e1848-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="e1848-159">Файлы *.razor* определяют компоненты, составляющие uI приложения.</span><span class="sxs-lookup"><span data-stu-id="e1848-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="e1848-160">По большей части компоненты идентичны как для приложений Blazor Server, так и для WebAssembly Blazor.</span><span class="sxs-lookup"><span data-stu-id="e1848-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="e1848-161">Компоненты blazor аналогичны элементам управления пользователями в ASP.NET веб-формах.</span><span class="sxs-lookup"><span data-stu-id="e1848-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="e1848-162">Каждый файл компонента Razor компилируется в класс .NET при построении проекта.</span><span class="sxs-lookup"><span data-stu-id="e1848-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="e1848-163">Сгенерированный класс отражает состояние компонента, визуализацию логики, методов жизненного цикла, обработчиков событий и другую логику.</span><span class="sxs-lookup"><span data-stu-id="e1848-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="e1848-164">Мы рассмотрим авторские компоненты в [многоразовом компонентах uI Building с](./components.md) разделом Blazor.</span><span class="sxs-lookup"><span data-stu-id="e1848-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="e1848-165">Файлы *_Imports.razor* не являются файлами компонентов Razor.</span><span class="sxs-lookup"><span data-stu-id="e1848-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="e1848-166">Вместо этого они определяют набор директив Razor для импорта в другие файлы *.razor* в той же папке и в субфандрах.</span><span class="sxs-lookup"><span data-stu-id="e1848-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="e1848-167">Например, файл *_Imports.razor* — это `using` обычный способ добавления инструкций для часто используемых пространств имен:</span><span class="sxs-lookup"><span data-stu-id="e1848-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="e1848-168">Страницы</span><span class="sxs-lookup"><span data-stu-id="e1848-168">Pages</span></span>

<span data-ttu-id="e1848-169">Где страницы в приложениях Blazor?</span><span class="sxs-lookup"><span data-stu-id="e1848-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="e1848-170">Blazor не определяет отдельное расширение файлов для адресных страниц, таких как файлы *.aspx* в приложениях web-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e1848-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="e1848-171">Вместо этого страницы определяются путем присвоения маршрутов компонентам.</span><span class="sxs-lookup"><span data-stu-id="e1848-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="e1848-172">Маршрут обычно назначается с `@page` помощью директивы Razor.</span><span class="sxs-lookup"><span data-stu-id="e1848-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="e1848-173">Например, `Counter` компонент, автор из файла *Pages/Counter.razor,* определяет следующий маршрут:</span><span class="sxs-lookup"><span data-stu-id="e1848-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="e1848-174">Реутинг в Blazor обрабатывается на стороне клиента, а не на сервере.</span><span class="sxs-lookup"><span data-stu-id="e1848-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="e1848-175">Когда пользователь перемещается в браузере, Blazor перехватывает навигацию, а затем отображает компонент с соответствующим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="e1848-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="e1848-176">Маршруты компонентов в настоящее время не выведены расположением файла компонента, как на страницах *.aspx.*</span><span class="sxs-lookup"><span data-stu-id="e1848-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="e1848-177">Эта функция может быть добавлена в будущем.</span><span class="sxs-lookup"><span data-stu-id="e1848-177">This feature may be added in the future.</span></span> <span data-ttu-id="e1848-178">Каждый маршрут должен быть четко указан на компоненте.</span><span class="sxs-lookup"><span data-stu-id="e1848-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="e1848-179">Хранение компонентов в папке *Страницы* не имеет особого значения и является чисто конвенцией.</span><span class="sxs-lookup"><span data-stu-id="e1848-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="e1848-180">Мы рассмотрим более подробно на разгромва в Blazor в [разделе Страницы, трассировки и макетов.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="e1848-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="e1848-181">Макет</span><span class="sxs-lookup"><span data-stu-id="e1848-181">Layout</span></span>

<span data-ttu-id="e1848-182">В ASP.NET веб-приложений, общий макет страницы обрабатывается с помощью мастер-страниц (*Site.Master*).</span><span class="sxs-lookup"><span data-stu-id="e1848-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="e1848-183">В приложениях Blazor макет страницы обрабатывается с помощью компонентов макета *(Shared/MainLayout.razor*).</span><span class="sxs-lookup"><span data-stu-id="e1848-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="e1848-184">Компоненты макета будут более подробно обсуждаться в разделе [Страница, трассировка и макеты.](./pages-routing-layouts.md)</span><span class="sxs-lookup"><span data-stu-id="e1848-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="e1848-185">Bootstrap Блазор</span><span class="sxs-lookup"><span data-stu-id="e1848-185">Bootstrap Blazor</span></span>

<span data-ttu-id="e1848-186">Для загрузки Blazor, приложение должно:</span><span class="sxs-lookup"><span data-stu-id="e1848-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="e1848-187">Укажите, где на странице должен быть отображан корневой компонент *(App.Razor).*</span><span class="sxs-lookup"><span data-stu-id="e1848-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="e1848-188">Добавьте соответствующий сценарий рамок Blazor.</span><span class="sxs-lookup"><span data-stu-id="e1848-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="e1848-189">В приложении Blazor Server страница хоста корневого компонента определяется в файле *_Host.cshtml.*</span><span class="sxs-lookup"><span data-stu-id="e1848-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="e1848-190">Этот файл определяет страницу Razor, а не компонент.</span><span class="sxs-lookup"><span data-stu-id="e1848-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="e1848-191">Razor Pages используют синтаксис Razor для определения адресной страницы сервера, очень похожей на страницу *.aspx.*</span><span class="sxs-lookup"><span data-stu-id="e1848-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="e1848-192">Метод `Html.RenderComponentAsync<TComponent>(RenderMode)` используется для определения того, где следует визуализировать компонент корневого уровня.</span><span class="sxs-lookup"><span data-stu-id="e1848-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="e1848-193">Параметр `RenderMode` указывает способ визуализации компонента.</span><span class="sxs-lookup"><span data-stu-id="e1848-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="e1848-194">В следующей таблице `RenderMode` излагаются поддерживаемые варианты.</span><span class="sxs-lookup"><span data-stu-id="e1848-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="e1848-195">Параметр</span><span class="sxs-lookup"><span data-stu-id="e1848-195">Option</span></span>                        |<span data-ttu-id="e1848-196">Описание</span><span class="sxs-lookup"><span data-stu-id="e1848-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="e1848-197">Внепланируется в интерактивном режиме после установления связи с браузером</span><span class="sxs-lookup"><span data-stu-id="e1848-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="e1848-198">Сначала prerendered, а затем визуализированы интерактивно</span><span class="sxs-lookup"><span data-stu-id="e1848-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="e1848-199">Рентаемые как статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="e1848-199">Rendered as static content</span></span>|

<span data-ttu-id="e1848-200">Ссылка на *_framework/blazor.server.js* устанавливает подключение в режиме реального времени с сервером, а затем касается всех пользовательских взаимодействий и обновлений пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e1848-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="e1848-201">В приложении Blazor WebAssembly страница хоста представляет собой простой статический HTML-файл *под wwwroot/index.html.*</span><span class="sxs-lookup"><span data-stu-id="e1848-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="e1848-202">Элемент `<app>` используется для указания того, где должен быть отрисован корневой компонент.</span><span class="sxs-lookup"><span data-stu-id="e1848-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="e1848-203">Конкретный компонент для визуализации настроен в `Startup.Configure` методе приложения с соответствующим селектораcs CSS с указанием, где компонент должен быть визуализирован.</span><span class="sxs-lookup"><span data-stu-id="e1848-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="e1848-204">Выходные данные при создании</span><span class="sxs-lookup"><span data-stu-id="e1848-204">Build output</span></span>

<span data-ttu-id="e1848-205">При построении проекта Blazor все компоненты Razor и файлы кода компилируются в единую сборку.</span><span class="sxs-lookup"><span data-stu-id="e1848-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="e1848-206">В отличие от проектов ASP.NET веб-форм, Blazor не поддерживает компиляцию времени выполнения логики uI.</span><span class="sxs-lookup"><span data-stu-id="e1848-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="e1848-207">Запустите приложение</span><span class="sxs-lookup"><span data-stu-id="e1848-207">Run the app</span></span>

<span data-ttu-id="e1848-208">Чтобы запустить приложение Blazor `F5` Server, нажмите в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e1848-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="e1848-209">Приложения Blazor не поддерживают компиляцию времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="e1848-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="e1848-210">Чтобы увидеть результаты изменений разметки кода и компонентов, перестроить и перезапустить приложение с прикрепленным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="e1848-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="e1848-211">Если вы работаете без прилагаемого отладчика ( ),`Ctrl+F5`Visual Studio часы для изменения файлов и перезапускает приложение по мере внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="e1848-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="e1848-212">Вы вручную обновляете браузер по мере внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="e1848-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="e1848-213">Чтобы запустить приложение Blazor WebAssembly, выберите один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="e1848-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="e1848-214">Запустите клиентский проект непосредственно с помощью сервера разработки.</span><span class="sxs-lookup"><span data-stu-id="e1848-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="e1848-215">Запустите проект сервера при размещении приложения с ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e1848-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="e1848-216">Приложения Blazor WebAssembly не поддерживают отладку с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e1848-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="e1848-217">Чтобы запустить приложение, `Ctrl+F5` используйте вместо `F5`.</span><span class="sxs-lookup"><span data-stu-id="e1848-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="e1848-218">Вместо этого вы можете отладить приложения Blazor WebAssembly непосредственно в браузере.</span><span class="sxs-lookup"><span data-stu-id="e1848-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="e1848-219">Подробности смотрите в подробностях [ASP.NET Core Blazor.](/aspnet/core/blazor/debug)</span><span class="sxs-lookup"><span data-stu-id="e1848-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e1848-220">[Предыдущий](hosting-models.md)
>[Следующий](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="e1848-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
