---
title: Переход с веб-форм ASP.NET на Блазор
description: Узнайте, как подходить к переносу существующего приложения веб-форм ASP.NET в Блазор.
author: twsouthwick
ms.author: tasou
ms.date: 09/19/2019
ms.openlocfilehash: b6604e000eaf79bcd8da15d72a3d85713c620851
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73842041"
---
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a><span data-ttu-id="535f2-103">Переход с веб-форм ASP.NET на Блазор</span><span class="sxs-lookup"><span data-stu-id="535f2-103">Migrate from ASP.NET Web Forms to Blazor</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="535f2-104">Миграция базы кода из веб-форм ASP.NET в Блазор является трудоемкой задачей, требующей планирования.</span><span class="sxs-lookup"><span data-stu-id="535f2-104">Migrating a code base from ASP.NET Web Forms to Blazor is a time-consuming task that requires planning.</span></span> <span data-ttu-id="535f2-105">В этой главе описывается процесс.</span><span class="sxs-lookup"><span data-stu-id="535f2-105">This chapter outlines the process.</span></span> <span data-ttu-id="535f2-106">Что может упростить переход — убедиться, что приложение соответствует *N-уровневой* архитектуре, где модель приложения (в нашем примере это веб-формы) отдельно от бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="535f2-106">Something that can ease the transition is to ensure the app adheres to an *N-tier* architecture, wherein the app model (in this case, Web Forms) is separate from the business logic.</span></span> <span data-ttu-id="535f2-107">Это логическое разделение слоев делает ясно, что необходимо для перехода на .NET Core и Блазор.</span><span class="sxs-lookup"><span data-stu-id="535f2-107">This logical separation of layers makes it clear what needs to move to .NET Core and Blazor.</span></span>

<span data-ttu-id="535f2-108">В этом примере используется приложение Ешоп, доступное на сайте [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) .</span><span class="sxs-lookup"><span data-stu-id="535f2-108">For this example, the eShop app available on [GitHub](https://github.com/dotnet-architecture/eShopOnBlazor) is used.</span></span> <span data-ttu-id="535f2-109">Ешоп — это служба каталога, которая предоставляет возможности CRUD посредством ввода форм и проверки.</span><span class="sxs-lookup"><span data-stu-id="535f2-109">eShop is a catalog service that provides CRUD capabilities via form entry and validation.</span></span>

<span data-ttu-id="535f2-110">Зачем нужно перенести рабочее приложение в Блазор?</span><span class="sxs-lookup"><span data-stu-id="535f2-110">Why should a working app be migrated to Blazor?</span></span> <span data-ttu-id="535f2-111">Во многих случаях нет необходимости.</span><span class="sxs-lookup"><span data-stu-id="535f2-111">Many times, there's no need.</span></span> <span data-ttu-id="535f2-112">Веб-формы ASP.NET продолжат поддерживаться в течение многих лет.</span><span class="sxs-lookup"><span data-stu-id="535f2-112">ASP.NET Web Forms will continue to be supported for many years.</span></span> <span data-ttu-id="535f2-113">Однако многие функции, предоставляемые Блазор, поддерживаются только в перенесенном приложении.</span><span class="sxs-lookup"><span data-stu-id="535f2-113">However, many of the features that Blazor provides are only supported on a migrated app.</span></span> <span data-ttu-id="535f2-114">К таким функциям относятся:</span><span class="sxs-lookup"><span data-stu-id="535f2-114">Such features include:</span></span>

- <span data-ttu-id="535f2-115">Повышение производительности платформы, например `Span<T>`</span><span class="sxs-lookup"><span data-stu-id="535f2-115">Performance improvements in the framework such as `Span<T>`</span></span>
- <span data-ttu-id="535f2-116">Возможность запуска от имени сборки</span><span class="sxs-lookup"><span data-stu-id="535f2-116">Ability to run as WebAssembly</span></span>
- <span data-ttu-id="535f2-117">Кросс-платформенная поддержка для Linux и macOS</span><span class="sxs-lookup"><span data-stu-id="535f2-117">Cross-platform support for Linux and macOS</span></span>
- <span data-ttu-id="535f2-118">Локальное развертывание приложения или развертывание общей платформы без влияния на другие приложения</span><span class="sxs-lookup"><span data-stu-id="535f2-118">App-local deployment or shared framework deployment without impacting other apps</span></span>

<span data-ttu-id="535f2-119">Если эти или другие новые функции являются достаточно привлекательными, может возникнуть значение в процессе миграции приложения.</span><span class="sxs-lookup"><span data-stu-id="535f2-119">If these or other new features are compelling enough, there may be value in migrating the app.</span></span> <span data-ttu-id="535f2-120">Миграция может принять другие формы. Это может быть все приложение или только определенные конечные точки, для которых требуются изменения.</span><span class="sxs-lookup"><span data-stu-id="535f2-120">The migration can take different shapes; it can be the entire app, or only certain endpoints that require the changes.</span></span> <span data-ttu-id="535f2-121">Решение о миграции в конечном итоге зависит от бизнес-задач, которые могут быть решены разработчиком.</span><span class="sxs-lookup"><span data-stu-id="535f2-121">The decision to migrate is ultimately based on the business problems to be solved by the developer.</span></span>

## <a name="server-side-versus-client-side-hosting"></a><span data-ttu-id="535f2-122">Размещение на стороне сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="535f2-122">Server-side versus client-side hosting</span></span>

<span data-ttu-id="535f2-123">Как описано в главе [модели размещения](hosting-models.md) , приложение блазор может размещаться двумя разными способами: на стороне сервера и на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="535f2-123">As described in the [hosting models](hosting-models.md) chapter, a Blazor app can be hosted in two different ways: server-side and client-side.</span></span> <span data-ttu-id="535f2-124">Модель на стороне сервера использует ASP.NET Coreные подключения SignalR для управления обновлениями DOM при выполнении любого фактического кода на сервере.</span><span class="sxs-lookup"><span data-stu-id="535f2-124">The server-side model uses ASP.NET Core SignalR connections to manage the DOM updates while running any actual code on the server.</span></span> <span data-ttu-id="535f2-125">Клиентская модель выполняется как веб-сборка в браузере и не требует соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="535f2-125">The client-side model runs as WebAssembly within a browser and requires no server connections.</span></span> <span data-ttu-id="535f2-126">Существует ряд различий, которые могут повлиять на то, что лучше всего подходит для конкретного приложения:</span><span class="sxs-lookup"><span data-stu-id="535f2-126">There are a number of differences that may affect which is best for a specific app:</span></span>

- <span data-ttu-id="535f2-127">Работа в качестве сборки по-прежнему разрабатывается и может не поддерживать все функции (например, потоки) в текущее время.</span><span class="sxs-lookup"><span data-stu-id="535f2-127">Running as WebAssembly is still in development and may not support all features (such as threading) at the current time</span></span>
- <span data-ttu-id="535f2-128">Обмен данными между клиентом и сервером может вызвать проблемы задержки в режиме на стороне сервера</span><span class="sxs-lookup"><span data-stu-id="535f2-128">Chatty communication between the client and server may cause latency issues in server-side mode</span></span>
- <span data-ttu-id="535f2-129">Для доступа к базам данных и внутренним или защищенным службам требуется отдельная служба с размещением на стороне клиента.</span><span class="sxs-lookup"><span data-stu-id="535f2-129">Access to databases and internal or protected services require a separate service with client-side hosting</span></span>

<span data-ttu-id="535f2-130">На момент написания статьи модель на стороне сервера более похожа на веб-формы.</span><span class="sxs-lookup"><span data-stu-id="535f2-130">At the time of writing, the server-side model more closely resembles Web Forms.</span></span> <span data-ttu-id="535f2-131">Большая часть этой главы посвящена модели размещения на стороне сервера, так как она готова к производству.</span><span class="sxs-lookup"><span data-stu-id="535f2-131">Most of this chapter focuses on the server-side hosting model, as it's production-ready.</span></span>

## <a name="create-a-new-project"></a><span data-ttu-id="535f2-132">Создание нового проекта</span><span class="sxs-lookup"><span data-stu-id="535f2-132">Create a new project</span></span>

<span data-ttu-id="535f2-133">Этот этап начальной миграции заключается в создании нового проекта.</span><span class="sxs-lookup"><span data-stu-id="535f2-133">This initial migration step is to create a new project.</span></span> <span data-ttu-id="535f2-134">Этот тип проекта основан на проектах стиля пакета SDK .NET Core и упрощает большую часть шаблона, который использовался в предыдущих форматах проекта.</span><span class="sxs-lookup"><span data-stu-id="535f2-134">This project type is based on the SDK style projects of .NET Core and simplifies much of the boilerplate that was used in previous project formats.</span></span> <span data-ttu-id="535f2-135">Дополнительные сведения см. в разделе [Структура проекта](project-structure.md).</span><span class="sxs-lookup"><span data-stu-id="535f2-135">For more detail, please see the chapter on [Project Structure](project-structure.md).</span></span>

<span data-ttu-id="535f2-136">После создания проекта установите библиотеки, которые использовались в предыдущем проекте.</span><span class="sxs-lookup"><span data-stu-id="535f2-136">Once the project has been created, install the libraries that were used in the previous project.</span></span> <span data-ttu-id="535f2-137">В более старых проектах веб-форм вы могли использовать файл *Packages. config* для перечисления необходимых пакетов NuGet.</span><span class="sxs-lookup"><span data-stu-id="535f2-137">In older Web Forms projects, you may have used the *packages.config* file to list the required NuGet packages.</span></span> <span data-ttu-id="535f2-138">В новом проекте типа пакета SDK *Packages. config* был заменен элементами `<PackageReference>` в файле проекта.</span><span class="sxs-lookup"><span data-stu-id="535f2-138">In the new SDK-style project, *packages.config* has been replaced with `<PackageReference>` elements in the project file.</span></span> <span data-ttu-id="535f2-139">Преимуществом этого подхода является то, что все зависимости устанавливаются транзитно.</span><span class="sxs-lookup"><span data-stu-id="535f2-139">A benefit to this approach is that all dependencies are installed transitively.</span></span> <span data-ttu-id="535f2-140">Вы перечислите только те зависимости верхнего уровня, которые вас интересуют.</span><span class="sxs-lookup"><span data-stu-id="535f2-140">You only list the top-level dependencies you care about.</span></span>

<span data-ttu-id="535f2-141">Многие из зависимостей, которые вы используете, доступны для .NET Core, включая Entity Framework 6 и log4net.</span><span class="sxs-lookup"><span data-stu-id="535f2-141">Many of the dependencies you're using are available for .NET Core, including Entity Framework 6 and log4net.</span></span> <span data-ttu-id="535f2-142">Если версия .NET Core или .NET Standard недоступна, часто можно использовать .NET Frameworkную версию.</span><span class="sxs-lookup"><span data-stu-id="535f2-142">If there's no .NET Core or .NET Standard version available, the .NET Framework version can often be used.</span></span> <span data-ttu-id="535f2-143">Расстояние может отличаться.</span><span class="sxs-lookup"><span data-stu-id="535f2-143">Your mileage may vary.</span></span> <span data-ttu-id="535f2-144">Любой интерфейс API, недоступный в .NET Core, вызывает ошибку во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="535f2-144">Any API used that isn't available in .NET Core causes a runtime error.</span></span> <span data-ttu-id="535f2-145">Visual Studio уведомляет вас о таких пакетах.</span><span class="sxs-lookup"><span data-stu-id="535f2-145">Visual Studio notifies you of such packages.</span></span> <span data-ttu-id="535f2-146">На узле **ссылки** проекта в **Обозреватель решений**появляется желтый значок.</span><span class="sxs-lookup"><span data-stu-id="535f2-146">A yellow icon appears on the project's **References** node in **Solution Explorer**.</span></span>

<span data-ttu-id="535f2-147">В проекте Ешоп на основе Блазор можно просмотреть установленные пакеты.</span><span class="sxs-lookup"><span data-stu-id="535f2-147">In the Blazor-based eShop project, you can see the packages that are installed.</span></span> <span data-ttu-id="535f2-148">Ранее в файле *Packages. config* перечислен каждый пакет, используемый в проекте, и в результате файл будет почти 50 строк.</span><span class="sxs-lookup"><span data-stu-id="535f2-148">Previously, the *packages.config* file listed every package used in the project, resulting in a file almost 50 lines long.</span></span> <span data-ttu-id="535f2-149">Фрагмент файла *Packages. config* :</span><span class="sxs-lookup"><span data-stu-id="535f2-149">A snippet of *packages.config* is:</span></span>

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

<span data-ttu-id="535f2-150">Элемент `<packages>` включает все необходимые зависимости.</span><span class="sxs-lookup"><span data-stu-id="535f2-150">The `<packages>` element includes all necessary dependencies.</span></span> <span data-ttu-id="535f2-151">Трудно обнаружить, какие из этих пакетов включены, так как они требуются.</span><span class="sxs-lookup"><span data-stu-id="535f2-151">It's difficult to identify which of these packages are included because you require them.</span></span> <span data-ttu-id="535f2-152">Некоторые `<package>` элементы перечислены просто для удовлетворения потребностей необходимых зависимостей.</span><span class="sxs-lookup"><span data-stu-id="535f2-152">Some `<package>` elements are listed simply to satisfy the needs of dependencies you require.</span></span>

<span data-ttu-id="535f2-153">Проект Блазор перечисляет зависимости, необходимые в элементе `<ItemGroup>` в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="535f2-153">The Blazor project lists the dependencies you require within an `<ItemGroup>` element in the project file:</span></span>

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

<span data-ttu-id="535f2-154">Одним пакетом NuGet, который упрощает жизнь разработчиков веб-форм, является [пакет обеспечения совместимости Windows](../../core/porting/windows-compat-pack.md).</span><span class="sxs-lookup"><span data-stu-id="535f2-154">One NuGet package that simplifies the life of Web Forms developers is the [Windows Compatibility Pack](../../core/porting/windows-compat-pack.md).</span></span> <span data-ttu-id="535f2-155">Несмотря на то, что .NET Core работает на разных платформах, некоторые функции доступны только в Windows.</span><span class="sxs-lookup"><span data-stu-id="535f2-155">Although .NET Core is cross-platform, some features are only available on Windows.</span></span> <span data-ttu-id="535f2-156">Функции Windows становятся доступными путем установки пакета обеспечения совместимости.</span><span class="sxs-lookup"><span data-stu-id="535f2-156">Windows-specific features are made available by installing the compatibility pack.</span></span> <span data-ttu-id="535f2-157">Примеры таких функций включают в себя реестр, WMI и службы каталогов.</span><span class="sxs-lookup"><span data-stu-id="535f2-157">Examples of such features include the Registry, WMI, and Directory Services.</span></span> <span data-ttu-id="535f2-158">Пакет добавляет около 20 000 API и активирует множество служб, с которыми вы, возможно, уже знакомы.</span><span class="sxs-lookup"><span data-stu-id="535f2-158">The package adds around 20,000 APIs and activates many services with which you may already be familiar.</span></span> <span data-ttu-id="535f2-159">Для проекта Ешоп не требуется пакет обеспечения совместимости; но если в проектах используются функции Windows, пакет упрощает миграцию.</span><span class="sxs-lookup"><span data-stu-id="535f2-159">The eShop project doesn't require the compatibility pack; but if your projects use Windows-specific features, the package eases the migration efforts.</span></span>

## <a name="enable-startup-process"></a><span data-ttu-id="535f2-160">Включить процесс запуска</span><span class="sxs-lookup"><span data-stu-id="535f2-160">Enable startup process</span></span>

<span data-ttu-id="535f2-161">Процесс запуска для Блазор был изменен с веб-форм и соответствует аналогичной настройке для других служб ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="535f2-161">The startup process for Blazor has changed from Web Forms and follows a similar setup for other ASP.NET Core services.</span></span> <span data-ttu-id="535f2-162">При размещении на стороне сервера Блазор компоненты запускаются как часть обычного ASP.NET Core приложения.</span><span class="sxs-lookup"><span data-stu-id="535f2-162">When hosted server-side, Blazor components are run as part of a normal ASP.NET Core app.</span></span> <span data-ttu-id="535f2-163">При размещении в браузере с веб-сборкой компоненты Блазор используют аналогичную модель размещения.</span><span class="sxs-lookup"><span data-stu-id="535f2-163">When hosted in the browser with WebAssembly, Blazor components use a similar hosting model.</span></span> <span data-ttu-id="535f2-164">Различие состоит в том, что компоненты запускаются как отдельная служба из любого внутреннего процесса.</span><span class="sxs-lookup"><span data-stu-id="535f2-164">The difference is the components are run as a separate service from any of the backend processes.</span></span> <span data-ttu-id="535f2-165">В любом случае запуск будет похожим.</span><span class="sxs-lookup"><span data-stu-id="535f2-165">Either way, the startup is similar.</span></span>

<span data-ttu-id="535f2-166">Файл *Global.asax.CS* является страницей запуска по умолчанию для проектов веб-форм.</span><span class="sxs-lookup"><span data-stu-id="535f2-166">The *Global.asax.cs* file is the default startup page for Web Forms projects.</span></span> <span data-ttu-id="535f2-167">В проекте Ешоп этот файл настраивает контейнер инверсии управления (IoC) и обрабатывает различные события жизненного цикла приложения или запроса.</span><span class="sxs-lookup"><span data-stu-id="535f2-167">In the eShop project, this file configures the Inversion of Control (IoC) container and handles the various lifecycle events of the app or request.</span></span> <span data-ttu-id="535f2-168">Некоторые из этих событий обрабатываются по промежуточного слоя (например, `Application_BeginRequest`).</span><span class="sxs-lookup"><span data-stu-id="535f2-168">Some of these events are handled with middleware (such as `Application_BeginRequest`).</span></span> <span data-ttu-id="535f2-169">Другие события нуждаются в переопределении конкретных служб посредством внедрения зависимостей (DI).</span><span class="sxs-lookup"><span data-stu-id="535f2-169">Other events require the overriding of specific services via dependency injection (DI).</span></span>

<span data-ttu-id="535f2-170">Например, файл *Global.asax.CS* для ешоп содержит следующий код:</span><span class="sxs-lookup"><span data-stu-id="535f2-170">By way of example, the *Global.asax.cs* file for eShop, contains the following code:</span></span>

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

<span data-ttu-id="535f2-171">Предыдущий файл станет классом `Startup` в Блазор на стороне сервера:</span><span class="sxs-lookup"><span data-stu-id="535f2-171">The preceding file becomes the `Startup` class in server-side Blazor:</span></span>

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

<span data-ttu-id="535f2-172">Одно существенное изменение, которое можно заметить в Web Forms, является выразительностью внедрения.</span><span class="sxs-lookup"><span data-stu-id="535f2-172">One significant change you may notice from Web Forms is the prominence of DI.</span></span> <span data-ttu-id="535f2-173">DI является принципом GUID в ASP.NET Coreном проектировании.</span><span class="sxs-lookup"><span data-stu-id="535f2-173">DI has been a guiding principle in the ASP.NET Core design.</span></span> <span data-ttu-id="535f2-174">Он поддерживает настройку почти всех аспектов ASP.NET Core Framework.</span><span class="sxs-lookup"><span data-stu-id="535f2-174">It supports customization of almost all aspects of the ASP.NET Core framework.</span></span> <span data-ttu-id="535f2-175">Существует даже встроенный поставщик услуг, который можно использовать во многих сценариях.</span><span class="sxs-lookup"><span data-stu-id="535f2-175">There's even a built-in service provider that can be used for many scenarios.</span></span> <span data-ttu-id="535f2-176">Если требуется дополнительная настройка, она может поддерживаться многими проектами сообщества.</span><span class="sxs-lookup"><span data-stu-id="535f2-176">If more customization is required, it can be supported by the many community projects.</span></span> <span data-ttu-id="535f2-177">Например, вы можете переслать вложения библиотеки внедрения сторонних разработчиков.</span><span class="sxs-lookup"><span data-stu-id="535f2-177">For example, you can carry forward your third-party DI library investment.</span></span>

<span data-ttu-id="535f2-178">В исходном приложении Ешоп существует определенная конфигурация управления сеансами.</span><span class="sxs-lookup"><span data-stu-id="535f2-178">In the original eShop app, there's some configuration for session management.</span></span> <span data-ttu-id="535f2-179">Так как серверная часть Блазор использует SignalR для связи ASP.NET Core, состояние сеанса не поддерживается, так как соединения могут происходить независимо от контекста HTTP.</span><span class="sxs-lookup"><span data-stu-id="535f2-179">Since server-side Blazor uses ASP.NET Core SignalR for communication, session state isn't supported as the connections may occur independent of an HTTP context.</span></span> <span data-ttu-id="535f2-180">Для приложения, использующего состояние сеанса, требуется пересоздать архитектуру перед запуском в качестве приложения Блазор.</span><span class="sxs-lookup"><span data-stu-id="535f2-180">An app that uses session state requires rearchitecting before running as a Blazor app.</span></span>

<span data-ttu-id="535f2-181">Дополнительные сведения о запуске приложения см. в разделе [Запуск приложения](app-startup.md).</span><span class="sxs-lookup"><span data-stu-id="535f2-181">For more information about app startup, see [App startup](app-startup.md).</span></span>

## <a name="migrate-http-modules-and-handlers-to-middleware"></a><span data-ttu-id="535f2-182">Перенос HTTP-модулей и обработчиков на по промежуточного слоя</span><span class="sxs-lookup"><span data-stu-id="535f2-182">Migrate HTTP modules and handlers to middleware</span></span>

<span data-ttu-id="535f2-183">HTTP-модули и обработчики — это общие шаблоны в Web Forms для управления конвейером HTTP-запросов.</span><span class="sxs-lookup"><span data-stu-id="535f2-183">HTTP modules and handlers are common patterns in Web Forms to control the HTTP request pipeline.</span></span> <span data-ttu-id="535f2-184">Классы, реализующие `IHttpModule` или `IHttpHandler`, могут быть зарегистрированы и обрабатывать входящие запросы.</span><span class="sxs-lookup"><span data-stu-id="535f2-184">Classes that implement `IHttpModule` or `IHttpHandler` could be registered and process incoming requests.</span></span> <span data-ttu-id="535f2-185">Веб-формы настраивают модули и обработчики в файле *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="535f2-185">Web Forms configures modules and handlers in the *web.config* file.</span></span> <span data-ttu-id="535f2-186">Веб-формы также сильно основаны на обработке событий жизненного цикла приложения.</span><span class="sxs-lookup"><span data-stu-id="535f2-186">Web Forms is also heavily based on app lifecycle event handling.</span></span> <span data-ttu-id="535f2-187">Вместо этого ASP.NET Core использует по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="535f2-187">ASP.NET Core uses middleware instead.</span></span> <span data-ttu-id="535f2-188">По промежуточного слоя регистрируются в методе `Configure` класса `Startup`.</span><span class="sxs-lookup"><span data-stu-id="535f2-188">Middlewares are registered in the `Configure` method of the `Startup` class.</span></span> <span data-ttu-id="535f2-189">Порядок выполнения по промежуточного слоя определяется порядком регистрации.</span><span class="sxs-lookup"><span data-stu-id="535f2-189">Middleware execution order is determined by the registration order.</span></span>

<span data-ttu-id="535f2-190">В разделе [Включение процесса запуска](#enable-startup-process) событие жизненного цикла было вызвано веб-формами в качестве метода `Application_BeginRequest`.</span><span class="sxs-lookup"><span data-stu-id="535f2-190">In the [Enable startup process](#enable-startup-process) section, a lifecycle event was raised by Web Forms as the `Application_BeginRequest` method.</span></span> <span data-ttu-id="535f2-191">Это событие недоступно в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="535f2-191">This event isn't available in ASP.NET Core.</span></span> <span data-ttu-id="535f2-192">Одним из способов добиться такого поведения является реализация по промежуточного слоя, как показано в примере файла *Startup.CS* .</span><span class="sxs-lookup"><span data-stu-id="535f2-192">One way to achieve this behavior is to implement middleware as seen in the *Startup.cs* file example.</span></span> <span data-ttu-id="535f2-193">Это по промежуточного слоя выполняет ту же логику, а затем передает управление следующему обработчику в конвейере по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="535f2-193">This middleware does the same logic and then transfers control to the next handler in the middleware pipeline.</span></span>

<span data-ttu-id="535f2-194">Дополнительные сведения о миграции модулей и обработчиков см. [в разделе Миграция обработчиков и модулей HTTP в ASP.NET Core по промежуточного слоя](/aspnet/core/migration/http-modules).</span><span class="sxs-lookup"><span data-stu-id="535f2-194">For more information on migrating modules and handlers, see [Migrate HTTP handlers and modules to ASP.NET Core middleware](/aspnet/core/migration/http-modules).</span></span>

## <a name="migrate-static-files"></a><span data-ttu-id="535f2-195">Миграция статических файлов</span><span class="sxs-lookup"><span data-stu-id="535f2-195">Migrate static files</span></span>

<span data-ttu-id="535f2-196">Для обслуживания статических файлов (например, HTML, CSS, изображений и JavaScript) файлы должны предоставляться по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="535f2-196">To serve static files (for example, HTML, CSS, images, and JavaScript), the files must be exposed by middleware.</span></span> <span data-ttu-id="535f2-197">Вызов метода `UseStaticFiles` позволяет обслуживать статические файлы из корневого пути в Интернете.</span><span class="sxs-lookup"><span data-stu-id="535f2-197">Calling the `UseStaticFiles` method enables the serving of static files from the web root path.</span></span> <span data-ttu-id="535f2-198">Корневой каталог веб-сайта по умолчанию — *wwwroot*, но его можно настроить.</span><span class="sxs-lookup"><span data-stu-id="535f2-198">The default web root directory is *wwwroot*, but it can be customized.</span></span> <span data-ttu-id="535f2-199">Как включается в метод `Configure` класса `Startup` Ешоп:</span><span class="sxs-lookup"><span data-stu-id="535f2-199">As included in the `Configure` method of eShop's `Startup` class:</span></span>

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

<span data-ttu-id="535f2-200">Проект Ешоп обеспечивает базовый доступ к статическим файлам.</span><span class="sxs-lookup"><span data-stu-id="535f2-200">The eShop project enables basic static file access.</span></span> <span data-ttu-id="535f2-201">Существует множество настроек, доступных для доступа к статическим файлам.</span><span class="sxs-lookup"><span data-stu-id="535f2-201">There are many customizations available for static file access.</span></span> <span data-ttu-id="535f2-202">Сведения о включении файлов по умолчанию или обозревателя файлов см. [в разделе статические файлы в ASP.NET Core](/aspnet/core/fundamentals/static-files).</span><span class="sxs-lookup"><span data-stu-id="535f2-202">For information on enabling default files or a file browser, see [Static files in ASP.NET Core](/aspnet/core/fundamentals/static-files).</span></span>

## <a name="migrate-runtime-bundling-and-minification-setup"></a><span data-ttu-id="535f2-203">Миграция объединения среды выполнения и установки минификации</span><span class="sxs-lookup"><span data-stu-id="535f2-203">Migrate runtime bundling and minification setup</span></span>

<span data-ttu-id="535f2-204">Объединение и минификации — это методы оптимизации производительности, позволяющие сократить количество и размер запросов сервера для получения определенных типов файлов.</span><span class="sxs-lookup"><span data-stu-id="535f2-204">Bundling and minification are performance optimization techniques for reducing the number and size of server requests to retrieve certain file types.</span></span> <span data-ttu-id="535f2-205">JavaScript и CSS часто проводят некоторую форму объединения или минификации перед отправкой клиенту.</span><span class="sxs-lookup"><span data-stu-id="535f2-205">JavaScript and CSS often undergo some form of bundling or minification before being sent to the client.</span></span> <span data-ttu-id="535f2-206">В веб-формах ASP.NET эти оптимизации обрабатываются во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="535f2-206">In ASP.NET Web Forms, these optimizations are handled at runtime.</span></span> <span data-ttu-id="535f2-207">Соглашения по оптимизации определяют App_Start файл */бундлеконфиг.КС* .</span><span class="sxs-lookup"><span data-stu-id="535f2-207">The optimization conventions are defined an *App_Start/BundleConfig.cs* file.</span></span> <span data-ttu-id="535f2-208">В ASP.NET Core применяется более декларативный подход.</span><span class="sxs-lookup"><span data-stu-id="535f2-208">In ASP.NET Core, a more declarative approach is adopted.</span></span> <span data-ttu-id="535f2-209">Файл содержит список файлов, которые будут минифицированные, а также конкретные параметры минификации.</span><span class="sxs-lookup"><span data-stu-id="535f2-209">A file lists the files to be minified, along with specific minification settings.</span></span>

<span data-ttu-id="535f2-210">Дополнительные сведения о объединениях и минификации см. [в разделе статические ресурсы пакета и уменьшение в ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span><span class="sxs-lookup"><span data-stu-id="535f2-210">For more information on bundling and minification, see [Bundle and minify static assets in ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).</span></span>

## <a name="migrate-aspx-pages"></a><span data-ttu-id="535f2-211">Перенос страниц ASPX</span><span class="sxs-lookup"><span data-stu-id="535f2-211">Migrate ASPX pages</span></span>

<span data-ttu-id="535f2-212">Страница в приложении Web Forms — это файл с расширением *. aspx* .</span><span class="sxs-lookup"><span data-stu-id="535f2-212">A page in a Web Forms app is a file with the *.aspx* extension.</span></span> <span data-ttu-id="535f2-213">Страница веб-форм часто может быть сопоставлена с компонентом в Блазор.</span><span class="sxs-lookup"><span data-stu-id="535f2-213">A Web Forms page can often be mapped to a component in Blazor.</span></span> <span data-ttu-id="535f2-214">Компонент Блазор создан в файле с расширением *Razor* .</span><span class="sxs-lookup"><span data-stu-id="535f2-214">A Blazor component is authored in a file with the *.razor* extension.</span></span> <span data-ttu-id="535f2-215">Для проекта Ешоп пять страниц преобразуются в страницу Razor.</span><span class="sxs-lookup"><span data-stu-id="535f2-215">For the eShop project, five pages are converted to a Razor page.</span></span>

<span data-ttu-id="535f2-216">Например, подробное представление состоит из трех файлов в проекте Web Forms: *Details. aspx*, *Details.aspx.CS*и *Details.aspx.Designer.CS*.</span><span class="sxs-lookup"><span data-stu-id="535f2-216">For example, the details view is comprised of three files in the Web Forms project: *Details.aspx*, *Details.aspx.cs*, and *Details.aspx.designer.cs*.</span></span> <span data-ttu-id="535f2-217">При преобразовании в Блазор код программной части и разметка объединяются в *Details. Razor*.</span><span class="sxs-lookup"><span data-stu-id="535f2-217">When converting to Blazor, the code-behind and markup are combined into *Details.razor*.</span></span> <span data-ttu-id="535f2-218">Компиляция Razor (эквивалентная в *Designer.CS* -файлах) хранится в каталоге *obj* , а не по умолчанию, которую можно просмотреть в **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="535f2-218">Razor compilation (equivalent to what's in *.designer.cs* files) is stored in the *obj* directory and aren't, by default, viewable in **Solution Explorer**.</span></span> <span data-ttu-id="535f2-219">Страница веб-форм состоит из следующей разметки:</span><span class="sxs-lookup"><span data-stu-id="535f2-219">The Web Forms page consists of the following markup:</span></span>

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

<span data-ttu-id="535f2-220">Код программной части предыдущей разметки включает следующий код:</span><span class="sxs-lookup"><span data-stu-id="535f2-220">The preceding markup's code-behind includes the following code:</span></span>

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

<span data-ttu-id="535f2-221">При преобразовании в Блазор страница Web Forms преобразуется в следующий код:</span><span class="sxs-lookup"><span data-stu-id="535f2-221">When converted to Blazor, the Web Forms page translates to the following code:</span></span>

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

<span data-ttu-id="535f2-222">Обратите внимание, что код и разметка находятся в одном файле.</span><span class="sxs-lookup"><span data-stu-id="535f2-222">Notice that the code and markup are in the same file.</span></span> <span data-ttu-id="535f2-223">Все необходимые службы становятся доступными с помощью атрибута `@inject`.</span><span class="sxs-lookup"><span data-stu-id="535f2-223">Any required services are made accessible with the `@inject` attribute.</span></span> <span data-ttu-id="535f2-224">Для директивы `@page` Эта страница доступна по маршруту `Catalog/Details/{id}`.</span><span class="sxs-lookup"><span data-stu-id="535f2-224">Per the `@page` directive, this page can be accessed at the `Catalog/Details/{id}` route.</span></span> <span data-ttu-id="535f2-225">Значение заполнителя `{id}` маршрута ограничено целым числом.</span><span class="sxs-lookup"><span data-stu-id="535f2-225">The value of the route's `{id}` placeholder has been constrained to an integer.</span></span> <span data-ttu-id="535f2-226">Как описано в разделе о [маршрутизации](pages-routing-layouts.md) , в отличие от веб-форм, компонент Razor явным образом указывает свой маршрут и все включенные параметры.</span><span class="sxs-lookup"><span data-stu-id="535f2-226">As described in the [routing](pages-routing-layouts.md) section, unlike Web Forms, a Razor component explicitly states its route and any parameters that are included.</span></span> <span data-ttu-id="535f2-227">Многие элементы управления веб-форм могут не иметь точных аналогов в Блазор.</span><span class="sxs-lookup"><span data-stu-id="535f2-227">Many Web Forms controls may not have exact counterparts in Blazor.</span></span> <span data-ttu-id="535f2-228">Часто существует эквивалентный фрагмент кода HTML, который будет использоваться в той же цели.</span><span class="sxs-lookup"><span data-stu-id="535f2-228">There's often an equivalent HTML snippet that will serve the same purpose.</span></span> <span data-ttu-id="535f2-229">Например, элемент управления `<asp:Label />` можно заменить на HTML-элемент `<label>`.</span><span class="sxs-lookup"><span data-stu-id="535f2-229">For example, the `<asp:Label />` control can be replaced with an HTML `<label>` element.</span></span>

### <a name="model-validation-in-blazor"></a><span data-ttu-id="535f2-230">Проверка модели в Блазор</span><span class="sxs-lookup"><span data-stu-id="535f2-230">Model validation in Blazor</span></span>

<span data-ttu-id="535f2-231">Если код веб-форм включает проверку, вы можете переносить многие из них с минимальными изменениями.</span><span class="sxs-lookup"><span data-stu-id="535f2-231">If your Web Forms code includes validation, you can transfer much of what you have with little-to-no changes.</span></span> <span data-ttu-id="535f2-232">Преимуществом работы в Блазор является то, что логика проверки может выполняться без необходимости использования пользовательского кода JavaScript.</span><span class="sxs-lookup"><span data-stu-id="535f2-232">A benefit to running in Blazor is that the same validation logic can be run without needing custom JavaScript.</span></span> <span data-ttu-id="535f2-233">Заметки к данным обеспечивают простую проверку модели.</span><span class="sxs-lookup"><span data-stu-id="535f2-233">Data annotations enable easy model validation.</span></span>

<span data-ttu-id="535f2-234">Например, страница *Create. aspx* содержит форму ввода данных с проверкой.</span><span class="sxs-lookup"><span data-stu-id="535f2-234">For example, the *Create.aspx* page has a data entry form with validation.</span></span> <span data-ttu-id="535f2-235">Пример фрагмента кода выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="535f2-235">An example snippet would look like this:</span></span>

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

<span data-ttu-id="535f2-236">В Блазор Эквивалентная разметка предоставляется в файле *Create. Razor* :</span><span class="sxs-lookup"><span data-stu-id="535f2-236">In Blazor, the equivalent markup is provided in a *Create.razor* file:</span></span>

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

<span data-ttu-id="535f2-237">Контекст `EditForm` включает поддержку проверки, и его можно заключить в оболочку для ввода.</span><span class="sxs-lookup"><span data-stu-id="535f2-237">The `EditForm` context includes validation support and can be wrapped around input.</span></span> <span data-ttu-id="535f2-238">Заметки к данным являются обычным способом добавления проверки.</span><span class="sxs-lookup"><span data-stu-id="535f2-238">Data annotations are a common way to add validation.</span></span> <span data-ttu-id="535f2-239">Такая поддержка проверки может быть добавлена с помощью компонента `DataAnnotationsValidator`.</span><span class="sxs-lookup"><span data-stu-id="535f2-239">Such validation support can be added via the `DataAnnotationsValidator` component.</span></span> <span data-ttu-id="535f2-240">Дополнительные сведения об этом механизме см. в разделе [ASP.NET Core блазор Forms and Validation](/aspnet/core/blazor/forms-validation).</span><span class="sxs-lookup"><span data-stu-id="535f2-240">For more information on this mechanism, see [ASP.NET Core Blazor forms and validation](/aspnet/core/blazor/forms-validation).</span></span>

## <a name="migrate-built-in-web-forms-controls"></a><span data-ttu-id="535f2-241">Миграция встроенных элементов управления веб-форм</span><span class="sxs-lookup"><span data-stu-id="535f2-241">Migrate built-in Web Forms controls</span></span>

<span data-ttu-id="535f2-242">*Это содержимое скоро появится.*</span><span class="sxs-lookup"><span data-stu-id="535f2-242">*This content is coming soon.*</span></span>

## <a name="migrate-configuration"></a><span data-ttu-id="535f2-243">Миграция конфигурации</span><span class="sxs-lookup"><span data-stu-id="535f2-243">Migrate configuration</span></span>

<span data-ttu-id="535f2-244">В проекте веб-форм данные конфигурации чаще всего хранятся в файле *Web. config* .</span><span class="sxs-lookup"><span data-stu-id="535f2-244">In a Web Forms project, configuration data is most commonly stored in the *web.config* file.</span></span> <span data-ttu-id="535f2-245">Доступ к данным конфигурации осуществляется с помощью `ConfigurationManager`.</span><span class="sxs-lookup"><span data-stu-id="535f2-245">The configuration data is accessed with `ConfigurationManager`.</span></span> <span data-ttu-id="535f2-246">Службам часто требовалось анализировать объекты.</span><span class="sxs-lookup"><span data-stu-id="535f2-246">Services were often required to parse objects.</span></span> <span data-ttu-id="535f2-247">При использовании .NET Framework 4.7.2 компонуемости был добавлен в конфигурацию с помощью `ConfigurationBuilders`.</span><span class="sxs-lookup"><span data-stu-id="535f2-247">With .NET Framework 4.7.2, composability was added to configuration via `ConfigurationBuilders`.</span></span> <span data-ttu-id="535f2-248">Эти построители позволяли разработчикам добавлять различные источники для настройки, которые затем состоялись во время выполнения для получения необходимых значений.</span><span class="sxs-lookup"><span data-stu-id="535f2-248">These builders allowed developers to add various sources for configuration that was then composed at runtime to retrieve the necessary values.</span></span>

<span data-ttu-id="535f2-249">ASP.NET Core представил гибкую систему конфигурации, позволяющую определить источник конфигурации или источники, используемые приложением и развертыванием.</span><span class="sxs-lookup"><span data-stu-id="535f2-249">ASP.NET Core introduced a flexible configuration system that allows you to define the configuration source or sources used by your app and deployment.</span></span> <span data-ttu-id="535f2-250">Инфраструктура `ConfigurationBuilder`, которую можно использовать в приложении веб-форм, была смоделирована после использования концепций, используемых в системе конфигурации ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="535f2-250">The `ConfigurationBuilder` infrastructure that you may be using in your Web Forms app was modeled after the concepts used in the ASP.NET Core configuration system.</span></span>

<span data-ttu-id="535f2-251">В следующем фрагменте кода показано, как проект Web Forms Ешоп использует *Web. config* для хранения значений конфигурации:</span><span class="sxs-lookup"><span data-stu-id="535f2-251">The following snippet demonstrates how the Web Forms eShop project uses *web.config* to store configuration values:</span></span>

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
```

<span data-ttu-id="535f2-252">Обычно для секретов, таких как строки подключения к базе данных, они хранятся в *файле Web. config*. Секреты неизбежно сохраняются в незащищенных расположениях, таких как система управления версиями.</span><span class="sxs-lookup"><span data-stu-id="535f2-252">It's common for secrets, such as database connection strings, to be stored within the *web.config*. The secrets are inevitably persisted in unsecure locations, such as source control.</span></span> <span data-ttu-id="535f2-253">При использовании Блазор на ASP.NET Core предыдущая конфигурация на основе XML заменяется следующим JSON:</span><span class="sxs-lookup"><span data-stu-id="535f2-253">With Blazor on ASP.NET Core, the preceding XML-based configuration is replaced with the following JSON:</span></span>

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

<span data-ttu-id="535f2-254">JSON является форматом конфигурации по умолчанию; Однако ASP.NET Core поддерживает многие другие форматы, в том числе XML.</span><span class="sxs-lookup"><span data-stu-id="535f2-254">JSON is the default configuration format; however, ASP.NET Core supports many other formats, including XML.</span></span> <span data-ttu-id="535f2-255">Существует также несколько форматов, поддерживаемых сообществом.</span><span class="sxs-lookup"><span data-stu-id="535f2-255">There are also several community-supported formats.</span></span>

<span data-ttu-id="535f2-256">Конструктор в классе `Startup` проекта Блазор принимает экземпляр `IConfiguration` с помощью метода DI, известного как внедрение конструктора:</span><span class="sxs-lookup"><span data-stu-id="535f2-256">The constructor in the Blazor project's `Startup` class accepts an `IConfiguration` instance through a DI technique known as constructor injection:</span></span>

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

<span data-ttu-id="535f2-257">По умолчанию переменные среды, JSON-файлы (*appSettings. JSON* и *appSettings. { Environment}. JSON*) и параметры командной строки регистрируются в объекте конфигурации в качестве допустимых источников конфигурации.</span><span class="sxs-lookup"><span data-stu-id="535f2-257">By default, environment variables, JSON files (*appsettings.json* and *appsettings.{Environment}.json*), and command-line options are registered as valid configuration sources in the configuration object.</span></span> <span data-ttu-id="535f2-258">Доступ к источникам конфигурации можно получить с помощью `Configuration[key]`.</span><span class="sxs-lookup"><span data-stu-id="535f2-258">The configuration sources can be accessed via `Configuration[key]`.</span></span> <span data-ttu-id="535f2-259">Более сложная методика — привязать данные конфигурации к объектам с помощью шаблона параметров.</span><span class="sxs-lookup"><span data-stu-id="535f2-259">A more advanced technique is to bind the configuration data to objects using the options pattern.</span></span> <span data-ttu-id="535f2-260">Дополнительные сведения о конфигурации и шаблоне параметров см. в разделе [Конфигурация в ASP.NET Core](/aspnet/core/fundamentals/configuration/) и [шаблоне параметров в ASP.NET Core](/aspnet/core/fundamentals/configuration/options)соответственно.</span><span class="sxs-lookup"><span data-stu-id="535f2-260">For more information on configuration and the options pattern, see [Configuration in ASP.NET Core](/aspnet/core/fundamentals/configuration/) and [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options), respectively.</span></span>

## <a name="migrate-data-access"></a><span data-ttu-id="535f2-261">Перенос доступа к данным</span><span class="sxs-lookup"><span data-stu-id="535f2-261">Migrate data access</span></span>

<span data-ttu-id="535f2-262">Доступ к данным является важным аспектом любого приложения.</span><span class="sxs-lookup"><span data-stu-id="535f2-262">Data access is an important aspect of any app.</span></span> <span data-ttu-id="535f2-263">Проект Ешоп хранит сведения о каталоге в базе данных и извлекает их с помощью Entity Framework (EF) 6.</span><span class="sxs-lookup"><span data-stu-id="535f2-263">The eShop project stores catalog information in a database and retrieves the data with Entity Framework (EF) 6.</span></span> <span data-ttu-id="535f2-264">Поскольку EF 6 поддерживается в .NET Core 3,0, проект может продолжать его использовать.</span><span class="sxs-lookup"><span data-stu-id="535f2-264">Since EF 6 is supported in .NET Core 3.0, the project can continue to use it.</span></span>

<span data-ttu-id="535f2-265">Для Ешоп были необходимы следующие изменения, связанные с EF:</span><span class="sxs-lookup"><span data-stu-id="535f2-265">The following EF-related changes were necessary to eShop:</span></span>

- <span data-ttu-id="535f2-266">В .NET Framework объект `DbContext` принимает строку с *именем Form = ConnectionString* и использует строку подключения из `ConfigurationManager.AppSettings[ConnectionString]` для подключения.</span><span class="sxs-lookup"><span data-stu-id="535f2-266">In .NET Framework, the `DbContext` object accepts a string of the form *name=ConnectionString* and uses the connection string from `ConfigurationManager.AppSettings[ConnectionString]` to connect.</span></span> <span data-ttu-id="535f2-267">В .NET Core это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="535f2-267">In .NET Core, this isn't supported.</span></span> <span data-ttu-id="535f2-268">Необходимо указать строку подключения.</span><span class="sxs-lookup"><span data-stu-id="535f2-268">The connection string must be supplied.</span></span>
- <span data-ttu-id="535f2-269">Доступ к базе данных осуществлялся синхронно.</span><span class="sxs-lookup"><span data-stu-id="535f2-269">The database was accessed in a synchronous way.</span></span> <span data-ttu-id="535f2-270">Хотя это и работает, масштабируемость может снизиться.</span><span class="sxs-lookup"><span data-stu-id="535f2-270">Though this works, scalability may suffer.</span></span> <span data-ttu-id="535f2-271">Эта логика должна быть перемещена в асинхронную модель.</span><span class="sxs-lookup"><span data-stu-id="535f2-271">This logic should be moved to an asynchronous pattern.</span></span>

<span data-ttu-id="535f2-272">Несмотря на то, что собственная поддержка привязки набора данных не поддерживается, Блазор обеспечивает гибкость и мощь C# с поддержкой на странице Razor.</span><span class="sxs-lookup"><span data-stu-id="535f2-272">Although there isn't the same native support for dataset binding, Blazor provides flexibility and power with its C# support in a Razor page.</span></span> <span data-ttu-id="535f2-273">Например, можно выполнять вычисления и отображать результат.</span><span class="sxs-lookup"><span data-stu-id="535f2-273">For example, you can perform calculations and display the result.</span></span> <span data-ttu-id="535f2-274">Дополнительные сведения о шаблонах данных в Блазор см. в главе « [доступ к данным](data.md) ».</span><span class="sxs-lookup"><span data-stu-id="535f2-274">For more information on data patterns in Blazor, see the [Data access](data.md) chapter.</span></span>

## <a name="architectural-changes"></a><span data-ttu-id="535f2-275">Изменения архитектуры</span><span class="sxs-lookup"><span data-stu-id="535f2-275">Architectural changes</span></span>

<span data-ttu-id="535f2-276">Наконец, существуют некоторые важные архитектурные различия, которые следует учитывать при переходе на Блазор.</span><span class="sxs-lookup"><span data-stu-id="535f2-276">Finally, there are some important architectural differences to consider when migrating to Blazor.</span></span> <span data-ttu-id="535f2-277">Многие из этих изменений применимы к любому, основанному на .NET Core или ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="535f2-277">Many of these changes are applicable to anything based on .NET Core or ASP.NET Core.</span></span>

<span data-ttu-id="535f2-278">Поскольку Блазор построен на .NET Core, существуют рекомендации по обеспечению поддержки в .NET Core.</span><span class="sxs-lookup"><span data-stu-id="535f2-278">Because Blazor is built on .NET Core, there are considerations in ensuring support on .NET Core.</span></span> <span data-ttu-id="535f2-279">Некоторые из основных изменений включают удаление следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="535f2-279">Some of the major changes include the removal of the following features:</span></span>

- <span data-ttu-id="535f2-280">Несколько доменов AppDomain</span><span class="sxs-lookup"><span data-stu-id="535f2-280">Multiple AppDomains</span></span>
- <span data-ttu-id="535f2-281">Удаленное взаимодействие</span><span class="sxs-lookup"><span data-stu-id="535f2-281">Remoting</span></span>
- <span data-ttu-id="535f2-282">CAS (Code Access Security — безопасность доступа кода)</span><span class="sxs-lookup"><span data-stu-id="535f2-282">Code Access Security (CAS)</span></span>
- <span data-ttu-id="535f2-283">Прозрачность безопасности</span><span class="sxs-lookup"><span data-stu-id="535f2-283">Security Transparency</span></span>

<span data-ttu-id="535f2-284">Дополнительные сведения о методах, позволяющих определить необходимые изменения для поддержки в .NET Core, см. в разделе [Перенос кода из .NET Framework в .NET Core](/dotnet/core/porting).</span><span class="sxs-lookup"><span data-stu-id="535f2-284">For more information on techniques to identify necessary changes to support running on .NET Core, see [Port your code from .NET Framework to .NET Core](/dotnet/core/porting).</span></span>

<span data-ttu-id="535f2-285">ASP.NET Core является пересмотренной версией ASP.NET и содержит некоторые изменения, которые изначально не кажутся очевидными.</span><span class="sxs-lookup"><span data-stu-id="535f2-285">ASP.NET Core is a reimagined version of ASP.NET and has some changes that may not initially seem obvious.</span></span> <span data-ttu-id="535f2-286">Основные изменения:</span><span class="sxs-lookup"><span data-stu-id="535f2-286">The main changes are:</span></span>

- <span data-ttu-id="535f2-287">Нет контекста синхронизации, что означает отсутствие `HttpContext.Current`, `Thread.CurrentPrincipal`или других статических методов доступа</span><span class="sxs-lookup"><span data-stu-id="535f2-287">No synchronization context, which means there's no `HttpContext.Current`, `Thread.CurrentPrincipal`, or other static accessors</span></span>
- <span data-ttu-id="535f2-288">Без теневого копирования</span><span class="sxs-lookup"><span data-stu-id="535f2-288">No shadow copying</span></span>
- <span data-ttu-id="535f2-289">Нет очереди запросов</span><span class="sxs-lookup"><span data-stu-id="535f2-289">No request queue</span></span>

<span data-ttu-id="535f2-290">Многие операции в ASP.NET Core являются асинхронными, что позволяет упростить отгрузку задач, связанных с вводом-выводом.</span><span class="sxs-lookup"><span data-stu-id="535f2-290">Many operations in ASP.NET Core are asynchronous, which allows easier off-loading of I/O-bound tasks.</span></span> <span data-ttu-id="535f2-291">Важно никогда не блокировать с помощью `Task.Wait()` или `Task.GetResult()`, что позволяет быстро исчерпать ресурсы пула потоков.</span><span class="sxs-lookup"><span data-stu-id="535f2-291">It's important to never block by using `Task.Wait()` or `Task.GetResult()`, which can quickly exhaust thread pool resources.</span></span>

## <a name="migration-conclusion"></a><span data-ttu-id="535f2-292">Заключение миграции</span><span class="sxs-lookup"><span data-stu-id="535f2-292">Migration conclusion</span></span>

<span data-ttu-id="535f2-293">На этом этапе вы увидели много примеров того, что требуется для перемещения проекта веб-форм в Блазор.</span><span class="sxs-lookup"><span data-stu-id="535f2-293">At this point, you've seen many examples of what it takes to move a Web Forms project to Blazor.</span></span> <span data-ttu-id="535f2-294">Полный пример см. в разделе проект [ешопонблазор](https://github.com/dotnet-architecture/eShopOnBlazor) .</span><span class="sxs-lookup"><span data-stu-id="535f2-294">For a full example, see the [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) project.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="535f2-295">Назад</span><span class="sxs-lookup"><span data-stu-id="535f2-295">Previous</span></span>](security-authentication-authorization.md)
