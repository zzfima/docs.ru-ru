---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: ea531c7be676e940a263b019a66cc80cf280a772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
