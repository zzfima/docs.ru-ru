---
ms.openlocfilehash: 09fd95ba5f3aee59f2abdfbb4e64eb6202e2b873
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394025"
---
### <a name="mvc-pubternal-types-changed-to-internal"></a><span data-ttu-id="0f525-101">MVC. Типы Pubternal теперь стали внутренними</span><span class="sxs-lookup"><span data-stu-id="0f525-101">MVC: "Pubternal" types changed to internal</span></span>

<span data-ttu-id="0f525-102">В ASP.NET Core 3.0 все типы pubternal (MVC) теперь стали `public` в поддерживаемом пространстве имен либо `internal`, если это более уместно.</span><span class="sxs-lookup"><span data-stu-id="0f525-102">In ASP.NET Core 3.0, all "pubternal" types in MVC were updated to either be `public` in a supported namespace or `internal` as appropriate.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0f525-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="0f525-103">Change description</span></span>

<span data-ttu-id="0f525-104">В ASP.NET Core типы pubternal объявляются как `public`, но находятся в пространстве имен с суффиксом `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="0f525-104">In ASP.NET Core, "pubternal" types are declared as `public` but reside in a `.Internal`-suffixed namespace.</span></span> <span data-ttu-id="0f525-105">Хотя формально это типы `public`, для них отсутствует политика поддержки и они подвержены критическим изменениям.</span><span class="sxs-lookup"><span data-stu-id="0f525-105">While these types are `public`, they have no support policy and are subject to breaking changes.</span></span> <span data-ttu-id="0f525-106">К сожалению, довольно часто эти типы использовались случайно, что приводило к критическим изменениям в таких проектах и ограничивало возможности, связанные с обслуживанием платформы.</span><span class="sxs-lookup"><span data-stu-id="0f525-106">Unfortunately, accidental use of these types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0f525-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="0f525-107">Version introduced</span></span>

<span data-ttu-id="0f525-108">3.0</span><span class="sxs-lookup"><span data-stu-id="0f525-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="0f525-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="0f525-109">Old behavior</span></span>

<span data-ttu-id="0f525-110">Некоторые типы в MVC имели тип `public`, но существовали в пространстве имен `.Internal`.</span><span class="sxs-lookup"><span data-stu-id="0f525-110">Some types in MVC were `public` but in a `.Internal` namespace.</span></span> <span data-ttu-id="0f525-111">Для таких типов отсутствует политика поддержки и они подвержены критическим изменениям.</span><span class="sxs-lookup"><span data-stu-id="0f525-111">These types had no support policy and were subject to breaking changes.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="0f525-112">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="0f525-112">New behavior</span></span>

<span data-ttu-id="0f525-113">Все такие типы теперь стали `public` в поддерживаемом пространстве имен, либо помечены как `internal`.</span><span class="sxs-lookup"><span data-stu-id="0f525-113">All such types are updated either to be `public` in a supported namespace or marked as `internal`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0f525-114">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="0f525-114">Reason for change</span></span>

<span data-ttu-id="0f525-115">Довольно часто типы pubternal использовались случайно, что приводило к критическим изменениям в таких проектах и ограничивало возможности по обслуживанию платформы.</span><span class="sxs-lookup"><span data-stu-id="0f525-115">Accidental use of the "pubternal" types has been common, resulting in breaking changes to these projects and limiting the ability to maintain the framework.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0f525-116">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="0f525-116">Recommended action</span></span>

<span data-ttu-id="0f525-117">Если вы используете типы, которые стали `public` и перемещены в новое поддерживаемое пространство имен, обновите ссылки на них соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="0f525-117">If you're using types that have become truly `public` and have been moved into a new, supported namespace, update your references to match the new namespaces.</span></span>

<span data-ttu-id="0f525-118">Если вы используете типы, которые стали `internal`, замените их разумной альтернативой.</span><span class="sxs-lookup"><span data-stu-id="0f525-118">If you're using types that have become marked as `internal`, you'll need to find an alternative.</span></span> <span data-ttu-id="0f525-119">Общедоступное использование типов pubternal никогда не считалось поддерживаемым сценарием.</span><span class="sxs-lookup"><span data-stu-id="0f525-119">The previously "pubternal" types were never supported for public use.</span></span> <span data-ttu-id="0f525-120">Если в этих пространствах имен есть некоторые типы, которые критически важны для ваших приложений, сообщите об этой проблеме в [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span><span class="sxs-lookup"><span data-stu-id="0f525-120">If there are specific types in these namespaces that are critical to your apps, file an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span> <span data-ttu-id="0f525-121">Мы готовы рассмотреть возможность преобразовать эти типы в `public`.</span><span class="sxs-lookup"><span data-stu-id="0f525-121">Considerations may be made for making the requested types `public`.</span></span>

#### <a name="category"></a><span data-ttu-id="0f525-122">Категория</span><span class="sxs-lookup"><span data-stu-id="0f525-122">Category</span></span>

<span data-ttu-id="0f525-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="0f525-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0f525-124">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0f525-124">Affected APIs</span></span>

<span data-ttu-id="0f525-125">Это изменение затронуло следующие пространства имен:</span><span class="sxs-lookup"><span data-stu-id="0f525-125">This change includes types in the following namespaces:</span></span>

- `Microsoft.AspNetCore.Mvc.Cors.Internal`
- `Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `Microsoft.AspNetCore.Mvc.Internal`
- `Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `Microsoft.AspNetCore.Mvc.Razor.Internal`
- `Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

<!--

#### Affected APIs

- `N:Microsoft.AspNetCore.Mvc.Cors.Internal`
- `N:Microsoft.AspNetCore.Mvc.DataAnnotations.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Json.Internal`
- `N:Microsoft.AspNetCore.Mvc.Formatters.Xml.Internal`
- `N:Microsoft.AspNetCore.Mvc.Internal`
- `N:Microsoft.AspNetCore.Mvc.ModelBinding.Internal`
- `N:Microsoft.AspNetCore.Mvc.Razor.Internal`
- `N:Microsoft.AspNetCore.Mvc.RazorPages.Internal`
- `N:Microsoft.AspNetCore.Mvc.TagHelpers.Internal`
- `N:Microsoft.AspNetCore.Mvc.ViewFeatures.Internal`

-->
