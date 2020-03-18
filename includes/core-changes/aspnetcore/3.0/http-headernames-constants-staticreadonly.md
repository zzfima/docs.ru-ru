---
ms.openlocfilehash: 31e7f84a787d255a474f4c2b1fa3068903dbed52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901754"
---
### <a name="http-headernames-constants-changed-to-static-readonly"></a><span data-ttu-id="be783-101">HTTP. Изменение констант HeaderNames изменены на статические только для чтения</span><span class="sxs-lookup"><span data-stu-id="be783-101">HTTP: HeaderNames constants changed to static readonly</span></span>

<span data-ttu-id="be783-102">Начиная с ASP.NET Core 3.0 (предварительная версия 5), поля в <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> изменились с `const` на `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="be783-102">Starting in ASP.NET Core 3.0 Preview 5, the fields in <xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName> changed from `const` to `static readonly`.</span></span>

<span data-ttu-id="be783-103">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span><span class="sxs-lookup"><span data-stu-id="be783-103">For discussion, see [dotnet/aspnetcore#9514](https://github.com/dotnet/aspnetcore/issues/9514).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="be783-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="be783-104">Version introduced</span></span>

<span data-ttu-id="be783-105">3.0</span><span class="sxs-lookup"><span data-stu-id="be783-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="be783-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="be783-106">Old behavior</span></span>

<span data-ttu-id="be783-107">Эти поля использовались для `const`.</span><span class="sxs-lookup"><span data-stu-id="be783-107">These fields used to be `const`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="be783-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="be783-108">New behavior</span></span>

<span data-ttu-id="be783-109">Теперь эти поля являются `static readonly`.</span><span class="sxs-lookup"><span data-stu-id="be783-109">These fields are now `static readonly`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="be783-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="be783-110">Reason for change</span></span>

<span data-ttu-id="be783-111">Изменение:</span><span class="sxs-lookup"><span data-stu-id="be783-111">The change:</span></span>

* <span data-ttu-id="be783-112">предотвращает встраивание значений между границами сборки, что позволяет корректировать значения по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="be783-112">Prevents the values from being embedded across assembly boundaries, allowing for value corrections as needed.</span></span>
* <span data-ttu-id="be783-113">обеспечивает более быстрые проверки равенства ссылок.</span><span class="sxs-lookup"><span data-stu-id="be783-113">Enables faster reference equality checks.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="be783-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="be783-114">Recommended action</span></span>

<span data-ttu-id="be783-115">Выполните перекомпиляцию для версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="be783-115">Recompile against 3.0.</span></span> <span data-ttu-id="be783-116">Исходный код, использующий эти поля следующими способами, больше не поддерживает эту возможность:</span><span class="sxs-lookup"><span data-stu-id="be783-116">Source code using these fields in the following ways can no longer do so:</span></span>

* <span data-ttu-id="be783-117">как аргумент атрибута;</span><span class="sxs-lookup"><span data-stu-id="be783-117">As an attribute argument</span></span>
* <span data-ttu-id="be783-118">как `case` в операторе `switch`;</span><span class="sxs-lookup"><span data-stu-id="be783-118">As a `case` in a `switch` statement</span></span>
* <span data-ttu-id="be783-119">при определении `const`.</span><span class="sxs-lookup"><span data-stu-id="be783-119">When defining another `const`</span></span>

<span data-ttu-id="be783-120">Чтобы обойти критическое изменение, переключитесь на использование самостоятельно определенных констант имен заголовков или строковых литералов.</span><span class="sxs-lookup"><span data-stu-id="be783-120">To work around the breaking change, switch to using self-defined header name constants or string literals.</span></span>

#### <a name="category"></a><span data-ttu-id="be783-121">Категория</span><span class="sxs-lookup"><span data-stu-id="be783-121">Category</span></span>

<span data-ttu-id="be783-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="be783-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="be783-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="be783-123">Affected APIs</span></span>

<xref:Microsoft.Net.Http.Headers.HeaderNames?displayProperty=fullName>

<!-- 

#### Affected APIs

`T:Microsoft.Net.Http.Headers.HeaderNames`

-->
