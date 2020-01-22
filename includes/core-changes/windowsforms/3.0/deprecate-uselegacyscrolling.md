---
ms.openlocfilehash: 80fc75d0736e2ae17699073a025e79b52b340613
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937080"
---
### <a name="domainupdownuselegacyscrolling-compatibility-switch-not-supported"></a><span data-ttu-id="e772c-101">Параметр совместимости DomainUpDown.UseLegacyScrolling не поддерживается</span><span class="sxs-lookup"><span data-stu-id="e772c-101">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>

<span data-ttu-id="e772c-102">Параметр совместимости `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling`, появившийся в .NET Framework 4.7.1, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e772c-102">The `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e772c-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="e772c-103">Change description</span></span>

<span data-ttu-id="e772c-104">Начиная с версии .NET Framework 4.7.1, параметр совместимости `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` позволял разработчикам отказаться от независимых действий <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> и <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e772c-104">Starting with the .NET Framework 4.7.1, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` compatibility switch allowed developers to opt-out of independent <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> and <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> actions.</span></span> <span data-ttu-id="e772c-105">Параметр восстанавливал прежнее поведение, при котором действие <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> игнорируется, если присутствует текст контекста, и разработчику необходимо использовать действие <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> для элемента управления перед использованием действия <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e772c-105">The switch restored the legacy behavior, in which the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> is ignored if context text is present, and the developer is required to use <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType> action on the control before the <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType> action.</span></span> <span data-ttu-id="e772c-106">Дополнительные сведения см. в статье [Элемент \<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span><span class="sxs-lookup"><span data-stu-id="e772c-106">For more information, see [\<AppContextSwitchOverrides> element](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).</span></span>

<span data-ttu-id="e772c-107">В .NET Core параметр `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e772c-107">In .NET Core, the `Switch.System.Windows.Forms.DomainUpDown.UseLegacyScrolling` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e772c-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e772c-108">Version introduced</span></span>

<span data-ttu-id="e772c-109">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="e772c-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e772c-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="e772c-110">Recommended action</span></span>

<span data-ttu-id="e772c-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="e772c-111">Remove the switch.</span></span> <span data-ttu-id="e772c-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="e772c-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e772c-113">Категория</span><span class="sxs-lookup"><span data-stu-id="e772c-113">Category</span></span>

<span data-ttu-id="e772c-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e772c-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e772c-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e772c-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.DomainUpDown.DownButton?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.UpButton?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.DomainUpDown.DownButton`
- `M:System.Windows.Forms.DomainUpDown.UpButton`

-->
