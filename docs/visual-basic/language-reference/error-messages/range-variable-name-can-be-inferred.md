---
title: "Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords: BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c986fcf188482c526c53ddf3019cec5163d0b62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="4bca7-102">Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов</span><span class="sxs-lookup"><span data-stu-id="4bca7-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="4bca7-103">Программный элемент, который принимает один или несколько аргументов включается в запрос LINQ.</span><span class="sxs-lookup"><span data-stu-id="4bca7-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="4bca7-104">Компилятор не может вывести переменную диапазона из этого элемента программирования.</span><span class="sxs-lookup"><span data-stu-id="4bca7-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="4bca7-105">**Идентификатор ошибки:** BC36599</span><span class="sxs-lookup"><span data-stu-id="4bca7-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4bca7-106">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4bca7-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="4bca7-107">Предоставьте явное имя переменной программный элемент, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="4bca7-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bca7-108">См. также</span><span class="sxs-lookup"><span data-stu-id="4bca7-108">See Also</span></span>  
 <span data-ttu-id="4bca7-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bca7-109">[Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>  
 [<span data-ttu-id="4bca7-110">Предложение Select</span><span class="sxs-lookup"><span data-stu-id="4bca7-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
