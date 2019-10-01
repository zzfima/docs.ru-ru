---
title: Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36556
- bc36556
helpviewer_keywords:
- BC36556
ms.assetid: e3ba1f33-3a71-4f03-9b04-ed5ec17de17c
ms.openlocfilehash: 38f669fe183ac79ebed6e5a122bc70aedc9bb753
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701217"
---
# <a name="anonymous-type-member-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Имя члена анонимного типа может быть определено только из простого или уточненного имени без аргументов
Нельзя вывести имя члена анонимного типа из сложного выражения.  
  
```vb  
Dim numbers() As Integer = {1, 2, 3, 4, 5}  
' Not valid.  
' Dim instanceName1 = New With {numbers(3)}  
```  
  
 Дополнительные сведения об источниках, из которых анонимные типы могут и не могут вычислять имена и типы членов, см. в разделе [How to: Выводит имена и типы свойств в объявлениях анонимного типа @ no__t-0.  
  
 **Идентификатор ошибки:** BC36556  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Назначьте выражение имени члена, как показано в следующем коде:  
  
    ```vb  
    Dim instanceName2 = New With {.number = numbers(3)}  
    ```  
  
## <a name="see-also"></a>См. также

- [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Практическое руководство. Выводит имена и типы свойств в объявлениях анонимного типа @ no__t-0
