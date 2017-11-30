---
title: "Вложенная функция не имеет сигнатуры, совместимой с делегатом &#39; &lt;имя_делегата&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords: BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 60cf15343023110561da3e3fcf202bd00394127a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
