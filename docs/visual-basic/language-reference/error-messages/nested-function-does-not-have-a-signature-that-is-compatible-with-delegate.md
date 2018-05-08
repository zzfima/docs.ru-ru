---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 94c53d30ad9aea9386fbb1be3e65fa31719f7a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;
Лямбда-выражение для делегата, имеющего несовместимая сигнатура назначено. Например, в следующем коде делегат `Del` имеет два параметра целого типа.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Эта ошибка возникает, если лямбда-выражение с одним аргументом объявляется как тип `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Идентификатор ошибки:** BC36532  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените определение делегата или назначенного лямбда-выражения, чтобы сигнатуры были совместимы.  
  
## <a name="see-also"></a>См. также  
 [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
