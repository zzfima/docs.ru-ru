---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Выведение типа Nullable не поддерживается в данном контексте
Типы значений и структуры могут быть объявлены допускает значения NULL.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Однако нельзя использовать объявление nullable в сочетании с определением типа. Следующие примеры может вызвать эту ошибку.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Идентификатор ошибки:** BC36629  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Используйте `As` предложений, чтобы объявить переменную как допускающие значение NULL.  
  
## <a name="see-also"></a>См. также  
 [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
