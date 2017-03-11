---
title: "Одномерные массивы (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], одномерный"
  - "одномерные массивы [C#]"
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# Одномерные массивы (Руководство по программированию на C#)
Можно объявить массив из пяти целых чисел с одним измерением, как показано в следующем примере:  
  
 [!code-cs[csProgGuideArrays#4](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_1.cs)]  
  
 Массив содержит элементы с `array[0]` по `array[4]`.  Оператор [new](../../../csharp/language-reference/keywords/new.md) служит для создания массива и инициализации элементов массива со значениями по умолчанию.  В данном примере элементы массива инициализируются значением 0.  
  
 Массив, в котором хранятся строковые элементы, можно объявить таким же образом.  Примеры.  
  
 [!code-cs[csProgGuideArrays#5](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_2.cs)]  
  
## Инициализация массива  
 Массив можно инициализировать при объявлении. В этом случае спецификация ранга не нужна, поскольку она уже предоставлена по числу элементов в списке инициализации.  Примеры.  
  
 [!code-cs[csProgGuideArrays#6](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_3.cs)]  
  
 Строковый массив можно инициализировать таким же образом.  Ниже приведено объявление строкового массива, в котором каждый элемент инициализируется названием дня:  
  
 [!code-cs[csProgGuideArrays#7](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_4.cs)]  
  
 При инициализации массива при объявлении можно использовать следующие сочетания клавиш:  
  
 [!code-cs[csProgGuideArrays#8](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_5.cs)]  
  
 Можно объявить переменную массива без инициализации, но при присвоении массива этой переменной нужно использовать оператор `new`.  Примеры.  
  
 [!code-cs[csProgGuideArrays#9](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_6.cs)]  
  
 В C\# 3.0 поддерживаются неявно типизированные массивы.  Дополнительные сведения см. в разделе [Неявно типизированные массивы](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).  
  
## Массивы типов значений и ссылочных типов.  
 Рассмотрим следующие объявления массива:  
  
 [!code-cs[csProgGuideArrays#10](../../../csharp/programming-guide/arrays/codesnippet/csharp/single-dimensional-arrays_7.cs)]  
  
 Результат этого оператора зависит от того, является ли `SomeType` типом значения или ссылочным типом.  Если это тип значения, оператор создает массив из 10 элементов типа `SomeType`.  Если `SomeType` — ссылочный тип, оператор создает массив из 10 элементов, Каждый из которых инициализируется нулевой ссылкой.  
  
 Дополнительные сведения о типах значения и ссылочных типах см. в разделе [Типы](../../../csharp/language-reference/keywords/types.md).  
  
## См. также  
 <xref:System.Array>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)