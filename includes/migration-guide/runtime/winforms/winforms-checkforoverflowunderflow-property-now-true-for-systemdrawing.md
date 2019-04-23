---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804958"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="e927e-101">Свойство CheckForOverflowUnderflow WinForm теперь имеет значение true для System.Drawing</span><span class="sxs-lookup"><span data-stu-id="e927e-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e927e-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="e927e-102">Details</span></span>|<span data-ttu-id="e927e-103">Свойство CheckForOverflowUnderflow для сборки System.Drawing.dll имеет значение true.</span><span class="sxs-lookup"><span data-stu-id="e927e-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="e927e-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="e927e-104">Suggestion</span></span>|<span data-ttu-id="e927e-105">Раньше при переполнениях результат усекался без уведомления.</span><span class="sxs-lookup"><span data-stu-id="e927e-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="e927e-106">Теперь создается исключение <xref:System.OverflowException?displayProperty=name>,</span><span class="sxs-lookup"><span data-stu-id="e927e-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="e927e-107">Область</span><span class="sxs-lookup"><span data-stu-id="e927e-107">Scope</span></span>|<span data-ttu-id="e927e-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="e927e-108">Edge</span></span>|
|<span data-ttu-id="e927e-109">Версия</span><span class="sxs-lookup"><span data-stu-id="e927e-109">Version</span></span>|<span data-ttu-id="e927e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="e927e-110">4.5</span></span>|
|<span data-ttu-id="e927e-111">Тип</span><span class="sxs-lookup"><span data-stu-id="e927e-111">Type</span></span>|<span data-ttu-id="e927e-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="e927e-112">Runtime</span></span>|
