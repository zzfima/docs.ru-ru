---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0e9acf4b3e71295655c15ae9b1c80852c9aca8df
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835145"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="9e1f8-102">Производные классы не могут вызывать события базового класса</span><span class="sxs-lookup"><span data-stu-id="9e1f8-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="9e1f8-103">Событие может вызываться только из области объявления, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="9e1f8-104">Таким образом класс не может вызвать событие из другого класса, хотя бы один из которого он является производным.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="9e1f8-105">**Идентификатор ошибки:** BC30029</span><span class="sxs-lookup"><span data-stu-id="9e1f8-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9e1f8-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9e1f8-106">To correct this error</span></span>  
  
-   <span data-ttu-id="9e1f8-107">Переместить `Event` инструкции или `RaiseEvent` инструкции, поэтому они находятся в том же классе.</span><span class="sxs-lookup"><span data-stu-id="9e1f8-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e1f8-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9e1f8-108">See also</span></span>

- [<span data-ttu-id="9e1f8-109">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="9e1f8-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="9e1f8-110">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="9e1f8-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
