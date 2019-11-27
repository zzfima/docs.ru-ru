---
title: Этот массив имеет фиксированную длину или временно заблокирован
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350787"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="95608-102">Массив имеет фиксированный размер или временно заблокирован (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95608-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="95608-103">Эта ошибка может быть вызвана следующими причинами.</span><span class="sxs-lookup"><span data-stu-id="95608-103">This error has the following possible causes:</span></span>  
  
- <span data-ttu-id="95608-104">Использование `ReDim` для изменения количества элементов массива фиксированного размера.</span><span class="sxs-lookup"><span data-stu-id="95608-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
- <span data-ttu-id="95608-105">Переизмерение динамического массива на уровне модуля, в котором один элемент был передан в процедуру в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="95608-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="95608-106">Если передается элемент, массив блокируется, чтобы предотвратить освобождение памяти для параметра ссылки в процедуре.</span><span class="sxs-lookup"><span data-stu-id="95608-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
- <span data-ttu-id="95608-107">Попытка присвоить значение переменной `Variant`, содержащей массив, но `Variant` в данный момент заблокирован.</span><span class="sxs-lookup"><span data-stu-id="95608-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="95608-108">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="95608-108">To correct this error</span></span>  
  
1. <span data-ttu-id="95608-109">Сделайте исходный массив динамическим, а не фиксированным, объявив его с `ReDim` (если массив объявляется в процедуре) или объявив его без указания количества элементов (если массив объявлен на уровне модуля.</span><span class="sxs-lookup"><span data-stu-id="95608-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2. <span data-ttu-id="95608-110">Определите, действительно ли нужно передать элемент, так как он видим во всех процедурах в модуле.</span><span class="sxs-lookup"><span data-stu-id="95608-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3. <span data-ttu-id="95608-111">Определите, что блокирует `Variant` и исследует его.</span><span class="sxs-lookup"><span data-stu-id="95608-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95608-112">См. также</span><span class="sxs-lookup"><span data-stu-id="95608-112">See also</span></span>

- [<span data-ttu-id="95608-113">Массивы</span><span class="sxs-lookup"><span data-stu-id="95608-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
