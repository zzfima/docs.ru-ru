---
title: Массив имеет фиксированный размер или временно заблокирован (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c74d9524ff64101ba6002e133b93c9b80e8f50a9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337972"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="4ca37-102">Массив имеет фиксированный размер или временно заблокирован (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ca37-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="4ca37-103">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="4ca37-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="4ca37-104">С помощью `ReDim` изменение числа элементов массива фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="4ca37-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="4ca37-105">Изменение размерности динамического массива на уровне модуля, в котором один элемент был передан процедуре в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="4ca37-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="4ca37-106">Если передается элемент, массив заблокирован, чтобы предотвратить освобождение памяти для ссылочного параметра в процедуре.</span><span class="sxs-lookup"><span data-stu-id="4ca37-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="4ca37-107">Попытка присвоить значение `Variant` переменную, содержащую массив, но `Variant` в данный момент заблокирована.</span><span class="sxs-lookup"><span data-stu-id="4ca37-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4ca37-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4ca37-108">To correct this error</span></span>  
  
1. <span data-ttu-id="4ca37-109">Сделайте исходный массив динамическим, а не устранена, объявив ее с `ReDim` (при объявлении массива в процедуре), либо путем объявления его без указания числа элементов (если массив был объявлен на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="4ca37-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="4ca37-110">Определите, необходима ли передача элемента, так как он является видимым в пределах всех процедур в модуле.</span><span class="sxs-lookup"><span data-stu-id="4ca37-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="4ca37-111">Определите, что заблокирована `Variant` и разблокируйте ее.</span><span class="sxs-lookup"><span data-stu-id="4ca37-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca37-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca37-112">See also</span></span>

- [<span data-ttu-id="4ca37-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="4ca37-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
