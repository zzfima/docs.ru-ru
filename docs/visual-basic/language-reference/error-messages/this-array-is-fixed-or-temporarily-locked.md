---
title: Массив имеет фиксированный размер или временно заблокирован (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: f0b80e2be007ff44569365f37a2331f1ecd7a216
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839409"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="bc5c4-102">Массив имеет фиксированный размер или временно заблокирован (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc5c4-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="bc5c4-103">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="bc5c4-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="bc5c4-104">С помощью `ReDim` изменение числа элементов массива фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="bc5c4-105">Изменение размерности динамического массива на уровне модуля, в котором один элемент был передан процедуре в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="bc5c4-106">Если передается элемент, массив заблокирован, чтобы предотвратить освобождение памяти для ссылочного параметра в процедуре.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="bc5c4-107">Попытка присвоить значение `Variant` переменную, содержащую массив, но `Variant` в данный момент заблокирована.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bc5c4-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="bc5c4-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="bc5c4-109">Сделайте исходный массив динамическим, а не устранена, объявив ее с `ReDim` (при объявлении массива в процедуре), либо путем объявления его без указания числа элементов (если массив был объявлен на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="bc5c4-110">Определите, необходима ли передача элемента, так как он является видимым в пределах всех процедур в модуле.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="bc5c4-111">Определите, что заблокирована `Variant` и разблокируйте ее.</span><span class="sxs-lookup"><span data-stu-id="bc5c4-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5c4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="bc5c4-112">See also</span></span>

- [<span data-ttu-id="bc5c4-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="bc5c4-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
