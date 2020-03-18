---
ms.openlocfilehash: cd66317bc93343e03a73dec74dff534776ca42e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "73198547"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="50d78-101">HTTP. Изменения инфраструктуры текста ответа</span><span class="sxs-lookup"><span data-stu-id="50d78-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="50d78-102">Инфраструктура текста ответа HTTP изменена.</span><span class="sxs-lookup"><span data-stu-id="50d78-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="50d78-103">Если вы используете `HttpResponse` напрямую, вам не нужно вносить никаких изменений в код.</span><span class="sxs-lookup"><span data-stu-id="50d78-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="50d78-104">См. сведения ниже, если вы используете оболочку, заменяете `HttpResponse.Body` или обращаетесь к `HttpContext.Features`.</span><span class="sxs-lookup"><span data-stu-id="50d78-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="50d78-105">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="50d78-105">Version introduced</span></span>

<span data-ttu-id="50d78-106">3.0</span><span class="sxs-lookup"><span data-stu-id="50d78-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="50d78-107">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="50d78-107">Old behavior</span></span>

<span data-ttu-id="50d78-108">С текстом ответа HTTP связаны три API:</span><span class="sxs-lookup"><span data-stu-id="50d78-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="50d78-109">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="50d78-109">New behavior</span></span>

<span data-ttu-id="50d78-110">При замене `HttpResponse.Body` полностью заменяется `IHttpResponseBodyFeature` с оболочкой вокруг указанного потока с помощью `StreamResponseBodyFeature` для предоставления реализаций по умолчанию для всех ожидаемых API.</span><span class="sxs-lookup"><span data-stu-id="50d78-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="50d78-111">Возврат к исходному потоку отменяет это изменение.</span><span class="sxs-lookup"><span data-stu-id="50d78-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="50d78-112">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="50d78-112">Reason for change</span></span>

<span data-ttu-id="50d78-113">Объединение API текста ответа в единый новый интерфейс функций.</span><span class="sxs-lookup"><span data-stu-id="50d78-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="50d78-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="50d78-114">Recommended action</span></span>

<span data-ttu-id="50d78-115">Используйте `IHttpResponseBodyFeature` том, где ранее использовали `IHttpResponseFeature.Body`, `IHttpSendFileFeature` или `IHttpBufferingFeature`.</span><span class="sxs-lookup"><span data-stu-id="50d78-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="50d78-116">Категория</span><span class="sxs-lookup"><span data-stu-id="50d78-116">Category</span></span>

<span data-ttu-id="50d78-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="50d78-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="50d78-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="50d78-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
