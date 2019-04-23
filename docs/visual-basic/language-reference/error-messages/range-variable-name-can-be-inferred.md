---
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: a0b5633bb0efb3c67f73810552ef9a14ac3d0c70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331654"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="9972a-102">Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов</span><span class="sxs-lookup"><span data-stu-id="9972a-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="9972a-103">Программный элемент, который принимает один или несколько аргументов включается в запрос LINQ.</span><span class="sxs-lookup"><span data-stu-id="9972a-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="9972a-104">Компилятор не может определить переменную диапазона из этого элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="9972a-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="9972a-105">**Идентификатор ошибки:** BC36599</span><span class="sxs-lookup"><span data-stu-id="9972a-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9972a-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="9972a-106">To correct this error</span></span>  
  
1. <span data-ttu-id="9972a-107">Предоставьте явное имя переменной для элемента программирования, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="9972a-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="9972a-108">См. также</span><span class="sxs-lookup"><span data-stu-id="9972a-108">See also</span></span>

- <span data-ttu-id="9972a-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9972a-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
- [<span data-ttu-id="9972a-110">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="9972a-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
