---
title: Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: abfda4ee6064ec9ea54b8a3c383d10f8263a1458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506411"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;
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
