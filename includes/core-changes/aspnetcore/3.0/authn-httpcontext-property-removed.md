---
ms.openlocfilehash: 60ebcd9fc9ca18c33d31b82ba5020426d22a7d5a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901809"
---
### <a name="authentication-httpcontextauthentication-property-removed"></a><span data-ttu-id="8140b-101">Аутентификация. Удаление свойства HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="8140b-101">Authentication: HttpContext.Authentication property removed</span></span>

<span data-ttu-id="8140b-102">Устаревшее свойство `Authentication` в `HttpContext` было удалено.</span><span class="sxs-lookup"><span data-stu-id="8140b-102">The deprecated `Authentication` property on `HttpContext` has been removed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8140b-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="8140b-103">Change description</span></span>

<span data-ttu-id="8140b-104">В рамках [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504) устаревшее свойство `Authentication` в `HttpContext` было удалено.</span><span class="sxs-lookup"><span data-stu-id="8140b-104">As part of [dotnet/aspnetcore#6504](https://github.com/dotnet/aspnetcore/pull/6504), the deprecated `Authentication` property on `HttpContext` has been removed.</span></span> <span data-ttu-id="8140b-105">Свойство `Authentication` не рекомендуется к использованию, начиная с версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="8140b-105">The `Authentication` property has been deprecated since 2.0.</span></span> <span data-ttu-id="8140b-106">Были опубликованы [инструкции по переносу кода](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) с использованием этого устаревшего свойства в новые API замены.</span><span class="sxs-lookup"><span data-stu-id="8140b-106">A [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions) was published to migrate code using this deprecated property to the new replacement APIs.</span></span> <span data-ttu-id="8140b-107">Оставшиеся неиспользуемые классы и API, относящиеся к старому стеку проверки подлинности ASP.NET Core 1.x, были удалены в фиксации [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span><span class="sxs-lookup"><span data-stu-id="8140b-107">The remaining unused classes / APIs related to the old ASP.NET Core 1.x authentication stack were removed in commit [dotnet/aspnetcore@d7a7c65](https://github.com/dotnet/aspnetcore/commit/d7a7c65).</span></span>

<span data-ttu-id="8140b-108">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span><span class="sxs-lookup"><span data-stu-id="8140b-108">For discussion, see [dotnet/aspnetcore#6533](https://github.com/dotnet/aspnetcore/issues/6533).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8140b-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="8140b-109">Version introduced</span></span>

<span data-ttu-id="8140b-110">3.0</span><span class="sxs-lookup"><span data-stu-id="8140b-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8140b-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="8140b-111">Reason for change</span></span>

<span data-ttu-id="8140b-112">ASP.NET Core API 1.0 были заменены методами расширения в <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="8140b-112">ASP.NET Core 1.0 APIs have been replaced by extension methods in <xref:Microsoft.AspNetCore.Authentication.AuthenticationHttpContextExtensions?displayProperty=fullName>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8140b-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="8140b-113">Recommended action</span></span>

<span data-ttu-id="8140b-114">См. [руководство по переносу](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span><span class="sxs-lookup"><span data-stu-id="8140b-114">See the [migration guide](/aspnet/core/migration/1x-to-2x/identity-2x?view=aspnetcore-2.2#use-httpcontext-authentication-extensions).</span></span>

#### <a name="category"></a><span data-ttu-id="8140b-115">Категория</span><span class="sxs-lookup"><span data-stu-id="8140b-115">Category</span></span>

<span data-ttu-id="8140b-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8140b-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8140b-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="8140b-117">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpContext.Authentication?displayProperty=fullName>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticateInfo`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationManager`
- `T:Microsoft.AspNetCore.Http.Authentication.AuthenticationProperties`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.AuthenticateContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeBehavior`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.ChallengeContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.DescribeSchemesContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.IAuthenticationHandler`
- `P:Microsoft.AspNetCore.Http.Features.Authentication.IHttpAuthenticationFeature.Handler`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignInContext`
- `T:Microsoft.AspNetCore.Http.Features.Authentication.SignOutContext`
- `P:Microsoft.AspNetCore.Http.HttpContext.Authentication`

-->
