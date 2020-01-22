---
ms.openlocfilehash: 7e76c32ddeb50eaf1ee93d7cf3cac7469187cc41
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937001"
---
### <a name="allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported"></a><span data-ttu-id="88711-101">Параметр совместимости AllowUpdateChildControlIndexForTabControls не поддерживается</span><span class="sxs-lookup"><span data-stu-id="88711-101">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>

<span data-ttu-id="88711-102">Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` поддерживается в Windows Forms в .NET Framework 4.6 и более поздних версиях, но не поддерживается в Windows Forms, начиная с версии .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="88711-102">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch is supported in Windows Forms on .NET Framework 4.6 and later versions but is not supported in Windows Forms starting with .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="88711-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="88711-103">Change description</span></span>

<span data-ttu-id="88711-104">В .NET Framework 4.6 и более поздних версиях при выборе вкладки ее коллекция элементов управления переупорядочивается.</span><span class="sxs-lookup"><span data-stu-id="88711-104">In .NET Framework 4.6 and later versions, selecting a tab reorders its control collection.</span></span> <span data-ttu-id="88711-105">Параметр совместимости `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` позволяет приложению отменить переупорядочивание, если оно не требуется.</span><span class="sxs-lookup"><span data-stu-id="88711-105">The `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` compatibility switch allows an application to skip this reordering when this behavior is undesirable.</span></span>

<span data-ttu-id="88711-106">В .NET Core параметр `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="88711-106">In .NET Core, the `Switch.System.Windows.Forms.AllowUpdateChildControlIndexForTabControls` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="88711-107">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="88711-107">Version introduced</span></span>

<span data-ttu-id="88711-108">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="88711-108">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="88711-109">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="88711-109">Recommended action</span></span>

<span data-ttu-id="88711-110">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="88711-110">Remove the switch.</span></span> <span data-ttu-id="88711-111">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="88711-111">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="88711-112">Категория</span><span class="sxs-lookup"><span data-stu-id="88711-112">Category</span></span>

<span data-ttu-id="88711-113">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="88711-113">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="88711-114">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="88711-114">Affected APIs</span></span>

- <span data-ttu-id="88711-115">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="88711-115">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
