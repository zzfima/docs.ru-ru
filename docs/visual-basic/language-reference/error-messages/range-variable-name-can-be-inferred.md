---
title: Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6d082511d501b961b537317f0cb17bcd1c9370b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594625"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Имя переменной диапазона может быть выведено только из простого или полного имени без аргументов
Программный элемент, который принимает один или несколько аргументов включается в запрос LINQ. Компилятор не может вывести переменную диапазона из этого элемента программирования.  
  
 **Идентификатор ошибки:** BC36599  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Предоставьте явное имя переменной программный элемент, как показано в следующем коде:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>См. также  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [Предложение Select](../../../visual-basic/language-reference/queries/select-clause.md)
