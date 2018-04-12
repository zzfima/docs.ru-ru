---
title: Объект или класс не поддерживает набор событий
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID459
ms.assetid: 785df3f3-2aae-4a25-af36-1f9879d4e5fd
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: be4b9140222ef969bfb836fd74f45b8f662360b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="object-or-class-does-not-support-the-set-of-events"></a><span data-ttu-id="98f79-102">Объект или класс не поддерживает набор событий</span><span class="sxs-lookup"><span data-stu-id="98f79-102">Object or class does not support the set of events</span></span>
<span data-ttu-id="98f79-103">Предпринята попытка использования `WithEvents` переменной с компонентом, который не может служить источником событий для указанного набора событий.</span><span class="sxs-lookup"><span data-stu-id="98f79-103">You tried to use a `WithEvents` variable with a component that cannot work as an event source for the specified set of events.</span></span> <span data-ttu-id="98f79-104">Например, требуется приемник событий объекта, создайте другой объект, `Implements` первый объект.</span><span class="sxs-lookup"><span data-stu-id="98f79-104">For example, you wanted to sink the events of an object, then create another object that `Implements` the first object.</span></span> <span data-ttu-id="98f79-105">Хотя может показаться, что может управлять событиями из реализованного объекта, это не всегда так.</span><span class="sxs-lookup"><span data-stu-id="98f79-105">Although you might think you could sink the events from the implemented object, this is not always the case.</span></span> <span data-ttu-id="98f79-106">`Implements`реализует только интерфейс для методов и свойств.</span><span class="sxs-lookup"><span data-stu-id="98f79-106">`Implements` only implements an interface for methods and properties.</span></span> <span data-ttu-id="98f79-107">`WithEvents`не поддерживается для частного `UserControls`, так как информация о типе, необходимые для вызова `ObjectEvent` доступен не во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="98f79-107">`WithEvents` is not supported for private `UserControls`, because the type info needed to raise the `ObjectEvent` is not available at run time.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="98f79-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="98f79-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="98f79-109">Не удается получить события для компонента, который не является источником событий.</span><span class="sxs-lookup"><span data-stu-id="98f79-109">You cannot sink events for a component that does not source events.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f79-110">См. также</span><span class="sxs-lookup"><span data-stu-id="98f79-110">See Also</span></span>  
 [<span data-ttu-id="98f79-111">WithEvents</span><span class="sxs-lookup"><span data-stu-id="98f79-111">WithEvents</span></span>](../../../visual-basic/language-reference/modifiers/withevents.md)  
 [<span data-ttu-id="98f79-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="98f79-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
