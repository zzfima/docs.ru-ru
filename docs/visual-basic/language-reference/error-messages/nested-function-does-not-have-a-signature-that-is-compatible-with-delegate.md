---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом '<delegatename>'
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: ea6f230715520cb35809d57db76b300da326ec9a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283469"
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
