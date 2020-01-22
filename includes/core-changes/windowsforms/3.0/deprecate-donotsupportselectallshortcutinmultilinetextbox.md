---
ms.openlocfilehash: 9631e64bb403a3fe7b1b91e8ac592b57ce8068d9
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937029"
---
### <a name="donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="5b707-101">Параметр совместимости DoNotSupportSelectAllShortcutInMultilineTextBox не поддерживается</span><span class="sxs-lookup"><span data-stu-id="5b707-101">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="5b707-102">Параметр совместимости `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`, появившийся в .NET Framework 4.6.1, не поддерживается в Windows Forms в .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="5b707-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="5b707-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="5b707-103">Change description</span></span>

<span data-ttu-id="5b707-104">Начиная с .NET Framework 4.6.1, при нажатии клавиш <kbd>CTRL</kbd> + <kbd>A</kbd> в элементе управления <xref:System.Windows.Forms.TextBox> выделяется весь текст.</span><span class="sxs-lookup"><span data-stu-id="5b707-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="5b707-105">В .NET Framework 4.6 и более ранних версиях при нажатии клавиш <kbd>CTRL</kbd> + <kbd>A</kbd> выделение всего текста не происходило, если свойства [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) и <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> имели значение `true`.</span><span class="sxs-lookup"><span data-stu-id="5b707-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="5b707-106">Параметр совместимости `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` появился в .NET Framework 4.6.1 для восстановления прежнего поведения.</span><span class="sxs-lookup"><span data-stu-id="5b707-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="5b707-107">Дополнительные сведения см. в разделе <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5b707-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="5b707-108">В .NET Core параметр `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5b707-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="5b707-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="5b707-109">Version introduced</span></span>

<span data-ttu-id="5b707-110">3.0, предварительная версия 9</span><span class="sxs-lookup"><span data-stu-id="5b707-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="5b707-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="5b707-111">Recommended action</span></span>

<span data-ttu-id="5b707-112">Удалите параметр.</span><span class="sxs-lookup"><span data-stu-id="5b707-112">Remove the switch.</span></span> <span data-ttu-id="5b707-113">Он не поддерживается, и альтернативного варианта нет.</span><span class="sxs-lookup"><span data-stu-id="5b707-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="5b707-114">Категория</span><span class="sxs-lookup"><span data-stu-id="5b707-114">Category</span></span>

<span data-ttu-id="5b707-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b707-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="5b707-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="5b707-116">Affected APIs</span></span>

- <span data-ttu-id="5b707-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5b707-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->
