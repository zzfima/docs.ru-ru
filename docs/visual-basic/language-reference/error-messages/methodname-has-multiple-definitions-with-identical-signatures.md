---
title: '&#39;&lt;имя_метода&gt; &#39; имеет несколько определений с одинаковыми сигнатурами'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 059d152cf9c3fae77ab53a4a9248b36d99614c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="fab2d-102">&#39;&lt;имя_метода&gt; &#39; имеет несколько определений с одинаковыми сигнатурами</span><span class="sxs-lookup"><span data-stu-id="fab2d-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="fab2d-103">Объект `Function` или `Sub` в объявлении процедуры используются процедуры одинаковые имя и список аргументов, как и в предыдущем объявлении.</span><span class="sxs-lookup"><span data-stu-id="fab2d-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="fab2d-104">Возможной причиной этого может быть попытка перегрузки исходной процедуры.</span><span class="sxs-lookup"><span data-stu-id="fab2d-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="fab2d-105">Перегруженные процедуры должны иметь разные списки аргументов.</span><span class="sxs-lookup"><span data-stu-id="fab2d-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="fab2d-106">**Идентификатор ошибки:** BC30269</span><span class="sxs-lookup"><span data-stu-id="fab2d-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fab2d-107">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="fab2d-107">To correct this error</span></span>  
  
-   <span data-ttu-id="fab2d-108">Измените имя процедуры или список аргументов или удалите повторяющееся объявление.</span><span class="sxs-lookup"><span data-stu-id="fab2d-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fab2d-109">См. также</span><span class="sxs-lookup"><span data-stu-id="fab2d-109">See Also</span></span>  
 [<span data-ttu-id="fab2d-110">Ссылки на объявленные элементы</span><span class="sxs-lookup"><span data-stu-id="fab2d-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="fab2d-111">Вопросы, связанные с перегрузкой процедур</span><span class="sxs-lookup"><span data-stu-id="fab2d-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
