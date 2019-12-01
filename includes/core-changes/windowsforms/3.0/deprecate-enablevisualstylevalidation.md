---
ms.openlocfilehash: 84b6bfc32f5a73597b227098e5aee1e3450cf85b
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643901"
---
### <a name="switchsystemwindowsformsenablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="36014-101">Параметр совместимости Switch.System.Windows.Forms.EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="36014-101">Switch.System.Windows.Forms.EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="36014-102">Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="36014-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="36014-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="36014-103">Change description</span></span>

<span data-ttu-id="36014-104">В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.</span><span class="sxs-lookup"><span data-stu-id="36014-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="36014-105">В .NET Core параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="36014-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="36014-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="36014-106">Version introduced</span></span>

<span data-ttu-id="36014-107">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="36014-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="36014-108">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="36014-108">Recommended action</span></span>

<span data-ttu-id="36014-109">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="36014-109">Remove the switch.</span></span> <span data-ttu-id="36014-110">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="36014-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="36014-111">Категория</span><span class="sxs-lookup"><span data-stu-id="36014-111">Category</span></span>

<span data-ttu-id="36014-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36014-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="36014-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="36014-113">Affected APIs</span></span>

- <span data-ttu-id="36014-114">Нет</span><span class="sxs-lookup"><span data-stu-id="36014-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
