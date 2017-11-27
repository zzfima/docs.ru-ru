---
title: "Практическое руководство. Присвоение одного массива другому (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0dd2d678bbfdeaa6b12b5b5a4f69d0fbca8c1944
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a>Практическое руководство. Присвоение одного массива другому (Visual Basic)
Поскольку массивы — это объекты, их можно использовать в инструкциях присваивания, как и другие типы объектов. Переменная массива содержит указатель на данные, составляющие элементы массива и сведения о ранге и длине и назначения копирует только этот указатель.  
  
### <a name="to-assign-one-array-to-another-array"></a>Чтобы назначить один массив другого массива  
  
1.  Убедитесь, что два массива имеют одинаковый ранг (число измерений) и совместимый тип данных элементов.  
  
2.  Используйте стандартный оператор присваивания для присваивания исходного массива в массив назначения. Не выполняйте либо имя массива в круглые скобки.  
  
    ```  
    Dim formArray() As System.Windows.Forms.Form  
    Dim controlArray() As System.Windows.Forms.Control  
    controlArray = formArray  
    ```  
  
 При назначении одного массива в другой, применяются следующие правила:  
  
-   **Равенство ранга.** Ранг (число измерений) массива назначения должен быть таким же, как и для исходного массива.  
  
     Предоставляемые равны ранги двух массивов, размеры не обязательно должны совпадать. Количество элементов в определенном измерении может изменяться во время назначения.  
  
-   **Типы элементов.** Либо оба массива должны состоять *ссылочному типу* элементы или оба массива должны иметь *тип значения* элементов. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
    -   Если оба массива состоят из значений, их типы должны полностью совпадать. Единственным исключением является, которые можно назначить массив `Enum` элементы в массив, базовый тип `Enum`.  
  
    -   Если оба массива содержат элементы ссылочного типа, исходный тип элементов должен быть производным от типа конечного элемента. В случае два массива имеют такое же отношение наследования, что и их элементы. Это называется *Ковариация массивов*.  
  
 Компилятор выдает ошибку, если приведенные выше правила нарушены, например если типы данных несовместимы или ранги не равны. Можно добавить в код, чтобы убедиться в том, что массивы совместимы перед выполнением назначения обработки ошибок. Можно также использовать [оператор TryCast](../../../../visual-basic/language-reference/operators/trycast-operator.md) ключевое слово, если вы хотите избежать создания исключения.  
  
## <a name="see-also"></a>См. также  
 [Массивы](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Устранение неполадок, связанных с массивами](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Оператор Enum](../../../../visual-basic/language-reference/statements/enum-statement.md)  
 [Преобразования массивов](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
