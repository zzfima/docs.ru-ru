---
title: Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: bee3bcd3701945f5cf77f6761defc8be77acf49f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843582"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Массив, объявленный как переменная управления циклом, не может быть объявлен с исходным размером
Объект `For Each` цикле используется массив в качестве его *элемент* переменной итерации, но инициализирует этот массив.  
  
 Следующие инструкции показывают, как эта ошибка может возникать.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Первый `For Each` инструкция — это правильный способ доступа к элементам массива `arrayList`. Второй `For Each` инструкция создает эту ошибку.  
  
 **Идентификатор ошибки:** BC32039  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Удалите инициализацию из объявления *элемент* переменной итерации.  
  
## <a name="see-also"></a>См. также

- [Оператор For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Коллекции](../../../standard/collections/index.md)
