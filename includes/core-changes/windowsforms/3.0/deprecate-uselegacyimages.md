---
ms.openlocfilehash: 07527c247e6ccd53d2a77793946ffc796c3e1cbb
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643919"
---
### <a name="switchsystemwindowsformsuselegacyimages-compatibility-switch-not-supported"></a><span data-ttu-id="babab-101">Параметр совместимости Switch.System.Windows.Forms.UseLegacyImages не поддерживается</span><span class="sxs-lookup"><span data-stu-id="babab-101">Switch.System.Windows.Forms.UseLegacyImages compatibility switch not supported</span></span>

<span data-ttu-id="babab-102">Параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages`, появившийся в .NET Framework 4.8, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="babab-102">The `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch, which was introduced in .NET Framework 4.8, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="babab-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="babab-103">Change description</span></span>

<span data-ttu-id="babab-104">Начиная с .NET Framework 4.8, параметр совместимости `Switch.System.Windows.Forms.UseLegacyImages` устраняет возможные проблемы с масштабированием изображений в сценариях ClickOnce в средах с высоким DPI.</span><span class="sxs-lookup"><span data-stu-id="babab-104">Starting with the .NET Framework 4.8, the `Switch.System.Windows.Forms.UseLegacyImages` compatibility switch addressed possible image scaling issues in ClickOnce scenarios in high DPI environments.</span></span> <span data-ttu-id="babab-105">Если задано значение `true`, параметр позволяет пользователю восстановить прежний способ масштабирования изображений при высоком уровне DPI, когда масштаб составляет более 100 %.</span><span class="sxs-lookup"><span data-stu-id="babab-105">When set to `true`, the switch allows the user to restore legacy image scaling on high DPI displays whose scale is set to greater than 100%.</span></span> <span data-ttu-id="babab-106">Дополнительные сведения см. в [заметках о выпуске .NET Framework 4.8](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) в GitHub.</span><span class="sxs-lookup"><span data-stu-id="babab-106">For more information, see [.NET Framework 4.8 Release Notes](https://github.com/microsoft/dotnet/blob/master/releases/net48/dotnet48-changes.md#clickonce) on GitHub.</span></span>

<span data-ttu-id="babab-107">В .NET Core параметр `Switch.System.Windows.Forms.UseLegacyImages` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="babab-107">In .NET Core, the `Switch.System.Windows.Forms.UseLegacyImages` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="babab-108">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="babab-108">Version introduced</span></span>

<span data-ttu-id="babab-109">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="babab-109">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="babab-110">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="babab-110">Recommended action</span></span>

<span data-ttu-id="babab-111">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="babab-111">Remove the switch.</span></span> <span data-ttu-id="babab-112">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="babab-112">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="babab-113">Категория</span><span class="sxs-lookup"><span data-stu-id="babab-113">Category</span></span>

<span data-ttu-id="babab-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="babab-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="babab-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="babab-115">Affected APIs</span></span>

- <span data-ttu-id="babab-116">Нет</span><span class="sxs-lookup"><span data-stu-id="babab-116">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
