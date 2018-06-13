---
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6d082511d501b961b537317f0cb17bcd1c9370b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594625"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="8f9ad-102">Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов</span><span class="sxs-lookup"><span data-stu-id="8f9ad-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="8f9ad-103">Программный элемент, который принимает один или несколько аргументов включается в запрос LINQ.</span><span class="sxs-lookup"><span data-stu-id="8f9ad-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="8f9ad-104">Компилятор не может вывести переменную диапазона из этого элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="8f9ad-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="8f9ad-105">**Идентификатор ошибки:** BC36599</span><span class="sxs-lookup"><span data-stu-id="8f9ad-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8f9ad-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="8f9ad-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="8f9ad-107">Предоставьте явное имя переменной программный элемент, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="8f9ad-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f9ad-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8f9ad-108">See Also</span></span>  
 <span data-ttu-id="8f9ad-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f9ad-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="8f9ad-110">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="8f9ad-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
