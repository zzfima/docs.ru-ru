---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937017"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="544ac-101">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="544ac-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="544ac-102">Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="544ac-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="544ac-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="544ac-103">Change description</span></span>

<span data-ttu-id="544ac-104">В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.</span><span class="sxs-lookup"><span data-stu-id="544ac-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="544ac-105">В .NET Core параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="544ac-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="544ac-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="544ac-106">Version introduced</span></span>

<span data-ttu-id="544ac-107">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="544ac-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="544ac-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="544ac-108">Recommended action</span></span>

<span data-ttu-id="544ac-109">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="544ac-109">Remove the switch.</span></span> <span data-ttu-id="544ac-110">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="544ac-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="544ac-111">Категория</span><span class="sxs-lookup"><span data-stu-id="544ac-111">Category</span></span>

<span data-ttu-id="544ac-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="544ac-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="544ac-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="544ac-113">Affected APIs</span></span>

- <span data-ttu-id="544ac-114">None</span><span class="sxs-lookup"><span data-stu-id="544ac-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
