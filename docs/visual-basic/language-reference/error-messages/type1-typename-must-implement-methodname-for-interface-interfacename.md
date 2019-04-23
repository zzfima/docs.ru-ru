---
title: <type1>"<typename>«должен реализовывать»<methodname>«для интерфейса»<interfacename>"
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 432f089bc77928308820d7456d930fba8dc513f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304913"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="ba504-102">\<тип1 > "\<typename >" должен реализовывать "\<имя_метода >" для интерфейса "\<имя_интерфейса >"</span><span class="sxs-lookup"><span data-stu-id="ba504-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="ba504-103">Класс или структура объявляет о реализации интерфейса, но не реализует процедуры, определенные в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="ba504-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="ba504-104">Каждый член интерфейса должен быть реализован.</span><span class="sxs-lookup"><span data-stu-id="ba504-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="ba504-105">**Идентификатор ошибки:** BC30149</span><span class="sxs-lookup"><span data-stu-id="ba504-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ba504-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="ba504-106">To correct this error</span></span>  
  
1. <span data-ttu-id="ba504-107">Объявите процедуру с тем же именем и подписью, как определено в интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="ba504-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="ba504-108">Не забудьте включить по крайней мере `End Function` или `End Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ba504-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="ba504-109">Добавить `Implements` предложение в конец `Function` или `Sub` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ba504-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="ba504-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="ba504-110">For example:</span></span>  
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ba504-111">См. также</span><span class="sxs-lookup"><span data-stu-id="ba504-111">See also</span></span>

- [<span data-ttu-id="ba504-112">Оператор Implements</span><span class="sxs-lookup"><span data-stu-id="ba504-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="ba504-113">Интерфейсы</span><span class="sxs-lookup"><span data-stu-id="ba504-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
