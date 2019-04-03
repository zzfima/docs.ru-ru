---
title: <type1>"<typename>«должен реализовывать»<membername>«для интерфейса»<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30154
- bc30154
helpviewer_keywords:
- BC30154
ms.assetid: 259afdfa-3608-4760-adcb-88ec0da5020d
ms.openlocfilehash: 485680a2984a29037b2836fcba13cf1aa1e2e699
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822756"
---
# <a name="type1typename-must-implement-membername-for-interface-interfacename"></a><span data-ttu-id="8a20c-102">\<тип1 > "\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >"</span><span class="sxs-lookup"><span data-stu-id="8a20c-102">\<type1>'\<typename>' must implement '\<membername>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="8a20c-103">"\<typename >" должен реализовывать "\<имя_члена >" для интерфейса "\<имя_интерфейса >".</span><span class="sxs-lookup"><span data-stu-id="8a20c-103">'\<typename>' must implement '\<membername>' for interface '\<interfacename>'.</span></span> <span data-ttu-id="8a20c-104">Реализация свойства должен иметь совпадающие «ReadOnly» или «WriteOnly» спецификаторы.</span><span class="sxs-lookup"><span data-stu-id="8a20c-104">Implementing property must have matching 'ReadOnly'/'WriteOnly' specifiers.</span></span>  
  
 <span data-ttu-id="8a20c-105">Класс или структура объявляет о реализации интерфейса, но не реализует процедуру, свойства или события, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="8a20c-105">A class or structure claims to implement an interface but does not implement a procedure, property, or event defined by the interface.</span></span> <span data-ttu-id="8a20c-106">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="8a20c-106">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="8a20c-107">**Идентификатор ошибки:** BC30154</span><span class="sxs-lookup"><span data-stu-id="8a20c-107">**Error ID:** BC30154</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8a20c-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8a20c-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="8a20c-109">Объявите член с тем же именем и подписью, как определено в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="8a20c-109">Declare a member with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="8a20c-110">Не забудьте включить по крайней мере `End Function`, `End Sub`, или `End Property` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a20c-110">Be sure to include at least the `End Function`, `End Sub`, or `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="8a20c-111">Добавить `Implements` предложение в конец `Function`, `Sub`, `Property`, или `Event` инструкции.</span><span class="sxs-lookup"><span data-stu-id="8a20c-111">Add an `Implements` clause to the end of the `Function`, `Sub`, `Property`, or `Event` statement.</span></span> <span data-ttu-id="8a20c-112">Пример:</span><span class="sxs-lookup"><span data-stu-id="8a20c-112">For example:</span></span>  
  
    ```  
    Public Event ItHappened() Implements IBaseInterface.ItHappened  
    ```  
  
3.  <span data-ttu-id="8a20c-113">При реализации свойства, убедитесь, что `ReadOnly` или `WriteOnly` используется таким же образом, как и в определении интерфейса.</span><span class="sxs-lookup"><span data-stu-id="8a20c-113">When implementing a property, make sure that `ReadOnly` or `WriteOnly` is used in the same way as in the interface definition.</span></span>  
  
4.  <span data-ttu-id="8a20c-114">При реализации свойства объявить `Get` и `Set` процедуры, соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="8a20c-114">When implementing a property, declare `Get` and `Set` procedures, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a20c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="8a20c-115">See also</span></span>

- [<span data-ttu-id="8a20c-116">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="8a20c-116">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="8a20c-117">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="8a20c-117">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
