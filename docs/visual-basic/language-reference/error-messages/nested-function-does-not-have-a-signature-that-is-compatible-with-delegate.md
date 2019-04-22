---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: 04eae6d2c6d64e8a0f46ae3c2801a7eb6d893dca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58822298"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-delegatename"></a>Вложенная функция не имеет сигнатуры, совместимой с делегатом '\<имя_делегата >'
Лямбда-выражение, явно назначенной делегат, который имеет несовместимую сигнатуру. Например, в следующем коде, делегировать `Del` имеет два целочисленных параметра.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Ошибка возникает, если лямбда-выражение с одним аргументом объявлен как тип `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Идентификатор ошибки:** BC36532  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Измените определения делегата или назначенного лямбда-выражения, таким образом, чтобы сигнатуры были совместимы.  
  
## <a name="see-also"></a>См. также

- [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
