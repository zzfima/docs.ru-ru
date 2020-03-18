---
ms.openlocfilehash: 806722ea9aec1c828786525e3155b7f624159ac1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "72522670"
---
### <a name="identity-adddefaultui-method-overload-removed"></a><span data-ttu-id="414b8-101">Удостоверение: перегрузка метода AddDefaultUI устранена</span><span class="sxs-lookup"><span data-stu-id="414b8-101">Identity: AddDefaultUI method overload removed</span></span>

<span data-ttu-id="414b8-102">Начиная с ASP.NET Core 3.0 перегрузка метода <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> больше не существует.</span><span class="sxs-lookup"><span data-stu-id="414b8-102">Starting with ASP.NET Core 3.0, the <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=nameWithType> method overload no longer exists.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="414b8-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="414b8-103">Version introduced</span></span>

<span data-ttu-id="414b8-104">3.0</span><span class="sxs-lookup"><span data-stu-id="414b8-104">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="414b8-105">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="414b8-105">Reason for change</span></span>

<span data-ttu-id="414b8-106">Это изменение было результатом внедрения функции статических веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="414b8-106">This change was a result of adoption of the static web assets feature.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="414b8-107">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="414b8-107">Recommended action</span></span>

<span data-ttu-id="414b8-108">Вызывайте <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> вместо перегрузки.</span><span class="sxs-lookup"><span data-stu-id="414b8-108">Call <xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder)?displayProperty=nameWithType> instead of the overload.</span></span> <span data-ttu-id="414b8-109">Если вы используете Bootstrap 3, добавьте следующую строку в элемент `<PropertyGroup>` в файле проекта:</span><span class="sxs-lookup"><span data-stu-id="414b8-109">If you're using Bootstrap 3, also add the following line to a `<PropertyGroup>` element in your project file:</span></span>

```xml
<IdentityUIFrameworkVersion>Bootstrap3</IdentityUIFrameworkVersion>
```

#### <a name="category"></a><span data-ttu-id="414b8-110">Категория</span><span class="sxs-lookup"><span data-stu-id="414b8-110">Category</span></span>

<span data-ttu-id="414b8-111">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="414b8-111">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="414b8-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="414b8-112">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)?displayProperty=fullName>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Identity.IdentityBuilderUIExtensions.AddDefaultUI(Microsoft.AspNetCore.Identity.IdentityBuilder,Microsoft.AspNetCore.Identity.UI.UIFramework)`

-->
