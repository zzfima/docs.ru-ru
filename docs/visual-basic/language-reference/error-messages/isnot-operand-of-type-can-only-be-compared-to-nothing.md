---
title: '&#39;IsNot&#39; операнд типа &#39;typename&#39; можно сравнивать только с &#39;ничего&#39;, так как &#39;typename&#39; — это тип, допускающий значение NULL'
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: 44cc17c73b476e5e322b9b58b021bc7bcd63167f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a><span data-ttu-id="4e8b5-102">&#39;IsNot&#39; операнд типа &#39;typename&#39; можно сравнивать только с &#39;ничего&#39;, так как &#39;typename&#39; — это тип, допускающий значение NULL</span><span class="sxs-lookup"><span data-stu-id="4e8b5-102">&#39;IsNot&#39; operand of type &#39;typename&#39; can only be compared to &#39;Nothing&#39;, because &#39;typename&#39; is a nullable type</span></span>
<span data-ttu-id="4e8b5-103">Переменная, объявленная как допускающая значение NULL, сравнивалась с выражением отличный от `Nothing` с помощью `IsNot` оператор.</span><span class="sxs-lookup"><span data-stu-id="4e8b5-103">A variable declared as nullable has been compared to an expression other than `Nothing` using the `IsNot` operator.</span></span>  
  
 <span data-ttu-id="4e8b5-104">**Идентификатор ошибки:** BC32128</span><span class="sxs-lookup"><span data-stu-id="4e8b5-104">**Error ID:** BC32128</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e8b5-105">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="4e8b5-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="4e8b5-106">Чтобы сравнить тип nullable выражения, отличным от `Nothing` с помощью `IsNot` оператор, вызовите `GetType` метод в тип, допускающий значение NULL и сравните результат выражения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4e8b5-106">To compare a nullable type to an expression other than `Nothing` by using the `IsNot` operator, call the `GetType` method on the nullable type and compare the result to the expression, as shown in the following example.</span></span>  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="4e8b5-107">См. также</span><span class="sxs-lookup"><span data-stu-id="4e8b5-107">See Also</span></span>  
 [<span data-ttu-id="4e8b5-108">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="4e8b5-108">Nullable Value Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="4e8b5-109">Оператор IsNot</span><span class="sxs-lookup"><span data-stu-id="4e8b5-109">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
