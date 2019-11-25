---
ms.openlocfilehash: ac5a3c4f3aefbb59418ad92b2d795f36916f877f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394217"
---
### <a name="spas-spaservices-and-nodeservices-marked-obsolete"></a>Одностраничные приложения. SpaServices и NodeServices отмечены как устаревшие

Содержимое указанных ниже пакетов NuGet стало полностью ненужным, начиная с версии ASP.NET Core 2.1. Поэтому они отмечены как устаревшие:

- [Microsoft.AspNetCore.SpaServices](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices/);
- [Microsoft.AspNetCore.NodeServices](https://www.nuget.org/packages/Microsoft.AspNetCore.NodeServices/).

По той же причине следующие модули npm отмечены как нерекомендуемые:

- [aspnet-angular](https://www.npmjs.com/package/aspnet-angular);
- [aspnet-prerendering](https://www.npmjs.com/package/aspnet-prerendering);
- [aspnet-webpack](https://www.npmjs.com/package/aspnet-webpack);
- [aspnet-webpack-react](https://www.npmjs.com/package/aspnet-webpack-react);
- [domain-task](https://www.npmjs.com/package/domain-task).

Все указанные выше пакеты и модули npm будут удалены в версии .NET 5.

#### <a name="version-introduced"></a>Представленная версия

3.0

#### <a name="old-behavior"></a>Старое поведение

Нерекомендуемые пакеты и модули NPM предназначались для интеграции ASP.NET Core с разными платформами одностраничных приложений (SPA). К ним относятся Angular, React и React с Redux.

#### <a name="new-behavior"></a>Новое поведение

В пакете NuGet [Microsoft.AspNetCore.SpaServices.Extensions](https://www.nuget.org/packages/Microsoft.AspNetCore.SpaServices.Extensions/) реализован новый механизм интеграции. Этот пакет остается основой для шаблонов проектов Angular и React, начиная с ASP.NET Core 2.1.

#### <a name="reason-for-change"></a>Причина изменения

ASP.NET Core поддерживает интеграцию с несколькими платформами одностраничных приложений (SPA), включая Angular, React и React с Redux. Изначально интеграция с этими платформами устанавливалась с помощью специальных компонентов ASP.NET Core, которые обрабатывали такие сценарии, как предварительная визуализация на стороне сервера и интеграция с пакетом Webpack. Но отраслевые стандарты постепенно изменились. На каждой из этих платформ SPA подготовлены собственные стандартные интерфейсы командной строки. Например, Angular CLI и create-react-app.

При выпуске ASP.NET Core 2.1 в мае 2018 года наши разработчики внесли обновления в соответствии с этим изменением стандартов. Мы предоставили новый и более простой способ для интеграции с цепочками инструментов разных платформ SPA. Новый механизм интеграции реализован в пакете `Microsoft.AspNetCore.SpaServices.Extensions` и стал основой для шаблонов проектов Angular и React, начиная с ASP.NET Core 2.1.

Чтобы не оставалось сомнений, что старые специальные компоненты ASP.NET Core стали не нужны и их использование не рекомендуется, внесены следующие изменения:

- механизм интеграции, существовавший до версии 2.1, отмечен как устаревший;
- вспомогательные пакеты npm отмечены как нерекомендуемые.

#### <a name="recommended-action"></a>Рекомендуемое действие

Если вы применяете эти пакеты, обновите приложения, чтобы они использовали следующие функции:

- содержащиеся в пакете `Microsoft.AspNetCore.SpaServices.Extensions`;
- предоставленные той платформой SPA, которую вы используете.

Чтобы поддерживать такие функции, как предварительная визуализация на стороне сервера и горячая перезагрузка модулей, изучите документацию по соответствующей платформе SPA. Функциональность `Microsoft.AspNetCore.SpaServices.Extensions` *не* считается устаревшей и будет поддерживаться далее.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.Builder.SpaRouteExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.WebpackDevMiddleware?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.INodeServices?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesFactory?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.NodeServicesOptions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.StringAsTempFile?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance?displayProperty=nameWithType>

- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions?displayProperty=nameWithType>

- <xref:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Builder.SpaRouteExtensions`
- `T:Microsoft.AspNetCore.Builder.WebpackDevMiddleware`

- `T:Microsoft.AspNetCore.NodeServices.EmbeddedResourceReader`
- `T:Microsoft.AspNetCore.NodeServices.INodeServices`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesFactory`
- `T:Microsoft.AspNetCore.NodeServices.NodeServicesOptions`
- `T:Microsoft.AspNetCore.NodeServices.StringAsTempFile`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.INodeInstance`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationException`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeInvocationInfo`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.NodeServicesOptionsExtensions`
- `T:Microsoft.AspNetCore.NodeServices.HostingModels.OutOfProcessNodeInstance`

- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.ISpaPrerendererBuilder`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.JavaScriptModuleExport`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.Prerenderer`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.PrerenderTagHelper`
- `T:Microsoft.AspNetCore.SpaServices.Prerendering.RenderToStringResult`
- `T:Microsoft.AspNetCore.SpaServices.Webpack.WebpackDevMiddlewareOptions`

- `T:Microsoft.Extensions.DependencyInjection.NodeServicesServiceCollectionExtensions`
- `T:Microsoft.Extensions.DependencyInjection.PrerenderingServiceCollectionExtensions`

-->
