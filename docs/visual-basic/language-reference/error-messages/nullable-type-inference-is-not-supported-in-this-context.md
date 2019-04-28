---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 9f7f878649d8b96f050b56d5b878eb3d67e027ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918226"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Выведение типа Nullable не поддерживается в данном контексте
Типы значений и структуры могут объявляться допускает значения NULL.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Тем не менее нельзя использовать объявление nullable в сочетании с определением типа. Следующие примеры вызывать эту ошибку.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Идентификатор ошибки:** BC36629  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте `As` предложение, чтобы объявить переменную как допускающие значение NULL.  
  
## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
