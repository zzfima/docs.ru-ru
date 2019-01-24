---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 3cb61a40e4522695b876d85f67dac1a109d3c3e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595868"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a><span data-ttu-id="cebf4-102">Производные классы не могут вызывать события базового класса</span><span class="sxs-lookup"><span data-stu-id="cebf4-102">Derived classes cannot raise base class events</span></span>
<span data-ttu-id="cebf4-103">Событие может вызываться только из области объявления, в котором она объявлена.</span><span class="sxs-lookup"><span data-stu-id="cebf4-103">An event can be raised only from the declaration space in which it is declared.</span></span> <span data-ttu-id="cebf4-104">Таким образом класс не может вызвать событие из другого класса, хотя бы один из которого он является производным.</span><span class="sxs-lookup"><span data-stu-id="cebf4-104">Therefore, a class cannot raise events from any other class, even one from which it is derived.</span></span>  
  
 <span data-ttu-id="cebf4-105">**Идентификатор ошибки:** BC30029</span><span class="sxs-lookup"><span data-stu-id="cebf4-105">**Error ID:** BC30029</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cebf4-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cebf4-106">To correct this error</span></span>  
  
-   <span data-ttu-id="cebf4-107">Переместить `Event` инструкции или `RaiseEvent` инструкции, поэтому они находятся в том же классе.</span><span class="sxs-lookup"><span data-stu-id="cebf4-107">Move the `Event` statement or the `RaiseEvent` statement so they are in the same class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cebf4-108">См. также</span><span class="sxs-lookup"><span data-stu-id="cebf4-108">See also</span></span>
- [<span data-ttu-id="cebf4-109">Оператор Event</span><span class="sxs-lookup"><span data-stu-id="cebf4-109">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)
- [<span data-ttu-id="cebf4-110">Оператор RaiseEvent</span><span class="sxs-lookup"><span data-stu-id="cebf4-110">RaiseEvent Statement</span></span>](../../../visual-basic/language-reference/statements/raiseevent-statement.md)
