---
title: "&#39; IsNot &#39; операнд типа &#39; typename &#39; можно сравнивать только с &#39; Ничего не &#39; так как &#39; typename &#39; — Это тип, допускающий значение NULL"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords: BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec0ae1561bfbee998e7c65f6023012c0f982a8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="cc565-102">&#39; IsNot &#39; операнд типа &#39; typename &#39; можно сравнивать только с &#39; Ничего не &#39; так как &#39; typename &#39; — Это тип, допускающий значение NULL</span><span class="sxs-lookup"><span data-stu-id="cc565-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="cc565-103">Переменная, объявленная как допускающая значение NULL, сравнивалась с выражением отличный от `Nothing` с помощью `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="cc565-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="cc565-104">**Идентификатор ошибки:** BC32128</span><span class="sxs-lookup"><span data-stu-id="cc565-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cc565-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="cc565-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="cc565-106">Чтобы сравнить тип nullable выражения, отличным от `Nothing` с помощью `IsNot` оператор, вызовите `GetType` метод в тип, допускающий значение NULL и сравните результат выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="cc565-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc565-107">См. также</span><span class="sxs-lookup"><span data-stu-id="cc565-107">See Also</span></span>  
 [<span data-ttu-id="cc565-108">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="cc565-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="cc565-109">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="cc565-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
