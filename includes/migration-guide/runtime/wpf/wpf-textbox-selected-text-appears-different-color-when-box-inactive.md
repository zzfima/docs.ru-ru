---
ms.openlocfilehash: 74ce1bbc9a887aee3a33eaf05084e8c2000967c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804933"
---
### <a name="wpf-textbox-selected-text-appears-a-different-color-when-the-text-box-is-inactive"></a><span data-ttu-id="72559-101">Выделенный текст в элементе управления TextBox WPF будет отображаться другим цветом, если текстовое поле неактивно</span><span class="sxs-lookup"><span data-stu-id="72559-101">WPF TextBox selected text appears a different color when the text box is inactive</span></span>

|   |   |
|---|---|
|<span data-ttu-id="72559-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="72559-102">Details</span></span>|<span data-ttu-id="72559-103">В .NET Framework 4.5, если элемент управления текстовым полем WPF неактивен (в нем отсутствует фокус), выбранный текст внутри поля будет отображаться цветом, отличным от того, когда элемент управления является активным.</span><span class="sxs-lookup"><span data-stu-id="72559-103">In .NET Framework 4.5, when a WPF text box control is inactive (it doesn't have focus), the selected text inside the box will appear a different color than when the control is active.</span></span>|
|<span data-ttu-id="72559-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="72559-104">Suggestion</span></span>|<span data-ttu-id="72559-105">Чтобы восстановить прежнее поведение (.NET Framework 4.0), задайте для свойства <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> значение <code>false</code>.</span><span class="sxs-lookup"><span data-stu-id="72559-105">The previous (.NET Framework 4.0) behavior may be restored by setting the <xref:System.Windows.FrameworkCompatibilityPreferences.AreInactiveSelectionHighlightBrushKeysSupported> property to <code>false</code>.</span></span>|
|<span data-ttu-id="72559-106">Область</span><span class="sxs-lookup"><span data-stu-id="72559-106">Scope</span></span>|<span data-ttu-id="72559-107">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="72559-107">Edge</span></span>|
|<span data-ttu-id="72559-108">Версия</span><span class="sxs-lookup"><span data-stu-id="72559-108">Version</span></span>|<span data-ttu-id="72559-109">4.5</span><span class="sxs-lookup"><span data-stu-id="72559-109">4.5</span></span>|
|<span data-ttu-id="72559-110">Тип</span><span class="sxs-lookup"><span data-stu-id="72559-110">Type</span></span>|<span data-ttu-id="72559-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="72559-111">Runtime</span></span>|
|<span data-ttu-id="72559-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="72559-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
