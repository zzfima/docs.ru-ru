---
title: Лямбда-выражения являются недопустимыми в первом выражении &#39;Select Case&#39; инструкции
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: afefa821f9695dbbfe2a96aee5afd3171ae5b1db
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700225"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Лямбда-выражения являются недопустимыми в первом выражении &#39;Select Case&#39; инструкции
Лямбда-выражения нельзя использовать для проверки выражения в `Select Case` инструкции. Определения лямбда-выражений возвращают функции, а выражение проверки `Select Case` инструкция должна быть простой тип данных.  
  
 Следующий код вызывает эту ошибку:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Идентификатор ошибки:** BC36635  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Проверьте свой код, чтобы определить, подойдет ли вам другая условная конструкция, например оператор `If...Then...Else` .  
  
-   Возможно, предполагалось вызывать функцию, как показано в следующем коде:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>См. также
- [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
