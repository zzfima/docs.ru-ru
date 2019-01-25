---
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 8b95bb3c53210cc11966466d32924c13aee8234b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54581956"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
Программный элемент, который принимает один или несколько аргументов включается в запрос LINQ. Компилятор не может определить переменную диапазона из этого элемента программирования.  
  
 **Идентификатор ошибки:** BC36599  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Предоставьте явное имя переменной для элемента программирования, как показано в следующем коде:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>См. также
- [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
