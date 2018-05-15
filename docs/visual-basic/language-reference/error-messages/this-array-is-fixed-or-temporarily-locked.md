---
title: Массив имеет фиксированный размер или временно заблокирован (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="80c00-102">Массив имеет фиксированный размер или временно заблокирован (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80c00-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="80c00-103">Эта ошибка имеет следующие возможные причины:</span><span class="sxs-lookup"><span data-stu-id="80c00-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="80c00-104">С помощью `ReDim` изменение числа элементов массива фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="80c00-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="80c00-105">Изменение размерности динамического массива на уровне модуля, в котором один элемент был передан процедуре в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="80c00-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="80c00-106">Если передается элемент, массив заблокирован, чтобы предотвратить освобождение памяти для параметра ссылки в пределах процедуры.</span><span class="sxs-lookup"><span data-stu-id="80c00-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="80c00-107">Попытка присвоить значение `Variant` переменная, содержащая массив, но `Variant` заблокирован.</span><span class="sxs-lookup"><span data-stu-id="80c00-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80c00-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="80c00-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="80c00-109">Сделайте исходный массив динамическим, а не фиксированным, объявив его с `ReDim` (если массив объявлен внутри процедуры), либо путем объявления его без указания числа элементов (если массив объявляется на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="80c00-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="80c00-110">Определите, требуется ли передача элемента, так как он является видимым в пределах всех процедур в модуле.</span><span class="sxs-lookup"><span data-stu-id="80c00-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="80c00-111">Определите, почему заблокирована `Variant` и разблокируйте ее.</span><span class="sxs-lookup"><span data-stu-id="80c00-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c00-112">См. также</span><span class="sxs-lookup"><span data-stu-id="80c00-112">See Also</span></span>  
 [<span data-ttu-id="80c00-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="80c00-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
