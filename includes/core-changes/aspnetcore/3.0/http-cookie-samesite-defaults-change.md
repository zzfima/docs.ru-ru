---
ms.openlocfilehash: 15ba678431b97e7c961c119d83546569bdf9bad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "74282523"
---
### <a name="http-some-cookie-samesite-defaults-changed-to-none"></a><span data-ttu-id="a13e1-101">HTTP. Некоторые значения по умолчанию параметра SameSite для файлов cookie изменены на None</span><span class="sxs-lookup"><span data-stu-id="a13e1-101">HTTP: Some cookie SameSite defaults changed to None</span></span>

<span data-ttu-id="a13e1-102">`SameSite` — это параметр для файлов cookie, который помогает предотвращать некоторые атаки с подделкой межсайтовых запросов.</span><span class="sxs-lookup"><span data-stu-id="a13e1-102">`SameSite` is an option for cookies that can help mitigate some Cross-Site Request Forgery (CSRF) attacks.</span></span> <span data-ttu-id="a13e1-103">Когда этот параметр изначально появился, в разных интерфейсах API ASP.NET Core использовались несогласованные значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a13e1-103">When this option was initially introduced, inconsistent defaults were used across various ASP.NET Core APIs.</span></span> <span data-ttu-id="a13e1-104">Это приводило к путанице в результатах.</span><span class="sxs-lookup"><span data-stu-id="a13e1-104">The inconsistency has led to confusing results.</span></span> <span data-ttu-id="a13e1-105">Начиная с версии ASP.NET Core 3.0, значения по умолчанию стали более согласованными.</span><span class="sxs-lookup"><span data-stu-id="a13e1-105">As of ASP.NET Core 3.0, these defaults are better aligned.</span></span> <span data-ttu-id="a13e1-106">Эту функцию необходимо включать отдельно для каждого метода.</span><span class="sxs-lookup"><span data-stu-id="a13e1-106">You must opt in to this feature on a per-component basis.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a13e1-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="a13e1-107">Version introduced</span></span>

<span data-ttu-id="a13e1-108">3.0</span><span class="sxs-lookup"><span data-stu-id="a13e1-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="a13e1-109">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="a13e1-109">Old behavior</span></span>

<span data-ttu-id="a13e1-110">В похожих интерфейсах API ASP.NET Core использовались разные значения по умолчанию параметра <xref:Microsoft.AspNetCore.Http.SameSiteMode>.</span><span class="sxs-lookup"><span data-stu-id="a13e1-110">Similar ASP.NET Core APIs used different default <xref:Microsoft.AspNetCore.Http.SameSiteMode> values.</span></span> <span data-ttu-id="a13e1-111">Примером несогласованности могут служить методы `HttpResponse.Cookies.Append(String, String)` и `HttpResponse.Cookies.Append(String, String, CookieOptions)` со значениями по умолчанию `SameSiteMode.None` и `SameSiteMode.Lax`соответственно.</span><span class="sxs-lookup"><span data-stu-id="a13e1-111">An example of the inconsistency is seen in `HttpResponse.Cookies.Append(String, String)` and `HttpResponse.Cookies.Append(String, String, CookieOptions)`, which defaulted to `SameSiteMode.None` and `SameSiteMode.Lax`, respectively.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="a13e1-112">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="a13e1-112">New behavior</span></span>

<span data-ttu-id="a13e1-113">Во всех затронутых интерфейсах API по умолчанию используется значение `SameSiteMode.None`.</span><span class="sxs-lookup"><span data-stu-id="a13e1-113">All the affected APIs default to `SameSiteMode.None`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="a13e1-114">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="a13e1-114">Reason for change</span></span>

<span data-ttu-id="a13e1-115">Значение по умолчанию было изменено, чтобы сделать функцию `SameSite` необязательной.</span><span class="sxs-lookup"><span data-stu-id="a13e1-115">The default value was changed to make `SameSite` an opt-in feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a13e1-116">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="a13e1-116">Recommended action</span></span>

<span data-ttu-id="a13e1-117">Для каждого компонента, создающего файлы cookie, необходимо принять решение об использовании параметра `SameSite`.</span><span class="sxs-lookup"><span data-stu-id="a13e1-117">Each component that emits cookies needs to decide if `SameSite` is appropriate for its scenarios.</span></span> <span data-ttu-id="a13e1-118">Проверьте использование затронутых интерфейсов API и при необходимости перенастройте параметр `SameSite`.</span><span class="sxs-lookup"><span data-stu-id="a13e1-118">Review your usage of the affected APIs and reconfigure `SameSite` as needed.</span></span>

#### <a name="category"></a><span data-ttu-id="a13e1-119">Категория</span><span class="sxs-lookup"><span data-stu-id="a13e1-119">Category</span></span>

<span data-ttu-id="a13e1-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a13e1-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a13e1-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="a13e1-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.Http.IResponseCookies.Append(System.String,System.String,Microsoft.AspNetCore.Http.CookieOptions)`
- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`

-->
