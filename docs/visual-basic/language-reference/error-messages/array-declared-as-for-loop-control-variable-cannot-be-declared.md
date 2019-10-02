---
title: Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: 9e8bb7b79b5a770c3c92e47d8e7c01c5b83d6061
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701207"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
Цикл `For Each` использует массив в качестве переменной итерации *элемента* , но инициализирует этот массив.  
  
 Следующие инструкции показывают, как можно создать эту ошибку.  
  
```vb  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Первая инструкция `For Each` является правильным способом доступа к элементам `arrayList`. Вторая инструкция `For Each` вызывает эту ошибку.  
  
 **Идентификатор ошибки:** BC32039  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Удалите инициализацию из объявления переменной итерации *элемента* .  
  
## <a name="see-also"></a>См. также

- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Коллекции](../../../standard/collections/index.md)
