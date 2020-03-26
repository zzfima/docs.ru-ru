---
title: Мигрировать из веб-форм ASP.NET в Blazor
description: Узнайте, как подойти к переходу к существующему приложению ASP.NET веб-форм в Blazor.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: 0a10a9a3d5ab32e16cb59a68da57116e20c53e49
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80134093"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a><span data-ttu-id="f047b-103">Мигрировать из веб-форм ASP.NET в Blazor</span><span class="sxs-lookup"><span data-stu-id="f047b-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="f047b-104">Миграция базы кода из веб-форм ASP.NET в Blazor является трудоемкой задачей, требующей планирования.</span><span class="sxs-lookup"><span data-stu-id="f047b-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="f047b-105">В этой главе излагается процесс.</span><span class="sxs-lookup"><span data-stu-id="f047b-105">This chapter outlines the process.</span></span> <span data-ttu-id="f047b-106">Что-то, что может облегчить переход, заключается в том, чтобы обеспечить соответствие приложения архитектуре *N-уровня,* в которой модель приложения (в данном случае Web Forms) отделена от бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="f047b-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="f047b-107">Это логическое разделение слоев дает понять, что нужно перейти к .NET Core и Blazor.</span><span class="sxs-lookup"><span data-stu-id="f047b-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="f047b-108">В этом примере используется приложение eShop, доступное на [GitHub.](https://github.com/dotnet-architecture/eShopOnBlazor)</span><span class="sxs-lookup"><span data-stu-id="f047b-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="f047b-109">eShop — это сервис каталога, предоставляющий возможности CRUD с помощью ввода формы и проверки.</span><span class="sxs-lookup"><span data-stu-id="f047b-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="f047b-110">Почему рабочее приложение должно быть перенесено в Blazor?</span><span class="sxs-lookup"><span data-stu-id="f047b-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="f047b-111">Много раз, нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="f047b-111">Many times, there's no need.</span></span> <span data-ttu-id="f047b-112">ASP.NET веб-формы будут поддерживаться в течение многих лет.</span><span class="sxs-lookup"><span data-stu-id="f047b-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="f047b-113">Однако многие функции, которые предоставляет Blazor, поддерживаются только в мигрировавом приложении.</span><span class="sxs-lookup"><span data-stu-id="f047b-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="f047b-114">К таким функциям относятся:</span><span class="sxs-lookup"><span data-stu-id="f047b-114">Such features include:</span></span>

- <span data-ttu-id="f047b-115">Улучшения производительности в таких рамках, как`Span<T>`</span><span class="sxs-lookup"><span data-stu-id="f047b-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="f047b-116">Возможность работать как Веб-сборка</span><span class="sxs-lookup"><span data-stu-id="f047b-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="f047b-117">Кросс-платформная поддержка Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="f047b-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="f047b-118">Развертывание локального приложения или совместное развертывание инфраструктуры без влияния на другие приложения</span><span class="sxs-lookup"><span data-stu-id="f047b-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="f047b-119">Если эти или другие новые функции являются достаточно убедительными, может быть значение в миграции приложения.</span><span class="sxs-lookup"><span data-stu-id="f047b-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="f047b-120">Миграция может принимать различные формы; это может быть все приложение, или только определенные конечные точки, которые требуют изменений.</span><span class="sxs-lookup"><span data-stu-id="f047b-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="f047b-121">Решение о миграции в конечном счете основано на бизнес-проблемах, которые должен быть решен разработчиком.</span><span class="sxs-lookup"><span data-stu-id="f047b-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="f047b-122">Серверная сторона по сравнению с хостингом на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="f047b-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="f047b-123">Как описано в главе [моделей хостинга,](hosting-models.md) приложение Blazor может быть размещено двумя различными способами: серверной и клиентской.</span><span class="sxs-lookup"><span data-stu-id="f047b-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="f047b-124">Модель сервера использует ASP.NET core SignalR соединения для управления обновлениями DOM при запуске любого фактического кода на сервере.</span><span class="sxs-lookup"><span data-stu-id="f047b-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="f047b-125">Модель клиентской стороны выполняется как WebAssembly в браузере и не требует подключения к серверу.</span><span class="sxs-lookup"><span data-stu-id="f047b-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="f047b-126">Есть ряд отличий, которые могут повлиять на то, что лучше всего подходит для конкретного приложения:</span><span class="sxs-lookup"><span data-stu-id="f047b-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="f047b-127">Запуск WebAssembly все еще находится в разработке и может не поддерживать все функции (например, потоков) в настоящее время</span><span class="sxs-lookup"><span data-stu-id="f047b-127">Running as WebAssembly is still in development and may not support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="f047b-128">Чаттая связь между клиентом и сервером может вызвать проблемы с задержкой в режиме сервера</span><span class="sxs-lookup"><span data-stu-id="f047b-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="f047b-129">Доступ к базам данных и внутренним или защищенным службам требует отдельной службы с хостингом на стороне клиента</span><span class="sxs-lookup"><span data-stu-id="f047b-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="f047b-130">На момент написания статьи модель сервера больше напоминает веб-формы.</span><span class="sxs-lookup"><span data-stu-id="f047b-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="f047b-131">Большая часть этой главы посвящена модели хостинга на стороне сервера, так как она готова к производству.</span><span class="sxs-lookup"><span data-stu-id="f047b-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="f047b-132">Создание нового проекта</span><span class="sxs-lookup"><span data-stu-id="f047b-132">Create a new project</span></span>

<span data-ttu-id="f047b-133">Этот первоначальный шаг миграции заключается в создании нового проекта.</span><span class="sxs-lookup"><span data-stu-id="f047b-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="f047b-134">Этот тип проекта основан на проектах стиля SDK .NET Core и упрощает большую часть шаблона, который использовался в предыдущих форматах проектов.</span><span class="sxs-lookup"><span data-stu-id="f047b-134">This project type is based on the SDK style projects of .NET Core and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="f047b-135">Для получения более подробной информации, пожалуйста, смотрите главу о [структуре проекта](project-structure.md).</span><span class="sxs-lookup"><span data-stu-id="f047b-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="f047b-136">Как только проект был создан, установите библиотеки, которые использовались в предыдущем проекте.</span><span class="sxs-lookup"><span data-stu-id="f047b-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="f047b-137">В старых проектах Web Forms вы, возможно, использовали файл *packages.config* для списка необходимых пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="f047b-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="f047b-138">В новом проекте в стиле SDK *packages.config* был заменен `<PackageReference>` элементами в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="f047b-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="f047b-139">Преимущество этого подхода заключается в том, что все зависимости устанавливаются транзитно.</span><span class="sxs-lookup"><span data-stu-id="f047b-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="f047b-140">Вы перечисляете только зависимые от верхнего уровня зависимости.</span><span class="sxs-lookup"><span data-stu-id="f047b-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="f047b-141">Многие из использовавшихся зависимостей доступны для .NET Core, включая систему entity 6 и log4net.</span><span class="sxs-lookup"><span data-stu-id="f047b-141">Many of the dependencies you're using are available for .NET Core, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="f047b-142">Если нет стандартной версии .NET Core или .NET, часто можно использовать рамочную версию .NET.</span><span class="sxs-lookup"><span data-stu-id="f047b-142">If there's no .NET Core or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="f047b-143">Ваш пробег может варьироваться.</span><span class="sxs-lookup"><span data-stu-id="f047b-143">Your mileage may vary.</span></span> <span data-ttu-id="f047b-144">Любой используемый API, недоступен в .NET Core, вызывает ошибку в времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="f047b-144">Any API used that isn't available in .NET Core causes a runtime error.</span></span> <span data-ttu-id="f047b-145">Visual Studio уведомляет вас о таких пакетах.</span><span class="sxs-lookup"><span data-stu-id="f047b-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="f047b-146">На узло **ссылки** проекта в Solution **Explorer**появляется желтая иконка.</span><span class="sxs-lookup"><span data-stu-id="f047b-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="f047b-147">В проекте blazor на основе eShop можно увидеть установленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="f047b-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="f047b-148">Ранее файл *packages.config* перечислял каждый пакет, используемый в проекте, в результате чего файл длиной почти 50 строк.</span><span class="sxs-lookup"><span data-stu-id="f047b-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="f047b-149">Фрагмент *packages.config:*</span><span class="sxs-lookup"><span data-stu-id="f047b-149">A snippet of *packages.config* is:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<packages>
  ...
  <package id="Microsoft.ApplicationInsights.Agent.Intercept" version="2.4.0" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.DependencyCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.PerfCounterCollector" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.Web" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.ApplicationInsights.WindowsServer.TelemetryChannel" version="2.9.1" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.FriendlyUrls.Core" version="1.0.2" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.MSAjax" version="5.0.0" targetFramework="net472" />
  <package id="Microsoft.AspNet.ScriptManager.WebForms" version="5.0.0" targetFramework="net472" />
  ...
  <package id="System.Memory" version="4.5.1" targetFramework="net472" />
  <package id="System.Numerics.Vectors" version="4.4.0" targetFramework="net472" />
  <package id="System.Runtime.CompilerServices.Unsafe" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Channels" version="4.5.0" targetFramework="net472" />
  <package id="System.Threading.Tasks.Extensions" version="4.5.1" targetFramework="net472" />
  <package id="WebGrease" version="1.6.0" targetFramework="net472" />
</packages>
```

<span data-ttu-id="f047b-150">Элемент `<packages>` включает в себя все необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="f047b-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="f047b-151">Трудно определить, какие из этих пакетов включены, потому что вы требуете их.</span><span class="sxs-lookup"><span data-stu-id="f047b-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="f047b-152">Некоторые `<package>` элементы перечислены просто для удовлетворения потребностей зависимостей, которые вам необходимы.</span><span class="sxs-lookup"><span data-stu-id="f047b-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="f047b-153">Проект Blazor перечисляет требуемые `<ItemGroup>` зависимости в элементе файла проекта:</span><span class="sxs-lookup"><span data-stu-id="f047b-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

<span data-ttu-id="f047b-154">Один пакет NuGet, который упрощает жизнь разработчиков Web Forms, — это [пакет совместимости Windows.](../../core/porting/windows-compat-pack.md)</span><span class="sxs-lookup"><span data-stu-id="f047b-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="f047b-155">Хотя .NET Core является кросс-платформенным, некоторые функции доступны только на Windows.</span><span class="sxs-lookup"><span data-stu-id="f047b-155">Although .NET Core is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="f047b-156">Особенности Windows становятся доступными, устанавливая пакет совместимости.</span><span class="sxs-lookup"><span data-stu-id="f047b-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="f047b-157">Примерами таких функций являются Службы регистрации, WMI и Справочник.</span><span class="sxs-lookup"><span data-stu-id="f047b-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="f047b-158">Пакет добавляет около 20 000 AA и активирует множество сервисов, с которыми вы, возможно, уже знакомы.</span><span class="sxs-lookup"><span data-stu-id="f047b-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="f047b-159">Проект eShop не требует пакета совместимости; но если в ваших проектах используются специфические функции Windows, пакет облегчает усилия по миграции.</span><span class="sxs-lookup"><span data-stu-id="f047b-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="f047b-160">Включить процесс запуска</span><span class="sxs-lookup"><span data-stu-id="f047b-160">Enable startup process</span></span>

<span data-ttu-id="f047b-161">Процесс запуска Blazor изменился с Web Forms и следует аналогичной настройке для других ASP.NET основных услуг.</span><span class="sxs-lookup"><span data-stu-id="f047b-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="f047b-162">При размещении сервера компоненты Blazor запускаются как часть обычного приложения ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f047b-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="f047b-163">При размещении в браузере с WebAssembly, компоненты Blazor используют аналогичную модель хостинга.</span><span class="sxs-lookup"><span data-stu-id="f047b-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="f047b-164">Разница в том, что компоненты работают как отдельная служба от любого из процессов бэкэнда.</span><span class="sxs-lookup"><span data-stu-id="f047b-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="f047b-165">В любом случае, стартап похож.</span><span class="sxs-lookup"><span data-stu-id="f047b-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="f047b-166">*Файл Global.asax.cs* — это страница запуска по умолчанию для проектов Web-форм.</span><span class="sxs-lookup"><span data-stu-id="f047b-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="f047b-167">В проекте eShop этот файл настраивает контейнер Inversion of Control (IoC) и обрабатывает различные события жизненного цикла приложения или запроса.</span><span class="sxs-lookup"><span data-stu-id="f047b-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="f047b-168">Некоторые из этих событий обрабатываются с `Application_BeginRequest`помощью промежуточного посуды (например, ).</span><span class="sxs-lookup"><span data-stu-id="f047b-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="f047b-169">Другие события требуют переопределения конкретных служб с помощью инъекций зависимости (DI).</span><span class="sxs-lookup"><span data-stu-id="f047b-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="f047b-170">Например, *Global.asax.cs* файл для eShop содержит следующий код:</span><span class="sxs-lookup"><span data-stu-id="f047b-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

```csharp
public class Global : HttpApplication, IContainerProviderAccessor
{
    private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

    static IContainerProvider _containerProvider;
    IContainer container;

    public IContainerProvider ContainerProvider
    {
        get { return _containerProvider; }
    }

    protected void Application_Start(object sender, EventArgs e)
    {
        // Code that runs on app startup
        RouteConfig.RegisterRoutes(RouteTable.Routes);
        BundleConfig.RegisterBundles(BundleTable.Bundles);
        ConfigureContainer();
        ConfigDataBase();
    }

    /// <summary>
    /// Track the machine name and the start time for the session inside the current session
    /// </summary>
    protected void Session_Start(Object sender, EventArgs e)
    {
        HttpContext.Current.Session["MachineName"] = Environment.MachineName;
        HttpContext.Current.Session["SessionStartTime"] = DateTime.Now;
    }

    /// <summary>
    /// http://docs.autofac.org/en/latest/integration/webforms.html
    /// </summary>
    private void ConfigureContainer()
    {
        var builder = new ContainerBuilder();
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);
        builder.RegisterModule(new ApplicationModule(mockData));
        container = builder.Build();
        _containerProvider = new ContainerProvider(container);
    }

    private void ConfigDataBase()
    {
        var mockData = bool.Parse(ConfigurationManager.AppSettings["UseMockData"]);

        if (!mockData)
        {
            Database.SetInitializer<CatalogDBContext>(container.Resolve<CatalogDBInitializer>());
        }
    }

    protected void Application_BeginRequest(object sender, EventArgs e)
    {
        //set the property to our new object
        LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper();

        LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo();

        _log.Debug("Application_BeginRequest");
    }
}
```

<span data-ttu-id="f047b-171">Предыдущий файл `Startup` становится классом в серверной стороне Blazor:</span><span class="sxs-lookup"><span data-stu-id="f047b-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    public IConfiguration Configuration { get; }

    public IWebHostEnvironment Env { get; }

    // This method gets called by the runtime. Use this method to add services to the container.
    // For more information on how to configure your application, visit https://go.microsoft.com/fwlink/?LinkID=398940
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddRazorPages();
        services.AddServerSideBlazor();

        if (Configuration.GetValue<bool>("UseMockData"))
        {
            services.AddSingleton<ICatalogService, CatalogServiceMock>();
        }
        else
        {
            services.AddScoped<ICatalogService, CatalogService>();
            services.AddScoped<IDatabaseInitializer<CatalogDBContext>, CatalogDBInitializer>();
            services.AddSingleton<CatalogItemHiLoGenerator>();
            services.AddScoped(_ => new CatalogDBContext(Configuration.GetConnectionString("CatalogDBContext")));
        }
    }

    // This method gets called by the runtime. Use this method to configure the HTTP request pipeline.
    public void Configure(IApplicationBuilder app, ILoggerFactory loggerFactory)
    {
        loggerFactory.AddLog4Net("log4Net.xml");

        if (Env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }
        else
        {
            app.UseExceptionHandler("/Home/Error");
        }

        // Middleware for Application_BeginRequest
        app.Use((ctx, next) =>
        {
            LogicalThreadContext.Properties["activityid"] = new ActivityIdHelper(ctx);
            LogicalThreadContext.Properties["requestinfo"] = new WebRequestInfo(ctx);
            return next();
        });

        app.UseStaticFiles();

        app.UseRouting();

        app.UseEndpoints(endpoints =>
        {
            endpoints.MapBlazorHub();
            endpoints.MapFallbackToPage("/_Host");
        });

        ConfigDataBase(app);
    }

    private void ConfigDataBase(IApplicationBuilder app)
    {
        using (var scope = app.ApplicationServices.CreateScope())
        {
            var initializer = scope.ServiceProvider.GetService<IDatabaseInitializer<CatalogDBContext>>();

            if (initializer != null)
            {
                Database.SetInitializer(initializer);
            }
        }
    }
}
```

<span data-ttu-id="f047b-172">Одним из существенных изменений, которые вы можете заметить из web-форм, является известность DI.</span><span class="sxs-lookup"><span data-stu-id="f047b-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="f047b-173">DI был руководящим принципом в ASP.NET Core дизайн.</span><span class="sxs-lookup"><span data-stu-id="f047b-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="f047b-174">Он поддерживает настройку почти всех аспектов ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f047b-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="f047b-175">Есть даже встроенный поставщик услуг, который может быть использован для многих сценариев.</span><span class="sxs-lookup"><span data-stu-id="f047b-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="f047b-176">Если требуется дополнительная настройка, она может быть поддержана многими проектами сообщества.</span><span class="sxs-lookup"><span data-stu-id="f047b-176">If more customization is required, it can be supported by the many community projects.</span></span> <span data-ttu-id="f047b-177">Например, вы можете продолжить инвестиции в библиотеку DI сторонних сторонних стран.</span><span class="sxs-lookup"><span data-stu-id="f047b-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="f047b-178">В оригинальном приложении eShop есть некоторая конфигурация для управления сеансами.</span><span class="sxs-lookup"><span data-stu-id="f047b-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="f047b-179">Поскольку серверная сторона Blazor использует ASP.NET Core SignalR для связи, состояние сеанса не поддерживается, поскольку соединения могут возникать независимо от контекста HTTP.</span><span class="sxs-lookup"><span data-stu-id="f047b-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="f047b-180">Приложение, использующего состояние сеанса, требует реархиринга перед запуском в качестве приложения Blazor.</span><span class="sxs-lookup"><span data-stu-id="f047b-180">An app that uses session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="f047b-181">Для получения дополнительной информации о запуске приложения, [см.](app-startup.md)</span><span class="sxs-lookup"><span data-stu-id="f047b-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="f047b-182">Мигрируйте модули и обработчики HTTP в промежуточное программное обеспечение</span><span class="sxs-lookup"><span data-stu-id="f047b-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="f047b-183">Модули и обработчики HTTP являются общими шаблонами в веб-формах для управления конвейером запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="f047b-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="f047b-184">Классы, `IHttpModule` `IHttpHandler` которые реализуют или могут быть зарегистрированы и обрабатывать входящие запросы.</span><span class="sxs-lookup"><span data-stu-id="f047b-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="f047b-185">Web Forms настраивает модули и обработчики в файле *web.config.*</span><span class="sxs-lookup"><span data-stu-id="f047b-185">Web Forms configures modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="f047b-186">Веб-формы также в значительной степени основаны на обработке событий жизненного цикла приложения.</span><span class="sxs-lookup"><span data-stu-id="f047b-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="f047b-187">ASP.NET Core использует вместо этого промежуточное программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="f047b-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="f047b-188">Среднее посуды `Configure` зарегистрировано `Startup` в методе класса.</span><span class="sxs-lookup"><span data-stu-id="f047b-188">Middleware is registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="f047b-189">Порядок исполнения Middleware определяется порядком регистрации.</span><span class="sxs-lookup"><span data-stu-id="f047b-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="f047b-190">В разделе [Процесс запуска Включить](#enable-startup-process) событие жизненного цикла было `Application_BeginRequest` поднято Web Forms в качестве метода.</span><span class="sxs-lookup"><span data-stu-id="f047b-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="f047b-191">Это событие недоступно в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f047b-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="f047b-192">Одним из способов достижения такого поведения является реализация промежуточного посуды, как видно из примера *Startup.cs* файла.</span><span class="sxs-lookup"><span data-stu-id="f047b-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="f047b-193">Это промежуточное программное обеспечение выполняет ту же логику, а затем передает управление следующему обработчику в промежуточном конвейере.</span><span class="sxs-lookup"><span data-stu-id="f047b-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="f047b-194">Для получения дополнительной информации о мигрирующих модулях и обработчиках см. [Мигрировать обработчики и модули HTTP, чтобы ASP.NET Core middleware.](/aspnet/core/migration/http-modules)</span><span class="sxs-lookup"><span data-stu-id="f047b-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="f047b-195">Мигрировать статические файлы</span><span class="sxs-lookup"><span data-stu-id="f047b-195">Migrate static files</span></span>

<span data-ttu-id="f047b-196">Для обслуживания статических файлов (например, HTML, CSS, изображений и JavaScript) файлы должны быть выставлены попромежутоным программным обеспечением.</span><span class="sxs-lookup"><span data-stu-id="f047b-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="f047b-197">Вызов `UseStaticFiles` метода позволяет служить статических файлов из пути корней в Интернете.</span><span class="sxs-lookup"><span data-stu-id="f047b-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="f047b-198">Каталог корней веб-страниц по умолчанию — *это wwwroot,* но его можно настроить.</span><span class="sxs-lookup"><span data-stu-id="f047b-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="f047b-199">Как включено `Configure` в метод `Startup` класса eShop:</span><span class="sxs-lookup"><span data-stu-id="f047b-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="f047b-200">Проект eShop обеспечивает базовый статический доступ к файлам.</span><span class="sxs-lookup"><span data-stu-id="f047b-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="f047b-201">Есть много настроек, доступных для статического доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="f047b-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="f047b-202">Для получения информации о включении файлов по умолчанию или файлового браузера, см [ASP.NET.](/aspnet/core/fundamentals/static-files)</span><span class="sxs-lookup"><span data-stu-id="f047b-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="f047b-203">Мигрировать настройки комплектации и минификации времени выполнения</span><span class="sxs-lookup"><span data-stu-id="f047b-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="f047b-204">Объединение и минификация являются методами оптимизации производительности для уменьшения числа и размера запросов серверов для получения определенных типов файлов.</span><span class="sxs-lookup"><span data-stu-id="f047b-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="f047b-205">JavaScript и CSS часто проходят ту или иную форму комплектации или минификации перед отправкой клиенту.</span><span class="sxs-lookup"><span data-stu-id="f047b-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="f047b-206">В ASP.NET веб-формах эти оптимизации обрабатываются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f047b-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="f047b-207">Конвенции оптимизации определяются *как файл App_Start/BundleConfig.cs.*</span><span class="sxs-lookup"><span data-stu-id="f047b-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="f047b-208">В ASP.NET Core принят более декларативный подход.</span><span class="sxs-lookup"><span data-stu-id="f047b-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="f047b-209">Файл перечисляет файлы, которые необходимо обыграть, а также определенные настройки минификации.</span><span class="sxs-lookup"><span data-stu-id="f047b-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="f047b-210">Для получения дополнительной информации о комплектации и минификации [см. Bundle и минимифицировать статические активы в ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="f047b-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="f047b-211">Мигрировать страницы ASPX</span><span class="sxs-lookup"><span data-stu-id="f047b-211">Migrate ASPX pages</span></span>

<span data-ttu-id="f047b-212">Страница в приложении Web Forms — это файл с расширением *.aspx.*</span><span class="sxs-lookup"><span data-stu-id="f047b-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="f047b-213">Страница веб-форм часто может быть отображана с компонентом Blazor.</span><span class="sxs-lookup"><span data-stu-id="f047b-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="f047b-214">Компонент Blazor авторизуется в файле с расширением *.razor.*</span><span class="sxs-lookup"><span data-stu-id="f047b-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="f047b-215">Для проекта eShop пять страниц преобразуются на страницу Razor.</span><span class="sxs-lookup"><span data-stu-id="f047b-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="f047b-216">Например, представление деталей состоит из трех файлов в проекте Web Forms: *Details.aspx,* *Details.aspx.cs*и *Details.aspx.designer.cs.*</span><span class="sxs-lookup"><span data-stu-id="f047b-216">For example, the details view is comprised of three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="f047b-217">При переходе в Blazor код сзади и разметку объединяются в *Details.razor*.</span><span class="sxs-lookup"><span data-stu-id="f047b-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="f047b-218">Компиляция razor (эквивалент того, что находится в *файлах .designer.cs)* хранится в каталоге *obj* и по умолчанию не просматривается в **Solution Explorer.**</span><span class="sxs-lookup"><span data-stu-id="f047b-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and aren't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="f047b-219">Страница веб-форм состоит из следующей разметки:</span><span class="sxs-lookup"><span data-stu-id="f047b-219">The Web Forms page consists of the following markup:</span></span>

```aspx-csharp
<%@ Page Title="Details" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Details.aspx.cs" Inherits="eShopLegacyWebForms.Catalog.Details" %>

<asp:Content ID="Details" ContentPlaceHolderID="MainContent" runat="server">
    <h2 class="esh-body-title">Details</h2>

    <div class="container">
        <div class="row">
            <asp:Image runat="server" CssClass="col-md-6 esh-picture" ImageUrl='<%#"/Pics/" + product.PictureFileName%>' />
            <dl class="col-md-6 dl-horizontal">
                <dt>Name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Name%>' />
                </dd>

                <dt>Description
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.Description%>' />
                </dd>

                <dt>Brand
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogBrand.Brand%>' />
                </dd>

                <dt>Type
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.CatalogType.Type%>' />
                </dd>
                <dt>Price
                </dt>

                <dd>
                    <asp:Label CssClass="esh-price" runat="server" Text='<%#product.Price%>' />
                </dd>

                <dt>Picture name
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.PictureFileName%>' />
                </dd>

                <dt>Stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.AvailableStock%>' />
                </dd>

                <dt>Restock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.RestockThreshold%>' />
                </dd>

                <dt>Max stock
                </dt>

                <dd>
                    <asp:Label runat="server" Text='<%#product.MaxStockThreshold%>' />
                </dd>

            </dl>
        </div>

        <div class="form-actions no-color esh-link-list">
            <a runat="server" href='<%# GetRouteUrl("EditProductRoute", new {id =product.Id}) %>' class="esh-link-item">Edit
            </a>
            |
            <a runat="server" href="~" class="esh-link-item">Back to list
            </a>
        </div>

    </div>
</asp:Content>
```

<span data-ttu-id="f047b-220">Код-задняя часть предыдущей разметки включает в себя следующий код:</span><span class="sxs-lookup"><span data-stu-id="f047b-220">The preceding markup's code-behind includes the following code:</span></span>

```csharp
using eShopLegacyWebForms.Models;
using eShopLegacyWebForms.Services;
using log4net;
using System;
using System.Web.UI;

namespace eShopLegacyWebForms.Catalog
{
    public partial class Details : System.Web.UI.Page
    {
        private static readonly ILog _log = LogManager.GetLogger(System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        protected CatalogItem product;

        public ICatalogService CatalogService { get; set; }

        protected void Page_Load(object sender, EventArgs e)
        {
            var productId = Convert.ToInt32(Page.RouteData.Values["id"]);
            _log.Info($"Now loading... /Catalog/Details.aspx?id={productId}");
            product = CatalogService.FindCatalogItem(productId);

            this.DataBind();
        }
    }
}
```

<span data-ttu-id="f047b-221">При преобразовании в Blazor страница Web Forms переводится на следующий код:</span><span class="sxs-lookup"><span data-stu-id="f047b-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

```razor
@page "/Catalog/Details/{id:int}"
@inject ICatalogService CatalogService
@inject ILogger<Details> Logger

<h2 class="esh-body-title">Details</h2>

<div class="container">
    <div class="row">
        <img class="col-md-6 esh-picture" src="@($"/Pics/{_item.PictureFileName}")">

        <dl class="col-md-6 dl-horizontal">
            <dt>
                Name
            </dt>

            <dd>
                @_item.Name
            </dd>

            <dt>
                Description
            </dt>

            <dd>
                @_item.Description
            </dd>

            <dt>
                Brand
            </dt>

            <dd>
                @_item.CatalogBrand.Brand
            </dd>

            <dt>
                Type
            </dt>

            <dd>
                @_item.CatalogType.Type
            </dd>
            <dt>
                Price
            </dt>

            <dd>
                @_item.Price
            </dd>

            <dt>
                Picture name
            </dt>

            <dd>
                @_item.PictureFileName
            </dd>

            <dt>
                Stock
            </dt>

            <dd>
                @_item.AvailableStock
            </dd>

            <dt>
                Restock
            </dt>

            <dd>
                @_item.RestockThreshold
            </dd>

            <dt>
                Max stock
            </dt>

            <dd>
                @_item.MaxStockThreshold
            </dd>

        </dl>
    </div>

    <div class="form-actions no-color esh-link-list">
        <a href="@($"/Catalog/Edit/{_item.Id}")" class="esh-link-item">
            Edit
        </a>
        |
        <a href="/" class="esh-link-item">
            Back to list
        </a>
    </div>

</div>

@code {
    private CatalogItem _item;

    [Parameter]
    public int Id { get; set; }

    protected override void OnInitialized()
    {
        Logger.LogInformation("Now loading... /Catalog/Details/{Id}", Id);

        _item = CatalogService.FindCatalogItem(Id);
    }
}
```

<span data-ttu-id="f047b-222">Обратите внимание, что код и разметка находятся в одном файле.</span><span class="sxs-lookup"><span data-stu-id="f047b-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="f047b-223">Любые необходимые услуги `@inject` становятся доступными с помощью атрибута.</span><span class="sxs-lookup"><span data-stu-id="f047b-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="f047b-224">В `@page` указании этой страницы можно `Catalog/Details/{id}` получить доступ на маршруте.</span><span class="sxs-lookup"><span data-stu-id="f047b-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="f047b-225">Значение `{id}` заполнителя маршрута ограничено спешкей.</span><span class="sxs-lookup"><span data-stu-id="f047b-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="f047b-226">Как описано в разделе [маршрутики,](pages-routing-layouts.md) в отличие от Web Forms, компонент Razor прямо указывает свой маршрут и любые параметры, которые включены.</span><span class="sxs-lookup"><span data-stu-id="f047b-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="f047b-227">Многие элементы управления web Forms могут не иметь точных аналогов в Blazor.</span><span class="sxs-lookup"><span data-stu-id="f047b-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="f047b-228">Там часто эквивалент HTML фрагмент, который будет служить той же цели.</span><span class="sxs-lookup"><span data-stu-id="f047b-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="f047b-229">Например, `<asp:Label />` элемент управления может быть `<label>` заменен элементом HTML.</span><span class="sxs-lookup"><span data-stu-id="f047b-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-blazor"></a><span data-ttu-id="f047b-230">Проверка модели в Блазоре</span><span class="sxs-lookup"><span data-stu-id="f047b-230">Model validation in Blazor</span></span>

<span data-ttu-id="f047b-231">Если код Web Forms включает в себя проверку, вы можете передать большую часть того, что у вас есть с практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="f047b-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="f047b-232">Преимущество работы в Blazor заключается в том, что та же логика проверки может быть запущена без необходимости пользовательского JavaScript.</span><span class="sxs-lookup"><span data-stu-id="f047b-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="f047b-233">Аннотации данных позволяют легко валидацию модели.</span><span class="sxs-lookup"><span data-stu-id="f047b-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="f047b-234">Например, страница *Create.aspx* имеет форму ввода данных с проверкой.</span><span class="sxs-lookup"><span data-stu-id="f047b-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="f047b-235">Пример фрагмента будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f047b-235">An example snippet would look like this:</span></span>

```aspx
<div class="form-group">
    <label class="control-label col-md-2">Name</label>
    <div class="col-md-3">
        <asp:TextBox ID="Name" runat="server" CssClass="form-control"></asp:TextBox>
        <asp:RequiredFieldValidator runat="server" ControlToValidate="Name" Display="Dynamic"
            CssClass="field-validation-valid text-danger" ErrorMessage="The Name field is required." />
    </div>
</div>
```

<span data-ttu-id="f047b-236">В Blazor эквивалентная разметка предоставляется в файле *Create.razor:*</span><span class="sxs-lookup"><span data-stu-id="f047b-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

```razor
<EditForm Model="_item" OnValidSubmit="@...">
    <DataAnnotationsValidator />

    <div class="form-group">
        <label class="control-label col-md-2">Name</label>
        <div class="col-md-3">
            <InputText class="form-control" @bind-Value="_item.Name" />
            <ValidationMessage For="(() => _item.Name)" />
        </div>
    </div>

    ...
</EditForm>
```

<span data-ttu-id="f047b-237">Контекст `EditForm` включает поддержку проверки и может быть обернут вокруг ввода.</span><span class="sxs-lookup"><span data-stu-id="f047b-237">The `EditForm` context includes validation support and can be wrapped around input.</span></span> <span data-ttu-id="f047b-238">Аннотации данных являются распространенным способом добавления проверки.</span><span class="sxs-lookup"><span data-stu-id="f047b-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="f047b-239">Такая поддержка проверки может `DataAnnotationsValidator` быть добавлена через компонент.</span><span class="sxs-lookup"><span data-stu-id="f047b-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="f047b-240">Для получения дополнительной информации об этом механизме, см [ASP.NET Основные формы Blazor и проверки](/aspnet/core/blazor/forms-validation).</span><span class="sxs-lookup"><span data-stu-id="f047b-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-built-in-web-forms-controls"></a><span data-ttu-id="f047b-241">Мигрировать встроенные веб-формы управления</span><span class="sxs-lookup"><span data-stu-id="f047b-241">Migrate built-in Web Forms controls</span></span>

<span data-ttu-id="f047b-242">*Это содержание в ближайшее время.*</span><span class="sxs-lookup"><span data-stu-id="f047b-242">*This content is coming soon.*</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="f047b-243">Миграция конфигурации</span><span class="sxs-lookup"><span data-stu-id="f047b-243">Migrate configuration</span></span>

<span data-ttu-id="f047b-244">В проекте Web Forms данные конфигурации чаще всего хранятся в файле *web.config.*</span><span class="sxs-lookup"><span data-stu-id="f047b-244">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="f047b-245">Данные конфигурации доступны `ConfigurationManager`с помощью .</span><span class="sxs-lookup"><span data-stu-id="f047b-245">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="f047b-246">Для разбора объектов часто требовались службы.</span><span class="sxs-lookup"><span data-stu-id="f047b-246">Services were often required to parse objects.</span></span> <span data-ttu-id="f047b-247">С помощью .NET Framework 4.7.2 композиция `ConfigurationBuilders`была добавлена в конфигурацию через .</span><span class="sxs-lookup"><span data-stu-id="f047b-247">With .NET Framework 4.7.2, composability was added to configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="f047b-248">Эти строители позволили разработчикам добавлять различные источники для конфигурации, которая затем была составлена во время выполнения для получения необходимых значений.</span><span class="sxs-lookup"><span data-stu-id="f047b-248">These builders allowed developers to add various sources for configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="f047b-249">ASP.NET Core представила гибкую систему конфигурации, которая позволяет определить источник конфигурации или источники, используемые вашим приложением и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="f047b-249">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="f047b-250">Инфраструктура, которую `ConfigurationBuilder` вы можете использовать в приложении Web Forms, была смоделирована по образцу концепций, используемых в системе конфигурации ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f047b-250">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="f047b-251">Следующий фрагмент демонстрирует, как проект Web Forms eShop использует *web.config* для хранения значений конфигурации:</span><span class="sxs-lookup"><span data-stu-id="f047b-251">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

```xml
<configuration>
  <configSections>
    <section name="entityFramework" type="System.Data.Entity.Internal.ConfigFile.EntityFrameworkSection, EntityFramework, Version=6.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" requirePermission="false" />
  </configSections>
  <connectionStrings>
    <add name="CatalogDBContext" connectionString="Data Source=(localdb)\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;" providerName="System.Data.SqlClient" />
  </connectionStrings>
  <appSettings>
    <add key="UseMockData" value="true" />
    <add key="UseCustomizationData" value="false" />
  </appSettings>
</configuration>
```

<span data-ttu-id="f047b-252">Секреты, такие как строки подключения к базе данных, обычно хранятся в *web..config.* Секреты неизбежно сохраняются в небезопасных местах, таких как контроль исходных источников.</span><span class="sxs-lookup"><span data-stu-id="f047b-252">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="f047b-253">С Blazor на ASP.NET Core предыдущая конфигурация на основе XML заменяется следующим ИСОН:</span><span class="sxs-lookup"><span data-stu-id="f047b-253">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="f047b-254">JSON — это формат конфигурации по умолчанию; однако ASP.NET Core поддерживает многие другие форматы, включая XML.</span><span class="sxs-lookup"><span data-stu-id="f047b-254">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="f047b-255">Существует также несколько форматов, поддерживаемых сообществом.</span><span class="sxs-lookup"><span data-stu-id="f047b-255">There are also several community-supported formats.</span></span>

<span data-ttu-id="f047b-256">Конструктор в классе проекта Blazor `Startup` принимает `IConfiguration` экземпляр с помощью метода DI, известного как инъекция конструктора:</span><span class="sxs-lookup"><span data-stu-id="f047b-256">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

```csharp
public class Startup
{
    public Startup(IConfiguration configuration, IWebHostEnvironment env)
    {
        Configuration = configuration;
        Env = env;
    }

    ...
}
```

<span data-ttu-id="f047b-257">По умолчанию переменные среды, файлы JSON *(appsettings.json* и *appsettings. Параметры среды и*командной строки зарегистрированы в качестве действительных источников конфигурации в объекте конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f047b-257">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="f047b-258">К источникам конфигурации можно `Configuration[key]`получить доступ через .</span><span class="sxs-lookup"><span data-stu-id="f047b-258">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="f047b-259">Более продвинутый метод заключается в привязке данных конфигурации к объектам с использованием шаблона опций.</span><span class="sxs-lookup"><span data-stu-id="f047b-259">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="f047b-260">Для получения дополнительной информации о конфигурации и шаблоне опций см [ASP.NET](/aspnet/core/fundamentals/configuration/options) [ASP.NET.](/aspnet/core/fundamentals/configuration/)</span><span class="sxs-lookup"><span data-stu-id="f047b-260">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="f047b-261">Миграция доступа к данным</span><span class="sxs-lookup"><span data-stu-id="f047b-261">Migrate data access</span></span>

<span data-ttu-id="f047b-262">Доступ к данным является важным аспектом любого приложения.</span><span class="sxs-lookup"><span data-stu-id="f047b-262">Data access is an important aspect of any app.</span></span> <span data-ttu-id="f047b-263">Проект eShop хранит информацию каталога в базе данных и извлекает данные с помощью Entity Framework (EF) 6.</span><span class="sxs-lookup"><span data-stu-id="f047b-263">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="f047b-264">Поскольку EF 6 поддерживается в .NET Core 3.0, проект может продолжать использовать его.</span><span class="sxs-lookup"><span data-stu-id="f047b-264">Since EF 6 is supported in .NET Core 3.0, the project can continue to use it.</span></span>

<span data-ttu-id="f047b-265">Следующие изменения, связанные с EF, были необходимы для eShop:</span><span class="sxs-lookup"><span data-stu-id="f047b-265">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="f047b-266">В рамках .NET `DbContext` объект принимает строку *названия формы-ConnectionString* и использует `ConfigurationManager.AppSettings[ConnectionString]` строку соединения от подключения.</span><span class="sxs-lookup"><span data-stu-id="f047b-266">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="f047b-267">В .NET Core это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="f047b-267">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="f047b-268">Строка соединения должна быть поставлена.</span><span class="sxs-lookup"><span data-stu-id="f047b-268">The connection string must be supplied.</span></span>
- <span data-ttu-id="f047b-269">Доступ к базе данных был синхронным образом.</span><span class="sxs-lookup"><span data-stu-id="f047b-269">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="f047b-270">Хотя это работает, масштабируемость может пострадать.</span><span class="sxs-lookup"><span data-stu-id="f047b-270">Though this works, scalability may suffer.</span></span> <span data-ttu-id="f047b-271">Эта логика должна быть перемещена в асинхронный шаблон.</span><span class="sxs-lookup"><span data-stu-id="f047b-271">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="f047b-272">Несмотря на то, что не существует той же нативной поддержки связывания набора данных, Blazor обеспечивает гибкость и мощность с поддержкой C's на странице Razor.</span><span class="sxs-lookup"><span data-stu-id="f047b-272">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="f047b-273">Например, можно выполнять вычисления и отображать результат.</span><span class="sxs-lookup"><span data-stu-id="f047b-273">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="f047b-274">Для получения дополнительной информации о моделях данных в Blazor [см.](data.md)</span><span class="sxs-lookup"><span data-stu-id="f047b-274">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="f047b-275">Архитектурные изменения</span><span class="sxs-lookup"><span data-stu-id="f047b-275">Architectural changes</span></span>

<span data-ttu-id="f047b-276">Наконец, есть некоторые важные архитектурные различия, которые следует учитывать при переходе в Blazor.</span><span class="sxs-lookup"><span data-stu-id="f047b-276">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="f047b-277">Многие из этих изменений применимы ко всему, основанному на .NET Core или ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f047b-277">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="f047b-278">Поскольку Blazor построен на основе .NET Core, есть соображения в обеспечении поддержки на .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f047b-278">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="f047b-279">Некоторые из основных изменений включают удаление следующих функций:</span><span class="sxs-lookup"><span data-stu-id="f047b-279">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="f047b-280">Несколько AppDomains</span><span class="sxs-lookup"><span data-stu-id="f047b-280">Multiple AppDomains</span></span>
- <span data-ttu-id="f047b-281">Удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="f047b-281">Remoting</span></span>
- <span data-ttu-id="f047b-282">Управление доступом для кода (CAS)</span><span class="sxs-lookup"><span data-stu-id="f047b-282">Code Access Security (CAS)</span></span>
- <span data-ttu-id="f047b-283">Прозрачность безопасности</span><span class="sxs-lookup"><span data-stu-id="f047b-283">Security Transparency</span></span>

<span data-ttu-id="f047b-284">Для получения дополнительной информации о методах выявления необходимых изменений для поддержки работы на .NET Core [см. Port ваш код от .NET Framework до .NET Core](/dotnet/core/porting).</span><span class="sxs-lookup"><span data-stu-id="f047b-284">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](/dotnet/core/porting).</span></span>

<span data-ttu-id="f047b-285">ASP.NET Core — это переосмысленная версия ASP.NET и имеет некоторые изменения, которые изначально не кажутся очевидными.</span><span class="sxs-lookup"><span data-stu-id="f047b-285">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="f047b-286">Основные изменения:</span><span class="sxs-lookup"><span data-stu-id="f047b-286">The main changes are:</span></span>

- <span data-ttu-id="f047b-287">Нет контекста синхронизации, что означает, `HttpContext.Current` `Thread.CurrentPrincipal`что нет, или другие статические аксессуары</span><span class="sxs-lookup"><span data-stu-id="f047b-287">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="f047b-288">Нет копирования теней</span><span class="sxs-lookup"><span data-stu-id="f047b-288">No shadow copying</span></span>
- <span data-ttu-id="f047b-289">Очередь запросов не</span><span class="sxs-lookup"><span data-stu-id="f047b-289">No request queue</span></span>

<span data-ttu-id="f047b-290">Многие операции в ASP.NET Core являются асинхронными, что позволяет легче разгружать задачи, связанные с вводом/о..</span><span class="sxs-lookup"><span data-stu-id="f047b-290">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="f047b-291">Важно никогда не блокировать `Task.Wait()` с `Task.GetResult()`помощью или , которые могут быстро исчерпать ресурсы пула потоков.</span><span class="sxs-lookup"><span data-stu-id="f047b-291">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="f047b-292">Заключение о миграции</span><span class="sxs-lookup"><span data-stu-id="f047b-292">Migration conclusion</span></span>

<span data-ttu-id="f047b-293">На данный момент вы видели много примеров того, что нужно для перемещения проекта Web Forms в Blazor.</span><span class="sxs-lookup"><span data-stu-id="f047b-293">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="f047b-294">Для полного примера [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) см.</span><span class="sxs-lookup"><span data-stu-id="f047b-294">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="f047b-295">Назад</span><span class="sxs-lookup"><span data-stu-id="f047b-295">Previous</span></span>](security-authentication-authorization.md)
