---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235420"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a><span data-ttu-id="3d780-101">Ограничение отмены по умолчанию для текстового поля WPF равно 100</span><span class="sxs-lookup"><span data-stu-id="3d780-101">WPF TextBox defaults to undo limit of 100</span></span>

|   |   |
|---|---|
|<span data-ttu-id="3d780-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="3d780-102">Details</span></span>|<span data-ttu-id="3d780-103">В .NET Framework 4.5 ограничение отмены по умолчанию для текстового поля WPF равно 100 (в отличие от неограниченного в .NET Framework 4.0)</span><span class="sxs-lookup"><span data-stu-id="3d780-103">In .NET Framework 4.5, the default undo limit for a WPF textbox is 100 (as opposed to being unlimited in .NET Framework 4.0)</span></span>|
|<span data-ttu-id="3d780-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="3d780-104">Suggestion</span></span>|<span data-ttu-id="3d780-105">Если ограничение отмены, равное 100, слишком низкое, ограничение можно задать явным образом с помощью свойства <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span><span class="sxs-lookup"><span data-stu-id="3d780-105">If an undo limit of 100 is too low, the limit can be set explicitly with <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit></span></span>|
|<span data-ttu-id="3d780-106">Область</span><span class="sxs-lookup"><span data-stu-id="3d780-106">Scope</span></span>|<span data-ttu-id="3d780-107">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="3d780-107">Edge</span></span>|
|<span data-ttu-id="3d780-108">Версия</span><span class="sxs-lookup"><span data-stu-id="3d780-108">Version</span></span>|<span data-ttu-id="3d780-109">4.5</span><span class="sxs-lookup"><span data-stu-id="3d780-109">4.5</span></span>|
|<span data-ttu-id="3d780-110">Тип</span><span class="sxs-lookup"><span data-stu-id="3d780-110">Type</span></span>|<span data-ttu-id="3d780-111">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="3d780-111">Runtime</span></span>|
|<span data-ttu-id="3d780-112">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="3d780-112">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|
