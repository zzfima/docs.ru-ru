---
title: Модули, обработчики и по промежуточного слоя
description: Сведения об обработке HTTP-запросов с помощью модулей, обработчиков и по промежуточного слоя.
author: danroth27
ms.author: daroth
ms.date: 10/11/2019
ms.openlocfilehash: b0be6109b9226bddbb9cbe4cebf114fd2b2a6114
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2019
ms.locfileid: "73841207"
---
# <a name="modules-handlers-and-middleware"></a><span data-ttu-id="7e72b-103">Модули, обработчики и по промежуточного слоя</span><span class="sxs-lookup"><span data-stu-id="7e72b-103">Modules, handlers, and middleware</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="7e72b-104">ASP.NET Core приложение строится на основе ряда по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7e72b-104">An ASP.NET Core app is built upon a series of middleware.</span></span> <span data-ttu-id="7e72b-105">По промежуточного слоя — это обработчики, которые упорядочены в конвейер для обработки запросов и ответов.</span><span class="sxs-lookup"><span data-stu-id="7e72b-105">Middlewares are handlers, which are arranged into a pipeline to handle requests and responses.</span></span> <span data-ttu-id="7e72b-106">В приложении веб-форм обработчики и модули HTTP решают аналогичные проблемы.</span><span class="sxs-lookup"><span data-stu-id="7e72b-106">In a Web Forms app, HTTP handlers and modules solve similar problems.</span></span> <span data-ttu-id="7e72b-107">В ASP.NET Core модули, обработчики, *Global.asax.CS*и жизненный цикл приложения заменяются по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7e72b-107">In ASP.NET Core, modules, handlers, *Global.asax.cs*, and the app life cycle are replaced with middleware.</span></span> <span data-ttu-id="7e72b-108">В этой главе вы узнаете, какое по промежуточного слоя в контексте приложения Блазор.</span><span class="sxs-lookup"><span data-stu-id="7e72b-108">In this chapter, you'll learn what middleware in the context of a Blazor app.</span></span>

## <a name="overview"></a><span data-ttu-id="7e72b-109">Обзор</span><span class="sxs-lookup"><span data-stu-id="7e72b-109">Overview</span></span>

<span data-ttu-id="7e72b-110">Конвейер запросов ASP.NET Core состоит из последовательности делегатов запроса, вызываемых один за другим.</span><span class="sxs-lookup"><span data-stu-id="7e72b-110">The ASP.NET Core request pipeline consists of a sequence of request delegates, called one after the other.</span></span> <span data-ttu-id="7e72b-111">На следующей схеме демонстрируется этот принцип.</span><span class="sxs-lookup"><span data-stu-id="7e72b-111">The following diagram demonstrates the concept.</span></span> <span data-ttu-id="7e72b-112">Поток выполнения показан черными стрелками.</span><span class="sxs-lookup"><span data-stu-id="7e72b-112">The thread of execution follows the black arrows.</span></span>

![надстройк](media/middleware/request-delegate-pipeline.png)

<span data-ttu-id="7e72b-114">На предыдущей схеме отсутствует концепция событий жизненного цикла.</span><span class="sxs-lookup"><span data-stu-id="7e72b-114">The preceding diagram lacks a concept of lifecycle events.</span></span> <span data-ttu-id="7e72b-115">Эта концепция основана на том, как обрабатываются запросы ASP.NET Web Forms.</span><span class="sxs-lookup"><span data-stu-id="7e72b-115">This concept is foundational to how ASP.NET Web Forms requests are handled.</span></span> <span data-ttu-id="7e72b-116">Эта система упрощает причины того, что происходит, и позволяет вставлять по промежуточного слоя в любой момент.</span><span class="sxs-lookup"><span data-stu-id="7e72b-116">This system makes it easier to reason about what process is occurring and allows middleware to be inserted at any point.</span></span> <span data-ttu-id="7e72b-117">По промежуточного слоя выполняется в том порядке, в котором он добавляется в конвейер запросов.</span><span class="sxs-lookup"><span data-stu-id="7e72b-117">Middleware executes in the order in which it's added to the request pipeline.</span></span> <span data-ttu-id="7e72b-118">Они также добавляются в код вместо файлов конфигурации, обычно в *Startup.CS*.</span><span class="sxs-lookup"><span data-stu-id="7e72b-118">They're also added in code instead of configuration files, usually in *Startup.cs*.</span></span>

## <a name="katana"></a><span data-ttu-id="7e72b-119">Katana</span><span class="sxs-lookup"><span data-stu-id="7e72b-119">Katana</span></span>

<span data-ttu-id="7e72b-120">Читатели, знакомые с Katana, покажутся вам удобным ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7e72b-120">Readers familiar with Katana will feel comfortable in ASP.NET Core.</span></span> <span data-ttu-id="7e72b-121">Фактически Katana — это платформа, от которой наследуется ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7e72b-121">In fact, Katana is a framework from which ASP.NET Core derives.</span></span> <span data-ttu-id="7e72b-122">В нем представлено аналогичное по промежуточного слоя и шаблоны конвейера для ASP.NET 4. x.</span><span class="sxs-lookup"><span data-stu-id="7e72b-122">It introduced similar middleware and pipeline patterns for ASP.NET 4.x.</span></span> <span data-ttu-id="7e72b-123">По промежуточного слоя, разработанного для Katana, можно адаптировать для работы с конвейером ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7e72b-123">Middleware designed for Katana can be adapted to work with the ASP.NET Core pipeline.</span></span>

## <a name="common-middleware"></a><span data-ttu-id="7e72b-124">Общее по промежуточного слоя</span><span class="sxs-lookup"><span data-stu-id="7e72b-124">Common middleware</span></span>

<span data-ttu-id="7e72b-125">ASP.NET 4. x включает множество модулей.</span><span class="sxs-lookup"><span data-stu-id="7e72b-125">ASP.NET 4.x includes many modules.</span></span> <span data-ttu-id="7e72b-126">Аналогичным образом, ASP.NET Core имеет много компонентов по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7e72b-126">In a similar fashion, ASP.NET Core has many middleware components available as well.</span></span> <span data-ttu-id="7e72b-127">В некоторых случаях в ASP.NET Core могут использоваться модули IIS.</span><span class="sxs-lookup"><span data-stu-id="7e72b-127">IIS modules may be used in some cases with ASP.NET Core.</span></span> <span data-ttu-id="7e72b-128">В других случаях может быть доступно собственное ASP.NET Core по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7e72b-128">In other cases, native ASP.NET Core middleware may be available.</span></span>

<span data-ttu-id="7e72b-129">В следующей таблице перечислены по промежуточного слоя и компоненты в ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7e72b-129">The following table lists replacement middleware and components in ASP.NET Core.</span></span>

|<span data-ttu-id="7e72b-130">Модуль</span><span class="sxs-lookup"><span data-stu-id="7e72b-130">Module</span></span>                 |<span data-ttu-id="7e72b-131">Модуль ASP.NET 4. x</span><span class="sxs-lookup"><span data-stu-id="7e72b-131">ASP.NET 4.x module</span></span>           |<span data-ttu-id="7e72b-132">ASP.NET Core, параметр</span><span class="sxs-lookup"><span data-stu-id="7e72b-132">ASP.NET Core option</span></span>|
|-----------------------|-----------------------------|-------------------|
|<span data-ttu-id="7e72b-133">Ошибки HTTP</span><span class="sxs-lookup"><span data-stu-id="7e72b-133">HTTP errors</span></span>            |`CustomErrorModule`          |[<span data-ttu-id="7e72b-134">ПО промежуточного слоя для страниц кода состояния</span><span class="sxs-lookup"><span data-stu-id="7e72b-134">Status Code Pages Middleware</span></span>](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|<span data-ttu-id="7e72b-135">Документ по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7e72b-135">Default document</span></span>       |`DefaultDocumentModule`      |[<span data-ttu-id="7e72b-136">ПО промежуточного слоя для файлов по умолчанию</span><span class="sxs-lookup"><span data-stu-id="7e72b-136">Default Files Middleware</span></span>](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|<span data-ttu-id="7e72b-137">Просмотр каталогов</span><span class="sxs-lookup"><span data-stu-id="7e72b-137">Directory browsing</span></span>     |`DirectoryListingModule`     |[<span data-ttu-id="7e72b-138">ПО промежуточного слоя для просмотра каталогов</span><span class="sxs-lookup"><span data-stu-id="7e72b-138">Directory Browsing Middleware</span></span>](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|<span data-ttu-id="7e72b-139">Динамическое сжатие</span><span class="sxs-lookup"><span data-stu-id="7e72b-139">Dynamic compression</span></span>    |`DynamicCompressionModule`   |[<span data-ttu-id="7e72b-140">ПО промежуточного слоя для сжатия ответов</span><span class="sxs-lookup"><span data-stu-id="7e72b-140">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="7e72b-141">Трассировка неудачных запросов</span><span class="sxs-lookup"><span data-stu-id="7e72b-141">Failed requests tracing</span></span>|`FailedRequestsTracingModule`|[<span data-ttu-id="7e72b-142">Ведение журналов ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7e72b-142">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|<span data-ttu-id="7e72b-143">Кэширование файлов</span><span class="sxs-lookup"><span data-stu-id="7e72b-143">File caching</span></span>           |`FileCacheModule`            |[<span data-ttu-id="7e72b-144">ПО промежуточного слоя для кэширования ответов</span><span class="sxs-lookup"><span data-stu-id="7e72b-144">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="7e72b-145">Кэширование HTTP</span><span class="sxs-lookup"><span data-stu-id="7e72b-145">HTTP caching</span></span>           |`HttpCacheModule`            |[<span data-ttu-id="7e72b-146">ПО промежуточного слоя для кэширования ответов</span><span class="sxs-lookup"><span data-stu-id="7e72b-146">Response Caching Middleware</span></span>](/aspnet/core/performance/caching/middleware)|
|<span data-ttu-id="7e72b-147">Ведение журнала HTTP</span><span class="sxs-lookup"><span data-stu-id="7e72b-147">HTTP logging</span></span>           |`HttpLoggingModule`          |[<span data-ttu-id="7e72b-148">Ведение журналов ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7e72b-148">ASP.NET Core Logging</span></span>](/aspnet/core/fundamentals/logging/index)|
|<span data-ttu-id="7e72b-149">Перенаправление HTTP</span><span class="sxs-lookup"><span data-stu-id="7e72b-149">HTTP redirection</span></span>       |`HttpRedirectionModule`      |[<span data-ttu-id="7e72b-150">ПО промежуточного слоя для переопределения URL-адресов</span><span class="sxs-lookup"><span data-stu-id="7e72b-150">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="7e72b-151">Фильтры ISAPI</span><span class="sxs-lookup"><span data-stu-id="7e72b-151">ISAPI filters</span></span>          |`IsapiFilterModule`          |[<span data-ttu-id="7e72b-152">ПО промежуточного слоя</span><span class="sxs-lookup"><span data-stu-id="7e72b-152">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="7e72b-153">ISAPI</span><span class="sxs-lookup"><span data-stu-id="7e72b-153">ISAPI</span></span>                  |`IsapiModule`                |[<span data-ttu-id="7e72b-154">ПО промежуточного слоя</span><span class="sxs-lookup"><span data-stu-id="7e72b-154">Middleware</span></span>](/aspnet/core/fundamentals/middleware/index)|
|<span data-ttu-id="7e72b-155">Фильтрация запросов</span><span class="sxs-lookup"><span data-stu-id="7e72b-155">Request filtering</span></span>      |`RequestFilteringModule`     |[<span data-ttu-id="7e72b-156">URL-адрес промежуточного слоя переопределения IRule</span><span class="sxs-lookup"><span data-stu-id="7e72b-156">URL Rewriting Middleware IRule</span></span>](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|<span data-ttu-id="7e72b-157">Перезапись URL-адресов&#8224;</span><span class="sxs-lookup"><span data-stu-id="7e72b-157">URL rewriting&#8224;</span></span>   |`RewriteModule`              |[<span data-ttu-id="7e72b-158">ПО промежуточного слоя для переопределения URL-адресов</span><span class="sxs-lookup"><span data-stu-id="7e72b-158">URL Rewriting Middleware</span></span>](/aspnet/core/fundamentals/url-rewriting)|
|<span data-ttu-id="7e72b-159">Статическое сжатие</span><span class="sxs-lookup"><span data-stu-id="7e72b-159">Static compression</span></span>     |`StaticCompressionModule`    |[<span data-ttu-id="7e72b-160">ПО промежуточного слоя для сжатия ответов</span><span class="sxs-lookup"><span data-stu-id="7e72b-160">Response Compression Middleware</span></span>](/aspnet/core/performance/response-compression)|
|<span data-ttu-id="7e72b-161">Статическое содержимое</span><span class="sxs-lookup"><span data-stu-id="7e72b-161">Static content</span></span>         |`StaticFileModule`           |[<span data-ttu-id="7e72b-162">ПО промежуточного слоя для статических файлов</span><span class="sxs-lookup"><span data-stu-id="7e72b-162">Static File Middleware</span></span>](/aspnet/core/fundamentals/static-files)|
|<span data-ttu-id="7e72b-163">Авторизация URL-адреса</span><span class="sxs-lookup"><span data-stu-id="7e72b-163">URL authorization</span></span>      |`UrlAuthorizationModule`     |[<span data-ttu-id="7e72b-164">Идентификация ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7e72b-164">ASP.NET Core Identity</span></span>](/aspnet/core/security/authentication/identity)|

<span data-ttu-id="7e72b-165">Этот список не является исчерпывающим, но должен понять, какое сопоставление существует между двумя платформами.</span><span class="sxs-lookup"><span data-stu-id="7e72b-165">This list isn't exhaustive but should give an idea of what mapping exists between the two frameworks.</span></span> <span data-ttu-id="7e72b-166">Более подробный список см. в разделе [модули IIS с ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span><span class="sxs-lookup"><span data-stu-id="7e72b-166">For a more detailed list, see [IIS modules with ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).</span></span>

## <a name="custom-middleware"></a><span data-ttu-id="7e72b-167">Настраиваемое по промежуточного слоя</span><span class="sxs-lookup"><span data-stu-id="7e72b-167">Custom middleware</span></span>

<span data-ttu-id="7e72b-168">Встроенное по промежуточного слоя может не поддерживать все сценарии, необходимые для приложения.</span><span class="sxs-lookup"><span data-stu-id="7e72b-168">Built-in middleware may not handle all scenarios needed for an app.</span></span> <span data-ttu-id="7e72b-169">В таких случаях имеет смысл создать собственное по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7e72b-169">In such cases, it makes sense to create your own middleware.</span></span> <span data-ttu-id="7e72b-170">Существует несколько способов определения по промежуточного слоя, с простым простым делегатом.</span><span class="sxs-lookup"><span data-stu-id="7e72b-170">There are multiple ways of defining middleware, with the simplest being a simple delegate.</span></span> <span data-ttu-id="7e72b-171">Рассмотрим следующее по промежуточного слоя, которое принимает запрос языка и региональных параметров из строки запроса:</span><span class="sxs-lookup"><span data-stu-id="7e72b-171">Consider the following middleware, which accepts a culture request from a query string:</span></span>

```csharp
public class Startup
{
    public void Configure(IApplicationBuilder app)
    {
        app.Use(async (context, next) =>
        {
            var cultureQuery = context.Request.Query["culture"];

            if (!string.IsNullOrWhiteSpace(cultureQuery))
            {
                var culture = new CultureInfo(cultureQuery);

                CultureInfo.CurrentCulture = culture;
                CultureInfo.CurrentUICulture = culture;
            }

            // Call the next delegate/middleware in the pipeline
            await next();
        });

        app.Run(async (context) =>
            await context.Response.WriteAsync(
                $"Hello {CultureInfo.CurrentCulture.DisplayName}"));
    }
}
```

<span data-ttu-id="7e72b-172">По промежуточного слоя можно также определить как класс, реализовав интерфейс `IMiddleware` или следуя правилам по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="7e72b-172">Middleware can also be defined as class, either by implementing the `IMiddleware` interface or by following middleware convention.</span></span> <span data-ttu-id="7e72b-173">Дополнительные сведения см. в разделе [Создание пользовательского по промежуточного слоя ASP.NET Core](/aspnet/core/fundamentals/middleware/write).</span><span class="sxs-lookup"><span data-stu-id="7e72b-173">For more information, see [Write custom ASP.NET Core middleware](/aspnet/core/fundamentals/middleware/write).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7e72b-174">[Назад](data.md)
>[Вперед](config.md)</span><span class="sxs-lookup"><span data-stu-id="7e72b-174">[Previous](data.md)
[Next](config.md)</span></span>
