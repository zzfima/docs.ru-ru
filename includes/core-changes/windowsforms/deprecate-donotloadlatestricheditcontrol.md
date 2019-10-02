---
ms.openlocfilehash: 265fc5bea97bf85bcb9cc8111f915e14297d9957
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2019
ms.locfileid: "71181813"
---
### <a name="switchsystemwindowsformsdonotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="9f1fe-101">Параметр совместимости Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="9f1fe-101">Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="9f1fe-102">Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.7.1, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="9f1fe-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9f1fe-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="9f1fe-103">Change description</span></span>

<span data-ttu-id="9f1fe-104">В .NET Framework 4.6.2 и предыдущих версиях элемент управления <xref:System.Windows.Forms.RichTextBox> создавал экземпляр элемента управления Win32 RichEdit версии 3.0, а для приложений, предназначенных для .NET Framework 4.7.1, элемент управления <xref:System.Windows.Forms.RichTextBox> создавал экземпляр элемента управления RichEdit версии 4.1 (в *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="9f1fe-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="9f1fe-105">Параметр совместимости `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` был введен для того, чтобы в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, можно было отказаться от использования нового элемента управления RichEdit версии 4.1 и использовать вместо него прежнюю версию 3.</span><span class="sxs-lookup"><span data-stu-id="9f1fe-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="9f1fe-106">В .NET Core параметр `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="9f1fe-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="9f1fe-107">Поддерживаются только новые версии элемента управления <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="9f1fe-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9f1fe-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="9f1fe-108">Version introduced</span></span>

<span data-ttu-id="9f1fe-109">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="9f1fe-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9f1fe-110">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="9f1fe-110">Recommended action</span></span>

<span data-ttu-id="9f1fe-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="9f1fe-111">Remove the switch.</span></span> <span data-ttu-id="9f1fe-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="9f1fe-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="9f1fe-113">Категория</span><span class="sxs-lookup"><span data-stu-id="9f1fe-113">Category</span></span>

<span data-ttu-id="9f1fe-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9f1fe-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9f1fe-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="9f1fe-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
