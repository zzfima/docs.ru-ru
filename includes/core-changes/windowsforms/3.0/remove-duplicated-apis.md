---
ms.openlocfilehash: e609b8006846cd202a6a7eeec2529cf1fbb09e7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937025"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="e0314-101">Дублированные API удалены из Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0314-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="e0314-102">В .NET Core 3.0 RC1 были удалены некоторые API, которые случайно дублируются в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName> начиная с версии .NET Core 3.0, предварительная версия 4.</span><span class="sxs-lookup"><span data-stu-id="e0314-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e0314-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="e0314-103">Change description</span></span>

<span data-ttu-id="e0314-104">В .NET Core 3.0, предварительная версия 4, случайно дублировались несколько типов в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName>, которые уже существовали в пространстве имен <xref:System.ComponentModel.Design?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="e0314-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="e0314-105">Начиная с .NET Core 3.0 RC1 эти дублирующиеся типы больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="e0314-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="e0314-106">В следующей таблице приводится список исходного типа и его повторяющегося типа:</span><span class="sxs-lookup"><span data-stu-id="e0314-106">The following table shows lists the original type and its duplicated type:</span></span>

> [!div class="mx-tdCol2BreakAll"]
> |<span data-ttu-id="e0314-107">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="e0314-107">Original type</span></span>|<span data-ttu-id="e0314-108">Повторяющийся тип</span><span class="sxs-lookup"><span data-stu-id="e0314-108">Duplicated type</span></span>|
> |---|---|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
> |<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
> |<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
> |<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="e0314-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="e0314-109">Version introduced</span></span>

<span data-ttu-id="e0314-110">3.0 RC1 (релиз-кандидат 1)</span><span class="sxs-lookup"><span data-stu-id="e0314-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e0314-111">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="e0314-111">Recommended action</span></span>

<span data-ttu-id="e0314-112">Обновите код, чтобы он ссылался на исходный тип, как показано в столбце **Исходный тип**.</span><span class="sxs-lookup"><span data-stu-id="e0314-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="e0314-113">Категория</span><span class="sxs-lookup"><span data-stu-id="e0314-113">Category</span></span>

<span data-ttu-id="e0314-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0314-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e0314-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="e0314-115">Affected APIs</span></span>

- <span data-ttu-id="e0314-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="e0314-116">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis.

-->
