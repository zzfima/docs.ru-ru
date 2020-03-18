---
ms.openlocfilehash: 82103d82a6f68c62f3532608718bc71b0ba126bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901910"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="39e16-101">Размещение. Модуль AspNetCoreModule версии 1 не входит в пакет размещения Windows</span><span class="sxs-lookup"><span data-stu-id="39e16-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="39e16-102">Начиная с ASP.NET Core 3.0, пакет размещения Windows не будет содержать AspNetCoreModule (ANCM) версии 1.</span><span class="sxs-lookup"><span data-stu-id="39e16-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="39e16-103">ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="39e16-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="39e16-104">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="39e16-104">For discussion, see [dotnet/aspnetcore#7095](https://github.com/dotnet/aspnetcore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="39e16-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="39e16-105">Version introduced</span></span>

<span data-ttu-id="39e16-106">3.0</span><span class="sxs-lookup"><span data-stu-id="39e16-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="39e16-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="39e16-107">Old behavior</span></span>

<span data-ttu-id="39e16-108">ANCM версии 1 входит в состав пакета размещения Windows.</span><span class="sxs-lookup"><span data-stu-id="39e16-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="39e16-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="39e16-109">New behavior</span></span>

<span data-ttu-id="39e16-110">ANCM версии 1 не входит в состав пакета размещения Windows.</span><span class="sxs-lookup"><span data-stu-id="39e16-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="39e16-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="39e16-111">Reason for change</span></span>

<span data-ttu-id="39e16-112">ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="39e16-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="39e16-113">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="39e16-113">Recommended action</span></span>

<span data-ttu-id="39e16-114">Используйте ANCM версии 2 с приложениями ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="39e16-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="39e16-115">Если требуется ANCM версии 1, выполните установку с помощью пакета размещения Windows ASP.NET Core 2.1 или 2.2.</span><span class="sxs-lookup"><span data-stu-id="39e16-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="39e16-116">Это изменение приведет к нарушению работы приложений ASP.NET Core 3.0, которые:</span><span class="sxs-lookup"><span data-stu-id="39e16-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="39e16-117">явно настроены использовать ANCM версии 1 с `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`;</span><span class="sxs-lookup"><span data-stu-id="39e16-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="39e16-118">имеют пользовательский файл *web.config* с `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span><span class="sxs-lookup"><span data-stu-id="39e16-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="39e16-119">Категория</span><span class="sxs-lookup"><span data-stu-id="39e16-119">Category</span></span>

<span data-ttu-id="39e16-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="39e16-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="39e16-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="39e16-121">Affected APIs</span></span>

<span data-ttu-id="39e16-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="39e16-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
