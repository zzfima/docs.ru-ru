---
ms.openlocfilehash: 75baa4f23eae838defafd3ce9b3907a187982a18
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937017"
---
### <a name="enablevisualstylevalidation-compatibility-switch-not-supported"></a><span data-ttu-id="e0c1d-101">Параметр совместимости EnableVisualStyleValidation не поддерживается</span><span class="sxs-lookup"><span data-stu-id="e0c1d-101">EnableVisualStyleValidation compatibility switch not supported</span></span>

<span data-ttu-id="e0c1d-102">Параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="e0c1d-102">The `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e0c1d-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="e0c1d-103">Change description</span></span>

<span data-ttu-id="e0c1d-104">В .NET Framework параметр совместимости `Switch.System.Windows.Forms.EnableVisualStyleValidation` позволял приложению отказаться от проверки визуальных стилей, предоставленных в числовой форме.</span><span class="sxs-lookup"><span data-stu-id="e0c1d-104">In .NET Framework, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` compatibility switch allowed an application to opt out of validation of visual styles supplied in a numeric form.</span></span>

<span data-ttu-id="e0c1d-105">В .NET Core параметр `Switch.System.Windows.Forms.EnableVisualStyleValidation` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e0c1d-105">In .NET Core, the `Switch.System.Windows.Forms.EnableVisualStyleValidation` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e0c1d-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e0c1d-106">Version introduced</span></span>

<span data-ttu-id="e0c1d-107">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="e0c1d-107">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0c1d-108">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="e0c1d-108">Recommended action</span></span>

<span data-ttu-id="e0c1d-109">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="e0c1d-109">Remove the switch.</span></span> <span data-ttu-id="e0c1d-110">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="e0c1d-110">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="e0c1d-111">Категория</span><span class="sxs-lookup"><span data-stu-id="e0c1d-111">Category</span></span>

<span data-ttu-id="e0c1d-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0c1d-112">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0c1d-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e0c1d-113">Affected APIs</span></span>

- <span data-ttu-id="e0c1d-114">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e0c1d-114">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
