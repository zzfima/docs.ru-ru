---
ms.openlocfilehash: e0d0a680915f14c2d33f1864ad5ad05aff3dde5f
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394079"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="791a4-101">HTTP. Изменение констант HeaderNames изменены на статические только для чтения</span><span class="sxs-lookup"><span data-stu-id="791a4-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="791a4-102">Начиная с ASP.NET Core 3.0 (предварительная версия 5), поля в <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> изменились с `const` на `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="791a4-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="791a4-103">Обсуждение этого вопроса см. на странице [aspnet/AspNetCore#9514](https://github.com/aspnet/AspNetCore/issues/9514).</span><span class="sxs-lookup"><span data-stu-id="791a4-103">For discussion, see [aspnet/AspNetCore#9514](https://github.com/aspnet/AspNetCore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="791a4-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="791a4-104">Version introduced</span></span>

<span data-ttu-id="791a4-105">3.0</span><span class="sxs-lookup"><span data-stu-id="791a4-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="791a4-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="791a4-106">Old behavior</span></span>

<span data-ttu-id="791a4-107">Эти поля использовались для `const`.</span><span class="sxs-lookup"><span data-stu-id="791a4-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="791a4-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="791a4-108">New behavior</span></span>

<span data-ttu-id="791a4-109">Теперь эти поля являются `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="791a4-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="791a4-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="791a4-110">Reason for change</span></span>

<span data-ttu-id="791a4-111">Изменение:</span><span class="sxs-lookup"><span data-stu-id="791a4-111">The change:</span></span>

* <span data-ttu-id="791a4-112">предотвращает встраивание значений между границами сборки, что позволяет корректировать значения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="791a4-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="791a4-113">обеспечивает более быстрые проверки равенства ссылок.</span><span class="sxs-lookup"><span data-stu-id="791a4-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="791a4-114">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="791a4-114">Recommended action</span></span>

<span data-ttu-id="791a4-115">Выполните перекомпиляцию для версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="791a4-115">Recompile against 3.0.</span></span> <span data-ttu-id="791a4-116">Исходный код, использующий эти поля следующими способами, больше не поддерживает эту возможность:</span><span class="sxs-lookup"><span data-stu-id="791a4-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="791a4-117">как аргумент атрибута;</span><span class="sxs-lookup"><span data-stu-id="791a4-117">As an attribute argument</span></span>
* <span data-ttu-id="791a4-118">как `case` в операторе `switch`;</span><span class="sxs-lookup"><span data-stu-id="791a4-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="791a4-119">при определении `const`.</span><span class="sxs-lookup"><span data-stu-id="791a4-119">When defining another `const`</span></span>

<span data-ttu-id="791a4-120">Чтобы обойти критическое изменение, переключитесь на использование самостоятельно определенных констант имен заголовков или строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="791a4-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="791a4-121">Категория</span><span class="sxs-lookup"><span data-stu-id="791a4-121">Category</span></span>

<span data-ttu-id="791a4-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="791a4-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="791a4-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="791a4-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
