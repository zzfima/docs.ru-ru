---
title: Тип <type1><typename> должен реализовать <methodname> для интерфейса <interfacename>
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c5dd7c6889a3fb5344142ee9914f98e8922d748b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264442"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="e8b5e-102">\<тип1 > "\<typename >" должен реализовывать "\<имя_метода >" для интерфейса "\<имя_интерфейса >"</span><span class="sxs-lookup"><span data-stu-id="e8b5e-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="e8b5e-103">Класс или структура объявляет о реализации интерфейса, но не реализует процедуры, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="e8b5e-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="e8b5e-104">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="e8b5e-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="e8b5e-105">**Идентификатор ошибки:** BC30149</span><span class="sxs-lookup"><span data-stu-id="e8b5e-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e8b5e-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="e8b5e-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="e8b5e-107">Объявите процедуру с тем же именем и подписью, как определено в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="e8b5e-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="e8b5e-108">Не забудьте включить по крайней мере `End Function` или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e8b5e-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="e8b5e-109">Добавить `Implements` предложение в конец `Function` или `Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="e8b5e-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="e8b5e-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="e8b5e-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e8b5e-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e8b5e-111">See also</span></span>
- [<span data-ttu-id="e8b5e-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="e8b5e-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="e8b5e-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="e8b5e-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
