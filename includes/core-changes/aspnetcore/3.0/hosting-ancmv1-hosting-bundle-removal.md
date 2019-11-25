---
ms.openlocfilehash: 04e5ca41374fc333a31f0422bc2e89f54b3cb049
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394294"
---
### <a name="hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle"></a><span data-ttu-id="402a2-101">Размещение. Модуль AspNetCoreModule версии 1 не входит в пакет размещения Windows</span><span class="sxs-lookup"><span data-stu-id="402a2-101">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>

<span data-ttu-id="402a2-102">Начиная с ASP.NET Core 3.0, пакет размещения Windows не будет содержать AspNetCoreModule (ANCM) версии 1.</span><span class="sxs-lookup"><span data-stu-id="402a2-102">Starting with ASP.NET Core 3.0, the Windows Hosting Bundle won't contain AspNetCoreModule (ANCM) V1.</span></span>

<span data-ttu-id="402a2-103">ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="402a2-103">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="402a2-104">Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).</span><span class="sxs-lookup"><span data-stu-id="402a2-104">For discussion, see [aspnet/AspNetCore#7095](https://github.com/aspnet/AspNetCore/issues/7095).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="402a2-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="402a2-105">Version introduced</span></span>

<span data-ttu-id="402a2-106">3.0</span><span class="sxs-lookup"><span data-stu-id="402a2-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="402a2-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="402a2-107">Old behavior</span></span>

<span data-ttu-id="402a2-108">ANCM версии 1 входит в состав пакета размещения Windows.</span><span class="sxs-lookup"><span data-stu-id="402a2-108">ANCM V1 is included in the Windows Hosting Bundle.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="402a2-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="402a2-109">New behavior</span></span>

<span data-ttu-id="402a2-110">ANCM версии 1 не входит в состав пакета размещения Windows.</span><span class="sxs-lookup"><span data-stu-id="402a2-110">ANCM V1 isn't included in the Windows Hosting Bundle.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="402a2-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="402a2-111">Reason for change</span></span>

<span data-ttu-id="402a2-112">ANCM версии 2 обеспечивает обратную совместимость с ANCM OutOfProcess и рекомендуется для использования с приложениями ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="402a2-112">ANCM V2 is backwards compatible with ANCM OutOfProcess and is recommended for use with ASP.NET Core 3.0 apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="402a2-113">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="402a2-113">Recommended action</span></span>

<span data-ttu-id="402a2-114">Используйте ANCM версии 2 с приложениями ASP.NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="402a2-114">Use ANCM V2 with ASP.NET Core 3.0 apps.</span></span>

<span data-ttu-id="402a2-115">Если требуется ANCM версии 1, выполните установку с помощью пакета размещения Windows ASP.NET Core 2.1 или 2.2.</span><span class="sxs-lookup"><span data-stu-id="402a2-115">If ANCM V1 is required, it can be installed using the ASP.NET Core 2.1 or 2.2 Windows Hosting Bundle.</span></span>

<span data-ttu-id="402a2-116">Это изменение приведет к нарушению работы приложений ASP.NET Core 3.0, которые:</span><span class="sxs-lookup"><span data-stu-id="402a2-116">This change will break ASP.NET Core 3.0 apps that:</span></span>

- <span data-ttu-id="402a2-117">явно настроены использовать ANCM версии 1 с `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`;</span><span class="sxs-lookup"><span data-stu-id="402a2-117">Explicitly opted into using ANCM V1 with `<AspNetCoreModuleName>AspNetCoreModule</AspNetCoreModuleName>`.</span></span>
- <span data-ttu-id="402a2-118">имеют пользовательский файл *web.config* с `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span><span class="sxs-lookup"><span data-stu-id="402a2-118">Have a custom *web.config* file with `<add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModule" resourceType="Unspecified" />`.</span></span>

#### <a name="category"></a><span data-ttu-id="402a2-119">Категория</span><span class="sxs-lookup"><span data-stu-id="402a2-119">Category</span></span>

<span data-ttu-id="402a2-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="402a2-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="402a2-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="402a2-121">Affected APIs</span></span>

<span data-ttu-id="402a2-122">Нет</span><span class="sxs-lookup"><span data-stu-id="402a2-122">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
