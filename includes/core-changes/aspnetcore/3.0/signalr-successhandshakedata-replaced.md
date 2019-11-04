---
ms.openlocfilehash: e9278320ee3fdf9e6b89698d187f047c309ea791
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198549"
---
### <a name="signalr-handshakeprotocolsuccesshandshakedata-replaced"></a><span data-ttu-id="998ed-101">SignalR. Замена HandshakeProtocol.SuccessHandshakeData</span><span class="sxs-lookup"><span data-stu-id="998ed-101">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>

<span data-ttu-id="998ed-102">Поле [HandshakeProtocol.SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) было удалено и заменено вспомогательным методом, который создает ответ об успешном подтверждении с учетом определенного `IHubProtocol`.</span><span class="sxs-lookup"><span data-stu-id="998ed-102">The [HandshakeProtocol.SuccessHandshakeData](https://github.com/aspnet/AspNetCore/blob/c5b2bc0df2a0027832bf7d01dfb19ca39cd08ae6/src/SignalR/common/SignalR.Common/src/Protocol/HandshakeProtocol.cs#L27) field was removed and replaced with a helper method that generates a successful handshake response given a specific `IHubProtocol`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="998ed-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="998ed-103">Version introduced</span></span>

<span data-ttu-id="998ed-104">3.0</span><span class="sxs-lookup"><span data-stu-id="998ed-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="998ed-105">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="998ed-105">Old behavior</span></span>

<span data-ttu-id="998ed-106">`HandshakeProtocol.SuccessHandshakeData` являлось полем `public static ReadOnlyMemory<byte>`.</span><span class="sxs-lookup"><span data-stu-id="998ed-106">`HandshakeProtocol.SuccessHandshakeData` was a `public static ReadOnlyMemory<byte>` field.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="998ed-107">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="998ed-107">New behavior</span></span>

<span data-ttu-id="998ed-108">`HandshakeProtocol.SuccessHandshakeData` заменено методом `static` `GetSuccessfulHandshake(IHubProtocol protocol)`, который возвращает `ReadOnlyMemory<byte>` на основе указанного протокола.</span><span class="sxs-lookup"><span data-stu-id="998ed-108">`HandshakeProtocol.SuccessHandshakeData` has been replaced by a `static` `GetSuccessfulHandshake(IHubProtocol protocol)` method that returns a `ReadOnlyMemory<byte>` based on the specified protocol.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="998ed-109">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="998ed-109">Reason for change</span></span>

<span data-ttu-id="998ed-110">Дополнительные поля были добавлены в _ответ_ подтверждения, которые не являются константами и отличаются в зависимости от выбранного протокола.</span><span class="sxs-lookup"><span data-stu-id="998ed-110">Additional fields were added to the handshake _response_ that are non-constant and change depending on the selected protocol.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="998ed-111">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="998ed-111">Recommended action</span></span>

<span data-ttu-id="998ed-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="998ed-112">None.</span></span> <span data-ttu-id="998ed-113">Этот тип не предназначен для использования из пользовательского кода.</span><span class="sxs-lookup"><span data-stu-id="998ed-113">This type isn't designed for use from user code.</span></span> <span data-ttu-id="998ed-114">Это `public`, поэтому он может быть общим для сервера SignalR и клиента.</span><span class="sxs-lookup"><span data-stu-id="998ed-114">It's `public`, so it can be shared between the SignalR server and client.</span></span> <span data-ttu-id="998ed-115">Он также может использоваться клиентами SignalR пользователя, написанными на .NET.</span><span class="sxs-lookup"><span data-stu-id="998ed-115">It may also be used by customer SignalR clients written in .NET.</span></span> <span data-ttu-id="998ed-116">Это изменение не влияет на **пользователей** SignalR.</span><span class="sxs-lookup"><span data-stu-id="998ed-116">**Users** of SignalR shouldn't be affected by this change.</span></span>

#### <a name="category"></a><span data-ttu-id="998ed-117">Категория</span><span class="sxs-lookup"><span data-stu-id="998ed-117">Category</span></span>

<span data-ttu-id="998ed-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="998ed-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="998ed-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="998ed-119">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData?displayProperty=namewithType>

<!--

#### Affected APIs

`F:Microsoft.AspNetCore.SignalR.Protocol.HandshakeProtocol.SuccessHandshakeData`

-->
