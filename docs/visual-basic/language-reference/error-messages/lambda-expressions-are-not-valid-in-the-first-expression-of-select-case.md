---
title: "Лямбда-выражения недопустимы в первом выражении &#39; Выберите вариант &#39; инструкции"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords: BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e91401d6891d4e38014bb716a337560885cf73a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Лямбда-выражения недопустимы в первом выражении &#39; Выберите вариант &#39; инструкции
Лямбда-выражения нельзя использовать для проверки выражения в `Select Case` инструкции. Определения лямбда-выражений возвращают функции, а тестовое выражение `Select Case` инструкция должна быть простой тип данных.  
  
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
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [Оператор If...Then...Else](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Оператор Select...Case](../../../visual-basic/language-reference/statements/select-case-statement.md)
