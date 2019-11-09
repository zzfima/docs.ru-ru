---
title: Структура проекта для приложений Блазор
description: Узнайте, как сравниваются структуры проекта веб-форм ASP.NET и проектов Блазор.
author: danroth27
ms.author: daroth
ms.date: 09/11/2019
ms.openlocfilehash: 2c383e86ff22f5a3460476998992b66e9417cc11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841909"
---
# <a name="project-structure-for-blazor-apps"></a><span data-ttu-id="88cd8-103">Структура проекта для приложений Блазор</span><span class="sxs-lookup"><span data-stu-id="88cd8-103">Project structure for Blazor apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="88cd8-104">Несмотря на существенные различия в структуре проекта, веб-формы ASP.NET и Блазор имеют много похожих концепций.</span><span class="sxs-lookup"><span data-stu-id="88cd8-104">Despite their significant project structure differences, ASP.NET Web Forms and Blazor share many similar concepts.</span></span> <span data-ttu-id="88cd8-105">Здесь мы рассмотрим структуру проекта Блазор и сравнив его с проектом веб-форм ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="88cd8-105">Here, we'll look at the structure of a Blazor project and compare it to an ASP.NET Web Forms project.</span></span>

<span data-ttu-id="88cd8-106">Чтобы создать первое приложение Блазор, следуйте инструкциям в руководстве по [началу работы с блазор](/aspnet/core/blazor/get-started).</span><span class="sxs-lookup"><span data-stu-id="88cd8-106">To create your first Blazor app, follow the instructions in the [Blazor getting started steps](/aspnet/core/blazor/get-started).</span></span> <span data-ttu-id="88cd8-107">Вы можете выполнить инструкции по созданию приложения Блазор Server или Блазор, размещенного в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="88cd8-107">You can follow the instructions to create either a Blazor Server app or a Blazor WebAssembly app hosted in ASP.NET Core.</span></span> <span data-ttu-id="88cd8-108">За исключением логики размещения для конкретной модели, большая часть кода в обоих проектах одинакова.</span><span class="sxs-lookup"><span data-stu-id="88cd8-108">Except for the hosting model-specific logic, most of the code in both projects is the same.</span></span>

## <a name="project-file"></a><span data-ttu-id="88cd8-109">Файл проекта</span><span class="sxs-lookup"><span data-stu-id="88cd8-109">Project file</span></span>

<span data-ttu-id="88cd8-110">Серверные приложения блазор — это проекты .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88cd8-110">Blazor Server apps are .NET Core projects.</span></span> <span data-ttu-id="88cd8-111">Файл проекта для серверного приложения Блазор примерно так прост, как он может получить:</span><span class="sxs-lookup"><span data-stu-id="88cd8-111">The project file for the Blazor Server app is about as simple as it can get:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>netcoreapp3.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="88cd8-112">Файл проекта для приложения Блазор-сборки выглядит немного подробнее (точный номер версии может отличаться):</span><span class="sxs-lookup"><span data-stu-id="88cd8-112">The project file for a Blazor WebAssembly app looks slightly more involved (exact version numbers may vary):</span></span>

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

<span data-ttu-id="88cd8-113">Проекты блазор-сборки предназначены .NET Standard вместо .NET Core, так как они выполняются в браузере в среде выполнения .NET на основе сборки.</span><span class="sxs-lookup"><span data-stu-id="88cd8-113">Blazor WebAssembly projects target .NET Standard instead of .NET Core because they run in the browser on a WebAssembly-based .NET runtime.</span></span> <span data-ttu-id="88cd8-114">Вы не можете установить .NET в веб-браузер, как на сервере или на компьютере разработчика.</span><span class="sxs-lookup"><span data-stu-id="88cd8-114">You can't install .NET into a web browser like you can on a server or developer machine.</span></span> <span data-ttu-id="88cd8-115">Следовательно, проект ссылается на платформу Блазор, используя отдельные ссылки на пакеты.</span><span class="sxs-lookup"><span data-stu-id="88cd8-115">Consequently, the project references the Blazor framework using individual package references.</span></span>

<span data-ttu-id="88cd8-116">По сравнению, проект веб-форм ASP.NET по умолчанию включает в себя почти 300 строк XML в файле *. csproj* , большинство из которых явно задает в проекте различные файлы кода и содержимого.</span><span class="sxs-lookup"><span data-stu-id="88cd8-116">By comparison, a default ASP.NET Web Forms project includes almost 300 lines of XML in its *.csproj* file, most of which is explicitly listing the various code and content files in the project.</span></span> <span data-ttu-id="88cd8-117">Многие из упрощений в проектах на основе .NET Core и .NET Standard берутся из целевых объектов по умолчанию и свойств, импортированных с помощью ссылки на `Microsoft.NET.Sdk.Web` SDK, который часто называют просто веб-пакетом SDK.</span><span class="sxs-lookup"><span data-stu-id="88cd8-117">Many of the simplifications in the .NET Core- and .NET Standard-based projects come from the default targets and properties imported by referencing the `Microsoft.NET.Sdk.Web` SDK, often referred to as simply the Web SDK.</span></span> <span data-ttu-id="88cd8-118">Веб-пакет SDK включает подстановочные знаки и другие удобства, упрощающие включение файлов кода и содержимого в проект.</span><span class="sxs-lookup"><span data-stu-id="88cd8-118">The Web SDK includes wildcards and other conveniences that simplify inclusion of code and content files in the project.</span></span> <span data-ttu-id="88cd8-119">Вам не нужно явно перечислять файлы.</span><span class="sxs-lookup"><span data-stu-id="88cd8-119">You don't need to list the files explicitly.</span></span> <span data-ttu-id="88cd8-120">При разработке для .NET Core веб-пакет SDK также добавляет ссылки на платформы в общие платформы .NET Core и ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="88cd8-120">When targeting .NET Core, the Web SDK also adds framework references to both the .NET Core and ASP.NET Core shared frameworks.</span></span> <span data-ttu-id="88cd8-121">Платформы отображаются в узле **зависимости** > **Frameworks** в окне **Обозреватель решений** .</span><span class="sxs-lookup"><span data-stu-id="88cd8-121">The frameworks are visible from the **Dependencies** > **Frameworks** node in the **Solution Explorer** window.</span></span> <span data-ttu-id="88cd8-122">Общие платформы — это коллекции сборок, которые были установлены на компьютере при установке .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88cd8-122">The shared frameworks are collections of assemblies that were installed on the machine when installing .NET Core.</span></span>

<span data-ttu-id="88cd8-123">Хотя они поддерживаются, отдельные ссылки на сборки менее распространены в проектах .NET Core.</span><span class="sxs-lookup"><span data-stu-id="88cd8-123">Although they're supported, individual assembly references are less common in .NET Core projects.</span></span> <span data-ttu-id="88cd8-124">Большинство зависимостей проектов обрабатываются как ссылки на пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="88cd8-124">Most project dependencies are handled as NuGet package references.</span></span> <span data-ttu-id="88cd8-125">В проектах .NET Core необходимо ссылаться только на зависимости пакетов верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="88cd8-125">You only need to reference top-level package dependencies in .NET Core projects.</span></span> <span data-ttu-id="88cd8-126">Транзитивные зависимости включаются автоматически.</span><span class="sxs-lookup"><span data-stu-id="88cd8-126">Transitive dependencies are included automatically.</span></span> <span data-ttu-id="88cd8-127">Вместо использования файла *Packages. config* , обычно находящихся в проектах ASP.NET Web Forms, для ссылки на пакеты, ссылки на пакет добавляются в файл проекта с помощью элемента `<PackageReference>`.</span><span class="sxs-lookup"><span data-stu-id="88cd8-127">Instead of using the *packages.config* file commonly found in ASP.NET Web Forms projects to reference packages, package references are added to the project file using the `<PackageReference>` element.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

## <a name="entry-point"></a><span data-ttu-id="88cd8-128">Точка входа</span><span class="sxs-lookup"><span data-stu-id="88cd8-128">Entry point</span></span>

<span data-ttu-id="88cd8-129">Точка входа серверного приложения Блазор определяется в файле *Program.CS* , как показано в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="88cd8-129">The Blazor Server app's entry point is defined in the *Program.cs* file, as you would see in a Console app.</span></span> <span data-ttu-id="88cd8-130">При выполнении приложения он создает и запускает экземпляр веб-узла с использованием значений по умолчанию, относящихся к веб-приложениям.</span><span class="sxs-lookup"><span data-stu-id="88cd8-130">When the app executes, it creates and runs a web host instance using defaults specific to web apps.</span></span> <span data-ttu-id="88cd8-131">Веб-узел управляет жизненным циклом приложения Блазор Server и настраивает службы на уровне узла.</span><span class="sxs-lookup"><span data-stu-id="88cd8-131">The web host manages the Blazor Server app's lifecycle and sets up host-level services.</span></span> <span data-ttu-id="88cd8-132">Примерами таких служб являются конфигурация, ведение журнала, внедрение зависимостей и HTTP-сервер.</span><span class="sxs-lookup"><span data-stu-id="88cd8-132">Examples of such services are configuration, logging, dependency injection, and the HTTP server.</span></span> <span data-ttu-id="88cd8-133">Этот код в основном является шаблоном, и часто остается без изменений.</span><span class="sxs-lookup"><span data-stu-id="88cd8-133">This code is mostly boilerplate and is often left unchanged.</span></span>

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

<span data-ttu-id="88cd8-134">Блазор приложения веб – сборки также определяют точку входа в *Program.CS*.</span><span class="sxs-lookup"><span data-stu-id="88cd8-134">Blazor WebAssembly apps also define an entry point in *Program.cs*.</span></span> <span data-ttu-id="88cd8-135">Код выглядит немного иначе.</span><span class="sxs-lookup"><span data-stu-id="88cd8-135">The code looks slightly different.</span></span> <span data-ttu-id="88cd8-136">Код аналогичен тому, что настраивает узел приложения для предоставления приложению тех же служб уровня узла.</span><span class="sxs-lookup"><span data-stu-id="88cd8-136">The code is similar in that it's setting up the app host to provide the same host-level services to the app.</span></span> <span data-ttu-id="88cd8-137">Однако узел приложения веб-сборки не настраивает сервер HTTP, так как он выполняется непосредственно в браузере.</span><span class="sxs-lookup"><span data-stu-id="88cd8-137">The WebAssembly app host doesn't, however, set up an HTTP server because it executes directly in the browser.</span></span>

<span data-ttu-id="88cd8-138">Приложения блазор имеют `Startup` класс, а не файл *Global. asax* для определения логики запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="88cd8-138">Blazor apps have a `Startup` class instead of a *Global.asax* file to define the startup logic for the app.</span></span> <span data-ttu-id="88cd8-139">Класс `Startup` используется для настройки приложения и любых служб, зависящих от приложения.</span><span class="sxs-lookup"><span data-stu-id="88cd8-139">The `Startup` class is used to configure the app and any app-specific services.</span></span> <span data-ttu-id="88cd8-140">В приложении сервера Блазор класс `Startup` используется для настройки конечной точки для подключения в режиме реального времени, используемого Блазор между клиентскими браузерами и сервером.</span><span class="sxs-lookup"><span data-stu-id="88cd8-140">In the Blazor Server app, the `Startup` class is used to set up the endpoint for the real-time connection used by Blazor between the client browsers and the server.</span></span> <span data-ttu-id="88cd8-141">В приложении Блазор, класс `Startup` определяет корневые компоненты для приложения и место их подготовки к просмотру.</span><span class="sxs-lookup"><span data-stu-id="88cd8-141">In the Blazor WebAssembly app, the `Startup` class defines the root components for the app and where they should be rendered.</span></span> <span data-ttu-id="88cd8-142">Мы подробнее рассмотрим класс `Startup` в разделе [Запуск приложения](./app-startup.md) .</span><span class="sxs-lookup"><span data-stu-id="88cd8-142">We'll take a deeper look at the `Startup` class in the [App startup](./app-startup.md) section.</span></span>

## <a name="static-files"></a><span data-ttu-id="88cd8-143">Статические файлы</span><span class="sxs-lookup"><span data-stu-id="88cd8-143">Static files</span></span>

<span data-ttu-id="88cd8-144">В отличие от проектов веб-форм ASP.NET, не все файлы в проекте Блазор могут быть запрошены как статические файлы.</span><span class="sxs-lookup"><span data-stu-id="88cd8-144">Unlike ASP.NET Web Forms projects, not all files in a Blazor project can be requested as static files.</span></span> <span data-ttu-id="88cd8-145">Веб-адресацией могут быть только файлы в папке *wwwroot* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-145">Only the files in the *wwwroot* folder are web-addressable.</span></span> <span data-ttu-id="88cd8-146">Эта папка называется "корневым веб-приложением".</span><span class="sxs-lookup"><span data-stu-id="88cd8-146">This folder is referred to the app's "web root".</span></span> <span data-ttu-id="88cd8-147">Все, что находится за пределами корневого веб-узла приложения, *не является* веб-адресацией.</span><span class="sxs-lookup"><span data-stu-id="88cd8-147">Anything outside of the app's web root *isn't* web-addressable.</span></span> <span data-ttu-id="88cd8-148">Эта установка обеспечивает дополнительный уровень безопасности, который предотвращает случайное предоставление файлов проекта через Интернет.</span><span class="sxs-lookup"><span data-stu-id="88cd8-148">This setup provides an additional level of security that prevents accidental exposing of project files over the web.</span></span>

## <a name="configuration"></a><span data-ttu-id="88cd8-149">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="88cd8-149">Configuration</span></span>

<span data-ttu-id="88cd8-150">Конфигурация в приложениях ASP.NET Web Forms обычно обрабатывается с помощью одного или нескольких файлов *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-150">Configuration in ASP.NET Web Forms apps is typically handled using one or more *web.config* files.</span></span> <span data-ttu-id="88cd8-151">Приложения блазор обычно не имеют файлов *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-151">Blazor apps don't typically have *web.config* files.</span></span> <span data-ttu-id="88cd8-152">В противном случае файл будет использоваться только для настройки параметров IIS при размещении в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="88cd8-152">If they do, the file is only used to configure IIS-specific settings when hosted on IIS.</span></span> <span data-ttu-id="88cd8-153">Вместо этого серверные приложения Блазор используют абстракции конфигурации ASP.NET Core (приложения Блазор веб-сборки в настоящее время не поддерживают одни и те же абстракции конфигурации, но это может быть функция, добавленная в будущем).</span><span class="sxs-lookup"><span data-stu-id="88cd8-153">Instead, Blazor Server apps use the ASP.NET Core configuration abstractions (Blazor WebAssembly apps don't currently support the same configuration abstractions, but that may be a feature added in the future).</span></span> <span data-ttu-id="88cd8-154">Например, серверное приложение Блазор по умолчанию хранит некоторые параметры в *appSettings. JSON*.</span><span class="sxs-lookup"><span data-stu-id="88cd8-154">For example, the default Blazor Server app stores some settings in *appsettings.json*.</span></span>

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

<span data-ttu-id="88cd8-155">Дополнительные сведения о конфигурации в ASP.NET Core проектах см. в разделе [конфигурации](./config.md) .</span><span class="sxs-lookup"><span data-stu-id="88cd8-155">We'll learn more about configuration in ASP.NET Core projects in the [Configuration](./config.md) section.</span></span>

## <a name="razor-components"></a><span data-ttu-id="88cd8-156">Компоненты Razor</span><span class="sxs-lookup"><span data-stu-id="88cd8-156">Razor components</span></span>

<span data-ttu-id="88cd8-157">Большинство файлов в проектах Блазор — это файлы *. Razor* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-157">Most files in Blazor projects are *.razor* files.</span></span> <span data-ttu-id="88cd8-158">Razor — это язык шаблонов, основанный на C# HTML и используемый для динамического создания пользовательского веб-интерфейса.</span><span class="sxs-lookup"><span data-stu-id="88cd8-158">Razor is a templating language based on HTML and C# that is used to dynamically generate web UI.</span></span> <span data-ttu-id="88cd8-159">Файлы *. Razor* определяют компоненты, составляющие пользовательский интерфейс приложения.</span><span class="sxs-lookup"><span data-stu-id="88cd8-159">The *.razor* files define components that make up the UI of the app.</span></span> <span data-ttu-id="88cd8-160">В большинстве случаев компоненты идентичны для приложений Блазор Server и Блазор.</span><span class="sxs-lookup"><span data-stu-id="88cd8-160">For the most part, the components are identical for both the Blazor Server and Blazor WebAssembly apps.</span></span> <span data-ttu-id="88cd8-161">Компоненты в Блазор аналогичны пользовательским элементам управления в ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="88cd8-161">Components in Blazor are analogous to user controls in ASP.NET Web Forms.</span></span>

<span data-ttu-id="88cd8-162">Каждый файл компонента Razor компилируется в класс .NET при построении проекта.</span><span class="sxs-lookup"><span data-stu-id="88cd8-162">Each Razor component file is compiled into a .NET class when the project is built.</span></span> <span data-ttu-id="88cd8-163">Созданный класс захватывает состояние компонента, логику отрисовки, методы жизненного цикла, обработчики событий и другую логику.</span><span class="sxs-lookup"><span data-stu-id="88cd8-163">The generated class captures the component's state, rendering logic, lifecycle methods, event handlers, and other logic.</span></span> <span data-ttu-id="88cd8-164">Мы рассмотрим создание компонентов [пользовательского интерфейса с возможностью повторного использования](./components.md) в разделе блазор.</span><span class="sxs-lookup"><span data-stu-id="88cd8-164">We'll look at authoring components in the [Building reusable UI components with Blazor](./components.md) section.</span></span>

<span data-ttu-id="88cd8-165">Файлы *_Imports. Razor* не являются файлами компонентов Razor.</span><span class="sxs-lookup"><span data-stu-id="88cd8-165">The *_Imports.razor* files aren't Razor component files.</span></span> <span data-ttu-id="88cd8-166">Вместо этого они определяют набор директив Razor для импорта в другие файлы *Razor* в той же папке и ее вложенных папках.</span><span class="sxs-lookup"><span data-stu-id="88cd8-166">Instead, they define a set of Razor directives to import into other *.razor* files within the same folder and in its subfolders.</span></span> <span data-ttu-id="88cd8-167">Например, файл *_Imports. Razor* — это стандартный способ добавления `using`ных инструкций для часто используемых пространств имен:</span><span class="sxs-lookup"><span data-stu-id="88cd8-167">For example, a *_Imports.razor* file is a conventional way to add `using` statements for commonly used namespaces:</span></span>

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

## <a name="pages"></a><span data-ttu-id="88cd8-168">Pages</span><span class="sxs-lookup"><span data-stu-id="88cd8-168">Pages</span></span>

<span data-ttu-id="88cd8-169">Где находятся страницы в приложениях Блазор?</span><span class="sxs-lookup"><span data-stu-id="88cd8-169">Where are the pages in the Blazor apps?</span></span> <span data-ttu-id="88cd8-170">Блазор не определяет отдельное расширение файла для адресных страниц, таких как *ASPX* -файлы в приложениях ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="88cd8-170">Blazor doesn't define a separate file extension for addressable pages, like the *.aspx* files in ASP.NET Web Forms apps.</span></span> <span data-ttu-id="88cd8-171">Вместо этого страницы определяются путем назначения маршрутов компонентам.</span><span class="sxs-lookup"><span data-stu-id="88cd8-171">Instead, pages are defined by assigning routes to components.</span></span> <span data-ttu-id="88cd8-172">Маршрут обычно назначается с помощью директивы `@page` Razor.</span><span class="sxs-lookup"><span data-stu-id="88cd8-172">A route is typically assigned using the `@page` Razor directive.</span></span> <span data-ttu-id="88cd8-173">Например, компонент `Counter`, созданный в файле *pages/Counter. Razor* , определяет следующий маршрут:</span><span class="sxs-lookup"><span data-stu-id="88cd8-173">For example, the `Counter` component authored in the *Pages/Counter.razor* file defines the following route:</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="88cd8-174">Маршрутизация в Блазор обрабатывается на стороне клиента, а не на сервере.</span><span class="sxs-lookup"><span data-stu-id="88cd8-174">Routing in Blazor is handled client-side, not on the server.</span></span> <span data-ttu-id="88cd8-175">При переходе пользователя в браузере Блазор перехватывает навигацию, а затем отображает компонент с соответствующим маршрутом.</span><span class="sxs-lookup"><span data-stu-id="88cd8-175">As the user navigates in the browser, Blazor intercepts the navigation and then renders the component with the matching route.</span></span>

<span data-ttu-id="88cd8-176">Маршруты к компонентам в настоящее время не выводятся расположением файлов компонента, как и страницы *ASPX* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-176">The component routes aren't currently inferred by the component's file location like they are with *.aspx* pages.</span></span> <span data-ttu-id="88cd8-177">Эта функция может быть добавлена в будущем.</span><span class="sxs-lookup"><span data-stu-id="88cd8-177">This feature may be added in the future.</span></span> <span data-ttu-id="88cd8-178">Каждый маршрут должен быть явно указан в компоненте.</span><span class="sxs-lookup"><span data-stu-id="88cd8-178">Each route must be specified explicitly on the component.</span></span> <span data-ttu-id="88cd8-179">Хранение маршрутизируемых компонентов в папке *pages* не имеет особого смысла и является исключительно Соглашением.</span><span class="sxs-lookup"><span data-stu-id="88cd8-179">Storing routable components in a *Pages* folder has no special meaning and is purely a convention.</span></span>

<span data-ttu-id="88cd8-180">Мы более подробно рассмотрим маршрутизацию в Блазор в разделе [страницы, маршрутизация и макеты](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="88cd8-180">We'll look in greater detail at routing in Blazor in the [Pages, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="layout"></a><span data-ttu-id="88cd8-181">Макет</span><span class="sxs-lookup"><span data-stu-id="88cd8-181">Layout</span></span>

<span data-ttu-id="88cd8-182">В приложениях веб-форм ASP.NET общий макет страницы обрабатывается с помощью главных страниц (*site. master*).</span><span class="sxs-lookup"><span data-stu-id="88cd8-182">In ASP.NET Web Forms apps, common page layout is handled using master pages (*Site.Master*).</span></span> <span data-ttu-id="88cd8-183">В приложениях Блазор макет страницы обрабатывается с помощью компонентов макета (*Shared/маинлайаут. Razor*).</span><span class="sxs-lookup"><span data-stu-id="88cd8-183">In Blazor apps, page layout is handled using layout components (*Shared/MainLayout.razor*).</span></span> <span data-ttu-id="88cd8-184">Компоненты макета будут обсуждаться более подробно в разделе [страница, маршрутизация и макеты](./pages-routing-layouts.md) .</span><span class="sxs-lookup"><span data-stu-id="88cd8-184">Layout components will be discussed in more detail in [Page, routing, and layouts](./pages-routing-layouts.md) section.</span></span>

## <a name="bootstrap-blazor"></a><span data-ttu-id="88cd8-185">Блазор начальной загрузки</span><span class="sxs-lookup"><span data-stu-id="88cd8-185">Bootstrap Blazor</span></span>

<span data-ttu-id="88cd8-186">Для начальной загрузки Блазор приложение должно:</span><span class="sxs-lookup"><span data-stu-id="88cd8-186">To bootstrap Blazor, the app must:</span></span>

- <span data-ttu-id="88cd8-187">Укажите, где на странице следует визуализировать корневой компонент (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="88cd8-187">Specify where on the page the root component (*App.Razor*) should be rendered.</span></span>
- <span data-ttu-id="88cd8-188">Добавьте соответствующий скрипт Блазор Framework.</span><span class="sxs-lookup"><span data-stu-id="88cd8-188">Add the corresponding Blazor framework script.</span></span>

<span data-ttu-id="88cd8-189">В приложении Блазор Server страница узла корневого компонента определена в файле *_Host. cshtml* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-189">In the Blazor Server app, the root component's host page is defined in the *_Host.cshtml* file.</span></span> <span data-ttu-id="88cd8-190">Этот файл определяет страницу Razor, а не компонент.</span><span class="sxs-lookup"><span data-stu-id="88cd8-190">This file defines a Razor Page, not a component.</span></span> <span data-ttu-id="88cd8-191">Razor Pages использовать синтаксис Razor для определения серверной страницы, которая во многом аналогична странице *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="88cd8-191">Razor Pages use Razor syntax to define a server-addressable page, very much like an *.aspx* page.</span></span> <span data-ttu-id="88cd8-192">Метод `Html.RenderComponentAsync<TComponent>(RenderMode)` используется для определения места отрисовки компонента корневого уровня.</span><span class="sxs-lookup"><span data-stu-id="88cd8-192">The `Html.RenderComponentAsync<TComponent>(RenderMode)` method is used to define where a root-level component should be rendered.</span></span> <span data-ttu-id="88cd8-193">Параметр `RenderMode` указывает способ подготовки компонента к просмотру.</span><span class="sxs-lookup"><span data-stu-id="88cd8-193">The `RenderMode` option indicates the manner in which the component should be rendered.</span></span> <span data-ttu-id="88cd8-194">В следующей таблице приведены поддерживаемые параметры `RenderMode`.</span><span class="sxs-lookup"><span data-stu-id="88cd8-194">The following table outlines the supported `RenderMode` options.</span></span>

|<span data-ttu-id="88cd8-195">Параметр</span><span class="sxs-lookup"><span data-stu-id="88cd8-195">Option</span></span>                        |<span data-ttu-id="88cd8-196">Описание</span><span class="sxs-lookup"><span data-stu-id="88cd8-196">Description</span></span>       |
|------------------------------|------------------|
|`RenderMode.Server`           |<span data-ttu-id="88cd8-197">Интерактивный просмотр после установки соединения с браузером</span><span class="sxs-lookup"><span data-stu-id="88cd8-197">Rendered interactively once a connection with the browser is established</span></span>|
|`RenderMode.ServerPrerendered`|<span data-ttu-id="88cd8-198">Первая предварительно визуализированная и отображаемая в интерактивном режиме</span><span class="sxs-lookup"><span data-stu-id="88cd8-198">First prerendered and then rendered interactively</span></span>|
|`RenderMode.Static`           |<span data-ttu-id="88cd8-199">Отображается как статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="88cd8-199">Rendered as static content</span></span>|

<span data-ttu-id="88cd8-200">Ссылка на скрипт для *_framework/блазор.сервер.ЖС* устанавливает подключение к серверу в режиме реального времени, а затем обрабатывает все взаимодействия с пользователем и обновления пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="88cd8-200">The script reference to *_framework/blazor.server.js* establishes the real-time connection with the server and then deals with all user interactions and UI updates.</span></span>

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

<span data-ttu-id="88cd8-201">В приложении Блазор веб-сборки страница узла представляет собой простой статический HTML-файл в разделе *wwwroot/index.HTML*.</span><span class="sxs-lookup"><span data-stu-id="88cd8-201">In the Blazor WebAssembly app, the host page is a simple static HTML file under *wwwroot/index.html*.</span></span> <span data-ttu-id="88cd8-202">Элемент `<app>` используется для указания места, где должен быть визуализирован корневой компонент.</span><span class="sxs-lookup"><span data-stu-id="88cd8-202">The `<app>` element is used to indicate where the root component should be rendered.</span></span>

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

<span data-ttu-id="88cd8-203">Конкретный компонент для подготовки к просмотру настраивается в методе `Startup.Configure` приложения с соответствующим селектором CSS, указывающим, где должен быть визуализирован компонент.</span><span class="sxs-lookup"><span data-stu-id="88cd8-203">The specific component to render is configured in the app's `Startup.Configure` method with a corresponding CSS selector indicating where the component should be rendered.</span></span>

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

## <a name="build-output"></a><span data-ttu-id="88cd8-204">Выходные данные сборки</span><span class="sxs-lookup"><span data-stu-id="88cd8-204">Build output</span></span>

<span data-ttu-id="88cd8-205">При сборке проекта Блазор все файлы компонента и кода Razor компилируются в одну сборку.</span><span class="sxs-lookup"><span data-stu-id="88cd8-205">When a Blazor project is built, all Razor component and code files are compiled into a single assembly.</span></span> <span data-ttu-id="88cd8-206">В отличие от проектов веб-форм ASP.NET, Блазор не поддерживает компиляцию логики пользовательского интерфейса во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88cd8-206">Unlike ASP.NET Web Forms projects, Blazor doesn't support runtime compilation of the UI logic.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="88cd8-207">Запуск приложения</span><span class="sxs-lookup"><span data-stu-id="88cd8-207">Run the app</span></span>

<span data-ttu-id="88cd8-208">Чтобы запустить приложение Блазор Server, нажмите в Visual Studio кнопку `F5`.</span><span class="sxs-lookup"><span data-stu-id="88cd8-208">To run the Blazor Server app, press `F5` in Visual Studio.</span></span> <span data-ttu-id="88cd8-209">Приложения блазор не поддерживают компиляцию во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="88cd8-209">Blazor apps don't support runtime compilation.</span></span> <span data-ttu-id="88cd8-210">Чтобы просмотреть результаты изменений разметки кода и компонентов, перестройте и перезапустите приложение с подключенным отладчиком.</span><span class="sxs-lookup"><span data-stu-id="88cd8-210">To see the results of code and component markup changes, rebuild and restart the app with the debugger attached.</span></span> <span data-ttu-id="88cd8-211">При запуске без подключения отладчика (`Ctrl+F5`) Visual Studio наблюдает за изменениями файлов и перезапускает приложение при внесении изменений.</span><span class="sxs-lookup"><span data-stu-id="88cd8-211">If you run without the debugger attached (`Ctrl+F5`), Visual Studio watches for file changes and restarts the app as changes are made.</span></span> <span data-ttu-id="88cd8-212">Вы вручную обновляете браузер по мере внесения изменений.</span><span class="sxs-lookup"><span data-stu-id="88cd8-212">You manually refresh the browser as changes are made.</span></span>

<span data-ttu-id="88cd8-213">Чтобы запустить приложение Блазор сборки, выберите один из следующих подходов:</span><span class="sxs-lookup"><span data-stu-id="88cd8-213">To run the Blazor WebAssembly app, choose one of the following approaches:</span></span>

- <span data-ttu-id="88cd8-214">Запустите клиентский проект непосредственно с помощью сервера разработки.</span><span class="sxs-lookup"><span data-stu-id="88cd8-214">Run the client project directly using the development server.</span></span>
- <span data-ttu-id="88cd8-215">Запустите серверный проект при размещении приложения с ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="88cd8-215">Run the server project when hosting the app with ASP.NET Core.</span></span>

<span data-ttu-id="88cd8-216">Приложения блазор сборки не поддерживают отладку с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="88cd8-216">Blazor WebAssembly apps don't support debugging using Visual Studio.</span></span> <span data-ttu-id="88cd8-217">Чтобы запустить приложение, используйте `Ctrl+F5` вместо `F5`.</span><span class="sxs-lookup"><span data-stu-id="88cd8-217">To run the app, use `Ctrl+F5` instead of `F5`.</span></span> <span data-ttu-id="88cd8-218">Вместо этого можно отлаживать приложения Блазор в браузере напрямую.</span><span class="sxs-lookup"><span data-stu-id="88cd8-218">You can instead debug Blazor WebAssembly apps directly in the browser.</span></span> <span data-ttu-id="88cd8-219">Дополнительные сведения см. в разделе [Debug ASP.NET Core блазор](/aspnet/core/blazor/debug) .</span><span class="sxs-lookup"><span data-stu-id="88cd8-219">See [Debug ASP.NET Core Blazor](/aspnet/core/blazor/debug) for details.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="88cd8-220">[Назад](hosting-models.md)
>[Вперед](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="88cd8-220">[Previous](hosting-models.md)
[Next](app-startup.md)</span></span>
