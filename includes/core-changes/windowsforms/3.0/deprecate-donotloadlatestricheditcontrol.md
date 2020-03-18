---
ms.openlocfilehash: 3f0e8fb4d0d727b40cff5de7cfdc7529bf32dac4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937082"
---
### <a name="donotloadlatestricheditcontrol-compatibility-switch-not-supported"></a><span data-ttu-id="d7c23-101">Параметр совместимости DoNotLoadLatestRichEditControl не поддерживается</span><span class="sxs-lookup"><span data-stu-id="d7c23-101">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>

<span data-ttu-id="d7c23-102">Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.7.1, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="d7c23-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.7.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="d7c23-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="d7c23-103">Change description</span></span>

<span data-ttu-id="d7c23-104">В .NET Framework 4.6.2 и предыдущих версиях элемент управления <xref:System.Windows.Forms.RichTextBox> создавал экземпляр элемента управления Win32 RichEdit версии 3.0, а для приложений, предназначенных для .NET Framework 4.7.1, элемент управления <xref:System.Windows.Forms.RichTextBox> создавал экземпляр элемента управления RichEdit версии 4.1 (в *msftedit.dll*).</span><span class="sxs-lookup"><span data-stu-id="d7c23-104">In the .NET Framework 4.6.2 and previous versions, the <xref:System.Windows.Forms.RichTextBox> control would instantiate the Win32 RichEdit control v3.0, and for applications that target .NET Framework 4.7.1, the  <xref:System.Windows.Forms.RichTextBox> control would instantiate RichEdit v4.1 (in *msftedit.dll*).</span></span> <span data-ttu-id="d7c23-105">Параметр совместимости `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` был введен для того, чтобы в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, можно было отказаться от использования нового элемента управления RichEdit версии 4.1 и использовать вместо него прежнюю версию 3.</span><span class="sxs-lookup"><span data-stu-id="d7c23-105">The `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` compatibility switch was introduced to allow applications that target .NET Framework 4.7.1 and later versions to opt-out of the new RichEdit v4.1 control and use the old RichEdit v3 control instead.</span></span>

<span data-ttu-id="d7c23-106">В .NET Core параметр `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d7c23-106">In .NET Core, the `Switch.System.Windows.Forms.DoNotLoadLatestRichEditControl` switch is not supported.</span></span> <span data-ttu-id="d7c23-107">Поддерживаются только новые версии элемента управления <xref:System.Windows.Forms.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="d7c23-107">Only new versions of the  <xref:System.Windows.Forms.RichTextBox> control are supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d7c23-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="d7c23-108">Version introduced</span></span>

<span data-ttu-id="d7c23-109">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="d7c23-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d7c23-110">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="d7c23-110">Recommended action</span></span>

<span data-ttu-id="d7c23-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="d7c23-111">Remove the switch.</span></span> <span data-ttu-id="d7c23-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="d7c23-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="d7c23-113">Категория</span><span class="sxs-lookup"><span data-stu-id="d7c23-113">Category</span></span>

<span data-ttu-id="d7c23-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d7c23-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d7c23-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d7c23-115">Affected APIs</span></span>

- <xref:System.Windows.Forms.RichTextBox?displayProperty=nameWithType>

<!-- 

### Affected APIs

-  `T:System.Windows.Forms.RichTextBox` 

-->
