---
title: Массив имеет фиксированный размер или временно заблокирован (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: c7b5372b6046e25aad87131ba141cb71c580e12c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64625944"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="48c2e-102">Массив имеет фиксированный размер или временно заблокирован (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48c2e-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="48c2e-103">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="48c2e-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="48c2e-104">С помощью `ReDim` изменение числа элементов массива фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="48c2e-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="48c2e-105">Изменение размерности динамического массива на уровне модуля, в котором один элемент был передан процедуре в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="48c2e-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="48c2e-106">Если передается элемент, массив заблокирован, чтобы предотвратить освобождение памяти для ссылочного параметра в процедуре.</span><span class="sxs-lookup"><span data-stu-id="48c2e-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="48c2e-107">Попытка присвоить значение `Variant` переменную, содержащую массив, но `Variant` в данный момент заблокирована.</span><span class="sxs-lookup"><span data-stu-id="48c2e-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="48c2e-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="48c2e-108">To correct this error</span></span>  
  
1. <span data-ttu-id="48c2e-109">Сделайте исходный массив динамическим, а не устранена, объявив ее с `ReDim` (при объявлении массива в процедуре), либо путем объявления его без указания числа элементов (если массив был объявлен на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="48c2e-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="48c2e-110">Определите, необходима ли передача элемента, так как он является видимым в пределах всех процедур в модуле.</span><span class="sxs-lookup"><span data-stu-id="48c2e-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="48c2e-111">Определите, что заблокирована `Variant` и разблокируйте ее.</span><span class="sxs-lookup"><span data-stu-id="48c2e-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c2e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="48c2e-112">See also</span></span>

- [<span data-ttu-id="48c2e-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="48c2e-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
