---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
ms.openlocfilehash: 4a6f1f59f43cdb351d49fbcbfd18362db888586e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="ea2b2-102">Объект или класс не поддерживает набор событий</span><span class="sxs-lookup"><span data-stu-id="ea2b2-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="ea2b2-103">Предпринята попытка использования `WithEvents` переменной с компонентом, который не может служить источником событий для указанного набора событий.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="ea2b2-104">Например, требуется приемник событий объекта, создайте другой объект, `Implements` первый объект.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="ea2b2-105">Хотя может показаться, что может управлять событиями из реализованного объекта, это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="ea2b2-106">`Implements` реализует только интерфейс для методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="ea2b2-107">`WithEvents` не поддерживается для частного `UserControls`, так как информация о типе, необходимые для вызова `ObjectEvent` доступен не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea2b2-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ea2b2-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="ea2b2-109">Не удается получить события для компонента, который не является источником событий.</span><span class="sxs-lookup"><span data-stu-id="ea2b2-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea2b2-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ea2b2-110">See Also</span></span>  
 [<span data-ttu-id="ea2b2-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="ea2b2-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [<span data-ttu-id="ea2b2-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="ea2b2-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
