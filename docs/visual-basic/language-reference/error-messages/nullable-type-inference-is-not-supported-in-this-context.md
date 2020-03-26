---
title: Выведение типа Nullable не поддерживается в данном контексте
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249504"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Выведение типа Nullable не поддерживается в данном контексте
Типы значений и структуры могут быть признаны недействительными.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Однако вы не можете использовать необдательную декларацию в сочетании с выводом типа. Следующие примеры вызывают эту ошибку.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Идентификатор ошибки:** BC36629  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Используйте `As` оговорку, чтобы объявить переменную в качестве необобнажаемого типа значения.  
  
## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Вывод локального типа](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
