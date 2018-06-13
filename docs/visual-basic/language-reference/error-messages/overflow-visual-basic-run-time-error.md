---
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 9db79071c4895d49680352bde2d0824a3756d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594179"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="03e0e-102">Переполнение (Ошибка во время выполнения Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03e0e-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="03e0e-103">Переполнение является результатом присваивания, которое нарушает ограничения присваиваемого результата.</span><span class="sxs-lookup"><span data-stu-id="03e0e-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="03e0e-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="03e0e-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="03e0e-105">Убедитесь, что результаты назначений, вычислений и данных типа преобразования не слишком велико для представления в диапазоне допустимых для данного типа значения переменных, а также присвоить значение переменной типа, может содержать больший диапазон значений , если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="03e0e-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="03e0e-106">Убедитесь, что назначения свойств соответствуют указанному диапазону свойства, к которому они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="03e0e-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="03e0e-107">Убедитесь в том, что номера, используемые в вычислениях, которые затем преобразуются в целые числа нет результатов, превышающих целые числа.</span><span class="sxs-lookup"><span data-stu-id="03e0e-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e0e-108">См. также</span><span class="sxs-lookup"><span data-stu-id="03e0e-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="03e0e-109">Типы данных</span><span class="sxs-lookup"><span data-stu-id="03e0e-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="03e0e-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="03e0e-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
