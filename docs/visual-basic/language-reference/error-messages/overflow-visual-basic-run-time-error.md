---
title: "Переполнение (Ошибка во время выполнения Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="d5a95-102">Переполнение (Ошибка во время выполнения Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5a95-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="d5a95-103">Переполнение является результатом присваивания, которое нарушает ограничения присваиваемого результата.</span><span class="sxs-lookup"><span data-stu-id="d5a95-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5a95-104">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="d5a95-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="d5a95-105">Убедитесь, что результаты назначений, вычислений и данных типа преобразования не слишком велико для представления в диапазоне допустимых для данного типа значения переменных, а также присвоить значение переменной типа, может содержать больший диапазон значений , если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="d5a95-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="d5a95-106">Убедитесь, что назначения свойств соответствуют указанному диапазону свойства, к которому они были сделаны.</span><span class="sxs-lookup"><span data-stu-id="d5a95-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="d5a95-107">Убедитесь в том, что номера, используемые в вычислениях, которые затем преобразуются в целые числа нет результатов, превышающих целые числа.</span><span class="sxs-lookup"><span data-stu-id="d5a95-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a95-108">См. также</span><span class="sxs-lookup"><span data-stu-id="d5a95-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="d5a95-109">Типы данных</span><span class="sxs-lookup"><span data-stu-id="d5a95-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="d5a95-110">Типы ошибок</span><span class="sxs-lookup"><span data-stu-id="d5a95-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
