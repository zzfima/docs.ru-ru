---
ms.openlocfilehash: a916af91670dc9c5ceb2ff759cd8ae308fb2c2dc
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394367"
---
### <a name="kestrel-connection-adapters-removed"></a><span data-ttu-id="838c2-101">Kestrel. Адаптеры подключений удалены</span><span class="sxs-lookup"><span data-stu-id="838c2-101">Kestrel: Connection adapters removed</span></span>

<span data-ttu-id="838c2-102">В рамках переноса API pubternal в `public` концепция `IConnectionAdapter` была удалена из Kestrel.</span><span class="sxs-lookup"><span data-stu-id="838c2-102">As part of the move to move "pubternal" APIs to `public`, the concept of an `IConnectionAdapter` was removed from Kestrel.</span></span> <span data-ttu-id="838c2-103">Адаптеры подключений заменяются соответствующим ПО промежуточного слоя, которое похоже на ПО промежуточного слоя HTTP в конвейере ASP.NET Core, но для подключений более низкого уровня.</span><span class="sxs-lookup"><span data-stu-id="838c2-103">Connection adapters are being replaced with connection middleware (similar to HTTP middleware in the ASP.NET Core pipeline, but for lower-level connections).</span></span> <span data-ttu-id="838c2-104">Журналы подключений и HTTPS перемещены из адаптеров соединений в соответствующее ПО промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="838c2-104">HTTPS and connection logging have moved from connection adapters to connection middleware.</span></span> <span data-ttu-id="838c2-105">Эти методы расширения должны и дальше работать без проблем, но детали реализации изменились.</span><span class="sxs-lookup"><span data-stu-id="838c2-105">Those extension methods should continue to work seamlessly, but the implementation details have changed.</span></span>

<span data-ttu-id="838c2-106">Подробную информацию см. на странице [aspnet/AspNetCore#11412](https://github.com/aspnet/AspNetCore/pull/11412).</span><span class="sxs-lookup"><span data-stu-id="838c2-106">For more information, see [aspnet/AspNetCore#11412](https://github.com/aspnet/AspNetCore/pull/11412).</span></span> <span data-ttu-id="838c2-107">Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#11475](https://github.com/aspnet/AspNetCore/issues/11475).</span><span class="sxs-lookup"><span data-stu-id="838c2-107">For discussion, see [aspnet/AspNetCore#11475](https://github.com/aspnet/AspNetCore/issues/11475).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="838c2-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="838c2-108">Version introduced</span></span>

<span data-ttu-id="838c2-109">3.0</span><span class="sxs-lookup"><span data-stu-id="838c2-109">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="838c2-110">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="838c2-110">Old behavior</span></span>

<span data-ttu-id="838c2-111">Компоненты расширяемости Kestrel были созданы с помощью `IConnectionAdapter`.</span><span class="sxs-lookup"><span data-stu-id="838c2-111">Kestrel extensibility components were created using `IConnectionAdapter`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="838c2-112">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="838c2-112">New behavior</span></span>

<span data-ttu-id="838c2-113">Компоненты расширяемости Kestrel созданы с помощью [ПО промежуточного слоя](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span><span class="sxs-lookup"><span data-stu-id="838c2-113">Kestrel extensibility components are created as [middleware](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="838c2-114">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="838c2-114">Reason for change</span></span>

<span data-ttu-id="838c2-115">Это изменение предназначено для обеспечения более гибкой архитектуры расширяемости.</span><span class="sxs-lookup"><span data-stu-id="838c2-115">This change is intended to provide a more flexible extensibility architecture.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="838c2-116">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="838c2-116">Recommended action</span></span>

<span data-ttu-id="838c2-117">Преобразуйте все реализации `IConnectionAdapter`, чтобы [использовать новый шаблон ПО промежуточного слоя](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span><span class="sxs-lookup"><span data-stu-id="838c2-117">Convert any implementations of `IConnectionAdapter` to use the new middleware pattern as shown [here](https://github.com/aspnet/AspNetCore/pull/11412/files#diff-89acc06acf1b2e96bbdb811ce523619f).</span></span>

#### <a name="category"></a><span data-ttu-id="838c2-118">Категория</span><span class="sxs-lookup"><span data-stu-id="838c2-118">Category</span></span>

<span data-ttu-id="838c2-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="838c2-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="838c2-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="838c2-120">Affected APIs</span></span>

`Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

<!-- 

#### Affected APIs

`T:Microsoft.AspNetCore.Server.Kestrel.Core.Adapter.Internal.IConnectionAdapter`

-->
