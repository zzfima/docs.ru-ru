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
# <a name="migrate-from-aspnet-web-forms-to-blazor"></a>Мигрировать из веб-форм ASP.NET в Blazor

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Миграция базы кода из веб-форм ASP.NET в Blazor является трудоемкой задачей, требующей планирования. В этой главе излагается процесс. Что-то, что может облегчить переход, заключается в том, чтобы обеспечить соответствие приложения архитектуре *N-уровня,* в которой модель приложения (в данном случае Web Forms) отделена от бизнес-логики. Это логическое разделение слоев дает понять, что нужно перейти к .NET Core и Blazor.

В этом примере используется приложение eShop, доступное на [GitHub.](https://github.com/dotnet-architecture/eShopOnBlazor) eShop — это сервис каталога, предоставляющий возможности CRUD с помощью ввода формы и проверки.

Почему рабочее приложение должно быть перенесено в Blazor? Много раз, нет необходимости. ASP.NET веб-формы будут поддерживаться в течение многих лет. Однако многие функции, которые предоставляет Blazor, поддерживаются только в мигрировавом приложении. К таким функциям относятся:

- Улучшения производительности в таких рамках, как`Span<T>`
- Возможность работать как Веб-сборка
- Кросс-платформная поддержка Linux и macOS
- Развертывание локального приложения или совместное развертывание инфраструктуры без влияния на другие приложения

Если эти или другие новые функции являются достаточно убедительными, может быть значение в миграции приложения. Миграция может принимать различные формы; это может быть все приложение, или только определенные конечные точки, которые требуют изменений. Решение о миграции в конечном счете основано на бизнес-проблемах, которые должен быть решен разработчиком.

## <a name="server-side-versus-client-side-hosting"></a>Серверная сторона по сравнению с хостингом на стороне клиента

Как описано в главе [моделей хостинга,](hosting-models.md) приложение Blazor может быть размещено двумя различными способами: серверной и клиентской. Модель сервера использует ASP.NET core SignalR соединения для управления обновлениями DOM при запуске любого фактического кода на сервере. Модель клиентской стороны выполняется как WebAssembly в браузере и не требует подключения к серверу. Есть ряд отличий, которые могут повлиять на то, что лучше всего подходит для конкретного приложения:

- Запуск WebAssembly все еще находится в разработке и может не поддерживать все функции (например, потоков) в настоящее время
- Чаттая связь между клиентом и сервером может вызвать проблемы с задержкой в режиме сервера
- Доступ к базам данных и внутренним или защищенным службам требует отдельной службы с хостингом на стороне клиента

На момент написания статьи модель сервера больше напоминает веб-формы. Большая часть этой главы посвящена модели хостинга на стороне сервера, так как она готова к производству.

## <a name="create-a-new-project"></a>Создание нового проекта

Этот первоначальный шаг миграции заключается в создании нового проекта. Этот тип проекта основан на проектах стиля SDK .NET Core и упрощает большую часть шаблона, который использовался в предыдущих форматах проектов. Для получения более подробной информации, пожалуйста, смотрите главу о [структуре проекта](project-structure.md).

Как только проект был создан, установите библиотеки, которые использовались в предыдущем проекте. В старых проектах Web Forms вы, возможно, использовали файл *packages.config* для списка необходимых пакетов NuGet. В новом проекте в стиле SDK *packages.config* был заменен `<PackageReference>` элементами в файле проекта. Преимущество этого подхода заключается в том, что все зависимости устанавливаются транзитно. Вы перечисляете только зависимые от верхнего уровня зависимости.

Многие из использовавшихся зависимостей доступны для .NET Core, включая систему entity 6 и log4net. Если нет стандартной версии .NET Core или .NET, часто можно использовать рамочную версию .NET. Ваш пробег может варьироваться. Любой используемый API, недоступен в .NET Core, вызывает ошибку в времени выполнения. Visual Studio уведомляет вас о таких пакетах. На узло **ссылки** проекта в Solution **Explorer**появляется желтая иконка.

В проекте blazor на основе eShop можно увидеть установленные пакеты. Ранее файл *packages.config* перечислял каждый пакет, используемый в проекте, в результате чего файл длиной почти 50 строк. Фрагмент *packages.config:*

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

Элемент `<packages>` включает в себя все необходимые зависимости. Трудно определить, какие из этих пакетов включены, потому что вы требуете их. Некоторые `<package>` элементы перечислены просто для удовлетворения потребностей зависимостей, которые вам необходимы.

Проект Blazor перечисляет требуемые `<ItemGroup>` зависимости в элементе файла проекта:

```xml
<ItemGroup>
    <PackageReference Include="Autofac" Version="4.9.3" />
    <PackageReference Include="EntityFramework" Version="6.3.0-preview9-19423-04" />
    <PackageReference Include="log4net" Version="2.0.8" />
</ItemGroup>
```

Один пакет NuGet, который упрощает жизнь разработчиков Web Forms, — это [пакет совместимости Windows.](../../core/porting/windows-compat-pack.md) Хотя .NET Core является кросс-платформенным, некоторые функции доступны только на Windows. Особенности Windows становятся доступными, устанавливая пакет совместимости. Примерами таких функций являются Службы регистрации, WMI и Справочник. Пакет добавляет около 20 000 AA и активирует множество сервисов, с которыми вы, возможно, уже знакомы. Проект eShop не требует пакета совместимости; но если в ваших проектах используются специфические функции Windows, пакет облегчает усилия по миграции.

## <a name="enable-startup-process"></a>Включить процесс запуска

Процесс запуска Blazor изменился с Web Forms и следует аналогичной настройке для других ASP.NET основных услуг. При размещении сервера компоненты Blazor запускаются как часть обычного приложения ASP.NET Core. При размещении в браузере с WebAssembly, компоненты Blazor используют аналогичную модель хостинга. Разница в том, что компоненты работают как отдельная служба от любого из процессов бэкэнда. В любом случае, стартап похож.

*Файл Global.asax.cs* — это страница запуска по умолчанию для проектов Web-форм. В проекте eShop этот файл настраивает контейнер Inversion of Control (IoC) и обрабатывает различные события жизненного цикла приложения или запроса. Некоторые из этих событий обрабатываются с `Application_BeginRequest`помощью промежуточного посуды (например, ). Другие события требуют переопределения конкретных служб с помощью инъекций зависимости (DI).

Например, *Global.asax.cs* файл для eShop содержит следующий код:

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

Предыдущий файл `Startup` становится классом в серверной стороне Blazor:

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

Одним из существенных изменений, которые вы можете заметить из web-форм, является известность DI. DI был руководящим принципом в ASP.NET Core дизайн. Он поддерживает настройку почти всех аспектов ASP.NET Core. Есть даже встроенный поставщик услуг, который может быть использован для многих сценариев. Если требуется дополнительная настройка, она может быть поддержана многими проектами сообщества. Например, вы можете продолжить инвестиции в библиотеку DI сторонних сторонних стран.

В оригинальном приложении eShop есть некоторая конфигурация для управления сеансами. Поскольку серверная сторона Blazor использует ASP.NET Core SignalR для связи, состояние сеанса не поддерживается, поскольку соединения могут возникать независимо от контекста HTTP. Приложение, использующего состояние сеанса, требует реархиринга перед запуском в качестве приложения Blazor.

Для получения дополнительной информации о запуске приложения, [см.](app-startup.md)

## <a name="migrate-http-modules-and-handlers-to-middleware"></a>Мигрируйте модули и обработчики HTTP в промежуточное программное обеспечение

Модули и обработчики HTTP являются общими шаблонами в веб-формах для управления конвейером запросов HTTP. Классы, `IHttpModule` `IHttpHandler` которые реализуют или могут быть зарегистрированы и обрабатывать входящие запросы. Web Forms настраивает модули и обработчики в файле *web.config.* Веб-формы также в значительной степени основаны на обработке событий жизненного цикла приложения. ASP.NET Core использует вместо этого промежуточное программное обеспечение. Среднее посуды `Configure` зарегистрировано `Startup` в методе класса. Порядок исполнения Middleware определяется порядком регистрации.

В разделе [Процесс запуска Включить](#enable-startup-process) событие жизненного цикла было `Application_BeginRequest` поднято Web Forms в качестве метода. Это событие недоступно в ASP.NET Core. Одним из способов достижения такого поведения является реализация промежуточного посуды, как видно из примера *Startup.cs* файла. Это промежуточное программное обеспечение выполняет ту же логику, а затем передает управление следующему обработчику в промежуточном конвейере.

Для получения дополнительной информации о мигрирующих модулях и обработчиках см. [Мигрировать обработчики и модули HTTP, чтобы ASP.NET Core middleware.](/aspnet/core/migration/http-modules)

## <a name="migrate-static-files"></a>Мигрировать статические файлы

Для обслуживания статических файлов (например, HTML, CSS, изображений и JavaScript) файлы должны быть выставлены попромежутоным программным обеспечением. Вызов `UseStaticFiles` метода позволяет служить статических файлов из пути корней в Интернете. Каталог корней веб-страниц по умолчанию — *это wwwroot,* но его можно настроить. Как включено `Configure` в метод `Startup` класса eShop:

```csharp
public void Configure(IApplicationBuilder app)
{
    ...

    app.UseStaticFiles();

    ...
}
```

Проект eShop обеспечивает базовый статический доступ к файлам. Есть много настроек, доступных для статического доступа к файлу. Для получения информации о включении файлов по умолчанию или файлового браузера, см [ASP.NET.](/aspnet/core/fundamentals/static-files)

## <a name="migrate-runtime-bundling-and-minification-setup"></a>Мигрировать настройки комплектации и минификации времени выполнения

Объединение и минификация являются методами оптимизации производительности для уменьшения числа и размера запросов серверов для получения определенных типов файлов. JavaScript и CSS часто проходят ту или иную форму комплектации или минификации перед отправкой клиенту. В ASP.NET веб-формах эти оптимизации обрабатываются во время выполнения. Конвенции оптимизации определяются *как файл App_Start/BundleConfig.cs.* В ASP.NET Core принят более декларативный подход. Файл перечисляет файлы, которые необходимо обыграть, а также определенные настройки минификации.

Для получения дополнительной информации о комплектации и минификации [см. Bundle и минимифицировать статические активы в ASP.NET Core](/aspnet/core/client-side/bundling-and-minification).

## <a name="migrate-aspx-pages"></a>Мигрировать страницы ASPX

Страница в приложении Web Forms — это файл с расширением *.aspx.* Страница веб-форм часто может быть отображана с компонентом Blazor. Компонент Blazor авторизуется в файле с расширением *.razor.* Для проекта eShop пять страниц преобразуются на страницу Razor.

Например, представление деталей состоит из трех файлов в проекте Web Forms: *Details.aspx,* *Details.aspx.cs*и *Details.aspx.designer.cs.* При переходе в Blazor код сзади и разметку объединяются в *Details.razor*. Компиляция razor (эквивалент того, что находится в *файлах .designer.cs)* хранится в каталоге *obj* и по умолчанию не просматривается в **Solution Explorer.** Страница веб-форм состоит из следующей разметки:

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

Код-задняя часть предыдущей разметки включает в себя следующий код:

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

При преобразовании в Blazor страница Web Forms переводится на следующий код:

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

Обратите внимание, что код и разметка находятся в одном файле. Любые необходимые услуги `@inject` становятся доступными с помощью атрибута. В `@page` указании этой страницы можно `Catalog/Details/{id}` получить доступ на маршруте. Значение `{id}` заполнителя маршрута ограничено спешкей. Как описано в разделе [маршрутики,](pages-routing-layouts.md) в отличие от Web Forms, компонент Razor прямо указывает свой маршрут и любые параметры, которые включены. Многие элементы управления web Forms могут не иметь точных аналогов в Blazor. Там часто эквивалент HTML фрагмент, который будет служить той же цели. Например, `<asp:Label />` элемент управления может быть `<label>` заменен элементом HTML.

### <a name="model-validation-in-blazor"></a>Проверка модели в Блазоре

Если код Web Forms включает в себя проверку, вы можете передать большую часть того, что у вас есть с практически без изменений. Преимущество работы в Blazor заключается в том, что та же логика проверки может быть запущена без необходимости пользовательского JavaScript. Аннотации данных позволяют легко валидацию модели.

Например, страница *Create.aspx* имеет форму ввода данных с проверкой. Пример фрагмента будет выглядеть следующим образом:

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

В Blazor эквивалентная разметка предоставляется в файле *Create.razor:*

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

Контекст `EditForm` включает поддержку проверки и может быть обернут вокруг ввода. Аннотации данных являются распространенным способом добавления проверки. Такая поддержка проверки может `DataAnnotationsValidator` быть добавлена через компонент. Для получения дополнительной информации об этом механизме, см [ASP.NET Основные формы Blazor и проверки](/aspnet/core/blazor/forms-validation).

## <a name="migrate-built-in-web-forms-controls"></a>Мигрировать встроенные веб-формы управления

*Это содержание в ближайшее время.*

## <a name="migrate-configuration"></a>Миграция конфигурации

В проекте Web Forms данные конфигурации чаще всего хранятся в файле *web.config.* Данные конфигурации доступны `ConfigurationManager`с помощью . Для разбора объектов часто требовались службы. С помощью .NET Framework 4.7.2 композиция `ConfigurationBuilders`была добавлена в конфигурацию через . Эти строители позволили разработчикам добавлять различные источники для конфигурации, которая затем была составлена во время выполнения для получения необходимых значений.

ASP.NET Core представила гибкую систему конфигурации, которая позволяет определить источник конфигурации или источники, используемые вашим приложением и развертыванием. Инфраструктура, которую `ConfigurationBuilder` вы можете использовать в приложении Web Forms, была смоделирована по образцу концепций, используемых в системе конфигурации ASP.NET Core.

Следующий фрагмент демонстрирует, как проект Web Forms eShop использует *web.config* для хранения значений конфигурации:

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

Секреты, такие как строки подключения к базе данных, обычно хранятся в *web..config.* Секреты неизбежно сохраняются в небезопасных местах, таких как контроль исходных источников. С Blazor на ASP.NET Core предыдущая конфигурация на основе XML заменяется следующим ИСОН:

```json
{
  "ConnectionStrings": {
    "CatalogDBContext": "Data Source=(localdb)\\MSSQLLocalDB; Initial Catalog=Microsoft.eShopOnContainers.Services.CatalogDb; Integrated Security=True; MultipleActiveResultSets=True;"
  },
  "UseMockData": true,
  "UseCustomizationData": false
}
```

JSON — это формат конфигурации по умолчанию; однако ASP.NET Core поддерживает многие другие форматы, включая XML. Существует также несколько форматов, поддерживаемых сообществом.

Конструктор в классе проекта Blazor `Startup` принимает `IConfiguration` экземпляр с помощью метода DI, известного как инъекция конструктора:

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

По умолчанию переменные среды, файлы JSON *(appsettings.json* и *appsettings. Параметры среды и*командной строки зарегистрированы в качестве действительных источников конфигурации в объекте конфигурации. К источникам конфигурации можно `Configuration[key]`получить доступ через . Более продвинутый метод заключается в привязке данных конфигурации к объектам с использованием шаблона опций. Для получения дополнительной информации о конфигурации и шаблоне опций см [ASP.NET](/aspnet/core/fundamentals/configuration/options) [ASP.NET.](/aspnet/core/fundamentals/configuration/)

## <a name="migrate-data-access"></a>Миграция доступа к данным

Доступ к данным является важным аспектом любого приложения. Проект eShop хранит информацию каталога в базе данных и извлекает данные с помощью Entity Framework (EF) 6. Поскольку EF 6 поддерживается в .NET Core 3.0, проект может продолжать использовать его.

Следующие изменения, связанные с EF, были необходимы для eShop:

- В рамках .NET `DbContext` объект принимает строку *названия формы-ConnectionString* и использует `ConfigurationManager.AppSettings[ConnectionString]` строку соединения от подключения. В .NET Core это не поддерживается. Строка соединения должна быть поставлена.
- Доступ к базе данных был синхронным образом. Хотя это работает, масштабируемость может пострадать. Эта логика должна быть перемещена в асинхронный шаблон.

Несмотря на то, что не существует той же нативной поддержки связывания набора данных, Blazor обеспечивает гибкость и мощность с поддержкой C's на странице Razor. Например, можно выполнять вычисления и отображать результат. Для получения дополнительной информации о моделях данных в Blazor [см.](data.md)

## <a name="architectural-changes"></a>Архитектурные изменения

Наконец, есть некоторые важные архитектурные различия, которые следует учитывать при переходе в Blazor. Многие из этих изменений применимы ко всему, основанному на .NET Core или ASP.NET Core.

Поскольку Blazor построен на основе .NET Core, есть соображения в обеспечении поддержки на .NET Core. Некоторые из основных изменений включают удаление следующих функций:

- Несколько AppDomains
- Удаленное взаимодействие
- Управление доступом для кода (CAS)
- Прозрачность безопасности

Для получения дополнительной информации о методах выявления необходимых изменений для поддержки работы на .NET Core [см. Port ваш код от .NET Framework до .NET Core](/dotnet/core/porting).

ASP.NET Core — это переосмысленная версия ASP.NET и имеет некоторые изменения, которые изначально не кажутся очевидными. Основные изменения:

- Нет контекста синхронизации, что означает, `HttpContext.Current` `Thread.CurrentPrincipal`что нет, или другие статические аксессуары
- Нет копирования теней
- Очередь запросов не

Многие операции в ASP.NET Core являются асинхронными, что позволяет легче разгружать задачи, связанные с вводом/о.. Важно никогда не блокировать `Task.Wait()` с `Task.GetResult()`помощью или , которые могут быстро исчерпать ресурсы пула потоков.

## <a name="migration-conclusion"></a>Заключение о миграции

На данный момент вы видели много примеров того, что нужно для перемещения проекта Web Forms в Blazor. Для полного примера [eShopOnBlazor](https://github.com/dotnet-architecture/eShopOnBlazor) см.

>[!div class="step-by-step"]
>[Назад](security-authentication-authorization.md)
