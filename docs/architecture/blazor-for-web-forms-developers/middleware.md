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
# <a name="modules-handlers-and-middleware"></a>Модули, обработчики и по промежуточного слоя

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

ASP.NET Core приложение строится на основе ряда по промежуточного слоя. По промежуточного слоя — это обработчики, которые упорядочены в конвейер для обработки запросов и ответов. В приложении веб-форм обработчики и модули HTTP решают аналогичные проблемы. В ASP.NET Core модули, обработчики, *Global.asax.CS*и жизненный цикл приложения заменяются по промежуточного слоя. В этой главе вы узнаете, какое по промежуточного слоя в контексте приложения Блазор.

## <a name="overview"></a>Обзор

Конвейер запросов ASP.NET Core состоит из последовательности делегатов запроса, вызываемых один за другим. На следующей схеме демонстрируется этот принцип. Поток выполнения показан черными стрелками.

![надстройк](media/middleware/request-delegate-pipeline.png)

На предыдущей схеме отсутствует концепция событий жизненного цикла. Эта концепция основана на том, как обрабатываются запросы ASP.NET Web Forms. Эта система упрощает причины того, что происходит, и позволяет вставлять по промежуточного слоя в любой момент. По промежуточного слоя выполняется в том порядке, в котором он добавляется в конвейер запросов. Они также добавляются в код вместо файлов конфигурации, обычно в *Startup.CS*.

## <a name="katana"></a>Katana

Читатели, знакомые с Katana, покажутся вам удобным ASP.NET Core. Фактически Katana — это платформа, от которой наследуется ASP.NET Core. В нем представлено аналогичное по промежуточного слоя и шаблоны конвейера для ASP.NET 4. x. По промежуточного слоя, разработанного для Katana, можно адаптировать для работы с конвейером ASP.NET Core.

## <a name="common-middleware"></a>Общее по промежуточного слоя

ASP.NET 4. x включает множество модулей. Аналогичным образом, ASP.NET Core имеет много компонентов по промежуточного слоя. В некоторых случаях в ASP.NET Core могут использоваться модули IIS. В других случаях может быть доступно собственное ASP.NET Core по промежуточного слоя.

В следующей таблице перечислены по промежуточного слоя и компоненты в ASP.NET Core.

|Модуль                 |Модуль ASP.NET 4. x           |ASP.NET Core, параметр|
|-----------------------|-----------------------------|-------------------|
|Ошибки HTTP            |`CustomErrorModule`          |[ПО промежуточного слоя для страниц кода состояния](/aspnet/core/fundamentals/error-handling#usestatuscodepages)|
|Документ по умолчанию       |`DefaultDocumentModule`      |[ПО промежуточного слоя для файлов по умолчанию](/aspnet/core/fundamentals/static-files#serve-a-default-document)|
|Просмотр каталогов     |`DirectoryListingModule`     |[ПО промежуточного слоя для просмотра каталогов](/aspnet/core/fundamentals/static-files#enable-directory-browsing)|
|Динамическое сжатие    |`DynamicCompressionModule`   |[ПО промежуточного слоя для сжатия ответов](/aspnet/core/performance/response-compression)|
|Трассировка неудачных запросов|`FailedRequestsTracingModule`|[Ведение журналов ASP.NET Core](/aspnet/core/fundamentals/logging/index#tracesource-provider)|
|Кэширование файлов           |`FileCacheModule`            |[ПО промежуточного слоя для кэширования ответов](/aspnet/core/performance/caching/middleware)|
|Кэширование HTTP           |`HttpCacheModule`            |[ПО промежуточного слоя для кэширования ответов](/aspnet/core/performance/caching/middleware)|
|Ведение журнала HTTP           |`HttpLoggingModule`          |[Ведение журналов ASP.NET Core](/aspnet/core/fundamentals/logging/index)|
|Перенаправление HTTP       |`HttpRedirectionModule`      |[ПО промежуточного слоя для переопределения URL-адресов](/aspnet/core/fundamentals/url-rewriting)|
|Фильтры ISAPI          |`IsapiFilterModule`          |[ПО промежуточного слоя](/aspnet/core/fundamentals/middleware/index)|
|ISAPI                  |`IsapiModule`                |[ПО промежуточного слоя](/aspnet/core/fundamentals/middleware/index)|
|Фильтрация запросов      |`RequestFilteringModule`     |[URL-адрес промежуточного слоя переопределения IRule](/aspnet/core/fundamentals/url-rewriting#irule-based-rule)|
|Перезапись URL-адресов&#8224;   |`RewriteModule`              |[ПО промежуточного слоя для переопределения URL-адресов](/aspnet/core/fundamentals/url-rewriting)|
|Статическое сжатие     |`StaticCompressionModule`    |[ПО промежуточного слоя для сжатия ответов](/aspnet/core/performance/response-compression)|
|Статическое содержимое         |`StaticFileModule`           |[ПО промежуточного слоя для статических файлов](/aspnet/core/fundamentals/static-files)|
|Авторизация URL-адреса      |`UrlAuthorizationModule`     |[Идентификация ASP.NET Core](/aspnet/core/security/authentication/identity)|

Этот список не является исчерпывающим, но должен понять, какое сопоставление существует между двумя платформами. Более подробный список см. в разделе [модули IIS с ASP.NET Core](/aspnet/core/host-and-deploy/iis/modules).

## <a name="custom-middleware"></a>Настраиваемое по промежуточного слоя

Встроенное по промежуточного слоя может не поддерживать все сценарии, необходимые для приложения. В таких случаях имеет смысл создать собственное по промежуточного слоя. Существует несколько способов определения по промежуточного слоя, с простым простым делегатом. Рассмотрим следующее по промежуточного слоя, которое принимает запрос языка и региональных параметров из строки запроса:

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

По промежуточного слоя можно также определить как класс, реализовав интерфейс `IMiddleware` или следуя правилам по промежуточного слоя. Дополнительные сведения см. в разделе [Создание пользовательского по промежуточного слоя ASP.NET Core](/aspnet/core/fundamentals/middleware/write).

>[!div class="step-by-step"]
>[Назад](data.md)
>[Вперед](config.md)
