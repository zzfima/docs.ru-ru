---
ms.openlocfilehash: cb72e1b92172b8989ce99b47181c13561a7ccd76
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643895"
---
### <a name="switchsystemwindowsformsdontsupportreentrantfiltermessage-compatibility-switch-not-supported"></a><span data-ttu-id="d782d-101">Параметр совместимости Switch.System.Windows.Forms.DontSupportReentrantFilterMessage не поддерживается</span><span class="sxs-lookup"><span data-stu-id="d782d-101">Switch.System.Windows.Forms.DontSupportReentrantFilterMessage compatibility switch not supported</span></span>

<span data-ttu-id="d782d-102">Параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage`, появившийся в .NET Framework 4.6.1, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d782d-102">The `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d782d-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="d782d-103">Change description</span></span>

<span data-ttu-id="d782d-104">Начиная с .NET Framework 4.6.1, параметр совместимости `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` устраняет возможные исключения <xref:System.IndexOutOfRangeException> при вызове сообщения <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> с пользовательской реализацией <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d782d-104">Starting with the .NET Framework 4.6.1, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` compatibility switch addresses possible <xref:System.IndexOutOfRangeException> exceptions when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> message is called with a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="d782d-105">Дополнительные сведения см. в разделе [Устранение рисков. Пользовательские реализации IMessageFilter.PreFilterMessage](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span><span class="sxs-lookup"><span data-stu-id="d782d-105">For more information, see [Mitigation: Custom IMessageFilter.PreFilterMessage Implementations](~/docs/framework/migration-guide/mitigation-custom-imessagefilter-prefiltermessage-implementations.md).</span></span>

<span data-ttu-id="d782d-106">В .NET Core параметр `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d782d-106">In .NET Core, the `Switch.System.Windows.Forms.DontSupportReentrantFilterMessage` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d782d-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d782d-107">Version introduced</span></span>

<span data-ttu-id="d782d-108">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="d782d-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d782d-109">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="d782d-109">Recommended action</span></span>

<span data-ttu-id="d782d-110">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="d782d-110">Remove the switch.</span></span> <span data-ttu-id="d782d-111">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="d782d-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d782d-112">Категория</span><span class="sxs-lookup"><span data-stu-id="d782d-112">Category</span></span>

<span data-ttu-id="d782d-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d782d-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d782d-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d782d-114">Affected APIs</span></span>

- <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.Application.FilterMessage(System.Windows.Forms.Message)`

-->
