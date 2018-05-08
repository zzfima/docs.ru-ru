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
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39;IsNot&#39; операнд типа &#39;typename&#39; можно сравнивать только с &#39;ничего&#39;, так как &#39;typename&#39; — это тип, допускающий значение NULL
Переменная, объявленная как допускающая значение NULL, сравнивалась с выражением отличный от `Nothing` с помощью `IsNot` оператор.  
  
 **Идентификатор ошибки:** BC32128  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Чтобы сравнить тип nullable выражения, отличным от `Nothing` с помощью `IsNot` оператор, вызовите `GetType` метод в тип, допускающий значение NULL и сравните результат выражения, как показано в следующем примере.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>См. также  
 [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Оператор IsNot](../../../visual-basic/language-reference/operators/isnot-operator.md)
