---
title: Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: f6cf397b1e76313ab399d5e39a43ae0263df619c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
Объект `For Each` цикл использует массив в качестве его *элемент* переменной итерации, но инициализирует этот массив.  
  
 Следующие инструкции показывают, как эта ошибка может быть создано.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Первый `For Each` инструкция является правильный способ доступа к элементам `arrayList`. Второй `For Each` инструкция создает эту ошибку.  
  
 **Идентификатор ошибки:** BC32039  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите инициализацию из объявления *элемент* переменной итерации.  
  
## <a name="see-also"></a>См. также  
 [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Коллекции](../../../standard/collections/index.md)
