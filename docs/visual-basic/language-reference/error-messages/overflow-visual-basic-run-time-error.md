---
title: Переполнение (Ошибка во время выполнения Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: c45559042231b72ef1ba892cabbead03797df8e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642520"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="41b87-102">Переполнение (Ошибка во время выполнения Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="41b87-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="41b87-103">Переполнение возникает, когда вы попытаетесь задание, которое превышает ограничения целевой объект назначения.</span><span class="sxs-lookup"><span data-stu-id="41b87-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="41b87-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="41b87-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="41b87-105">Убедитесь, что результаты назначений, вычисления и тип данных преобразования не слишком велико для представления в диапазоне от переменных, допустимых для данного типа значения и присвойте значение переменной типа, который может содержать более широкий диапазон значений , если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="41b87-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="41b87-106">Убедитесь, что назначения свойств соответствуют указанному диапазону свойства, к которому они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="41b87-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="41b87-107">Убедитесь, что номера, используемые в вычислениях, которые затем преобразуются в целые числа не имеют результаты, размер которых превышает целых чисел.</span><span class="sxs-lookup"><span data-stu-id="41b87-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41b87-108">См. также</span><span class="sxs-lookup"><span data-stu-id="41b87-108">See also</span></span>
- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="41b87-109">Типы данных</span><span class="sxs-lookup"><span data-stu-id="41b87-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="41b87-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="41b87-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
