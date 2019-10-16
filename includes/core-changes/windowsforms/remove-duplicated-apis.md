---
ms.openlocfilehash: 4d67da34cf692133df95480a7f0215943337a34e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003006"
---
### <a name="duplicated-apis-removed-from-windows-forms"></a><span data-ttu-id="dc8fa-101">Дублированные API удалены из Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc8fa-101">Duplicated APIs removed from Windows Forms</span></span>

<span data-ttu-id="dc8fa-102">В .NET Core 3.0 RC1 были удалены некоторые API, которые случайно дублируются в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName> начиная с версии .NET Core 3.0, предварительная версия 4.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-102">A number of APIs accidentally duplicated in the <xref:System.Windows.Forms?displayProperty=fullName> namespace starting in .NET Core 3.0 Preview 4 have been removed in .NET Core 3.0 RC1.</span></span> 

#### <a name="change-description"></a><span data-ttu-id="dc8fa-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="dc8fa-103">Change description</span></span>

<span data-ttu-id="dc8fa-104">В .NET Core 3.0, предварительная версия 4, случайно дублировались несколько типов в пространстве имен <xref:System.Windows.Forms?displayProperty=fullName>, которые уже существовали в пространстве имен <xref:System.ComponentModel.Design?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-104">.NET Core 3.0 Preview 4 inadvertently duplicated a number of types in the <xref:System.Windows.Forms?displayProperty=fullName> namespace that already existed in the <xref:System.ComponentModel.Design?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="dc8fa-105">Начиная с .NET Core 3.0 RC1 эти дублирующиеся типы больше не доступны.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-105">Starting with .NET Core 3.0 RC1, these duplicated types are no longer available.</span></span> <span data-ttu-id="dc8fa-106">В следующей таблице приводится список исходного типа и его повторяющегося типа:</span><span class="sxs-lookup"><span data-stu-id="dc8fa-106">The following table shows lists the original type and its duplicated type:</span></span>

|<span data-ttu-id="dc8fa-107">Исходный тип</span><span class="sxs-lookup"><span data-stu-id="dc8fa-107">Original type</span></span>|<span data-ttu-id="dc8fa-108">Повторяющийся тип</span><span class="sxs-lookup"><span data-stu-id="dc8fa-108">Duplicated type</span></span>|
|---|---|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventArgs?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventArgs`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedEventHandler?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedEventHandler`|
|<xref:System.ComponentModel.Design.DesignerActionListsChangedType?displayProperty=fullName>|`System.Windows.Forms.DesignerActionListsChangedType`|
|<xref:System.ComponentModel.Design.DesignerActionUIService?displayProperty=fullName>|`System.Windows.Forms.DesignerActionUIService`|
|<xref:System.ComponentModel.Design.DesignerCommandSet?displayProperty=fullName>|`System.Windows.Forms.DesignerCommandSet`|

#### <a name="version-introduced"></a><span data-ttu-id="dc8fa-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="dc8fa-109">Version introduced</span></span>

<span data-ttu-id="dc8fa-110">3.0 RC1 (релиз-кандидат 1)</span><span class="sxs-lookup"><span data-stu-id="dc8fa-110">3.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="dc8fa-111">Рекомендуемое действие</span><span class="sxs-lookup"><span data-stu-id="dc8fa-111">Recommended action</span></span>

<span data-ttu-id="dc8fa-112">Обновите код, чтобы он ссылался на исходный тип, как показано в столбце **Исходный тип**.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-112">Update the code to reference the original type, as shown in the **Original type** column of the table.</span></span>

#### <a name="category"></a><span data-ttu-id="dc8fa-113">Категория</span><span class="sxs-lookup"><span data-stu-id="dc8fa-113">Category</span></span>

<span data-ttu-id="dc8fa-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dc8fa-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="dc8fa-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="dc8fa-115">Affected APIs</span></span>

- <span data-ttu-id="dc8fa-116">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-116">Not detectable via API analysis.</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis.

-->
