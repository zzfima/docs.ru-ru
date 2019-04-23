---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: ad9176b5332a75f03968e742501c3fce541055de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342886"
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="c9bb7-102">Объект или класс не поддерживает набор событий</span><span class="sxs-lookup"><span data-stu-id="c9bb7-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="c9bb7-103">Предпринята попытка использования `WithEvents` переменной с компонентом, который не может служить источником событий для указанного набора событий.</span><span class="sxs-lookup"><span data-stu-id="c9bb7-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="c9bb7-104">Например, вы хотели приемник событий объекта, а затем создать другой объект, который `Implements` первый объект.</span><span class="sxs-lookup"><span data-stu-id="c9bb7-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="c9bb7-105">Несмотря на то, что может показаться, что удалось приемник событий из реализованного объекта, это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="c9bb7-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="c9bb7-106">`Implements` реализует только интерфейс для методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="c9bb7-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="c9bb7-107">`WithEvents` не поддерживается для частных `UserControls`, так как сведения о типе требуется для вызова `ObjectEvent` недоступен во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c9bb7-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9bb7-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="c9bb7-108">To correct this error</span></span>  
  
1. <span data-ttu-id="c9bb7-109">Не удается получить события для компонента, который не является источником событий.</span><span class="sxs-lookup"><span data-stu-id="c9bb7-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bb7-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c9bb7-110">See also</span></span>

- [<span data-ttu-id="c9bb7-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="c9bb7-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)
- [<span data-ttu-id="c9bb7-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="c9bb7-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
