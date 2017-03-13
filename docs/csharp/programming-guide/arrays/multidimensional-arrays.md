---
title: "Многомерные массивы (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], многомерные"
  - "многомерные массивы [C#]"
ms.assetid: 020ce02e-7dff-4273-8e53-bf0b33747232
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Многомерные массивы (Руководство по программированию на C#)
Массивы могут иметь несколько измерений.  Например, следующее объявление создает двумерный массив из четырех строк и двух столбцов.  
  
 [!code-cs[csProgGuideArrays#11](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_1.cs)]  
  
 Следующее объявление создает трехмерный массив с количеством элементов 4, 2 и 3.  
  
 [!code-cs[csProgGuideArrays#12](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_2.cs)]  
  
## Инициализация массива  
 Массив можно инициализировать при объявлении, как показано в следующем примере.  
  
 [!code-cs[csProgGuideArrays#13](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_3.cs)]  
  
 Можно также инициализировать массив, не указывая его размерность.  
  
 [!code-cs[csProgGuideArrays#14](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_4.cs)]  
  
 Если нужно создать переменную массива без инициализации, то необходимо использовать оператор `new`, чтобы присвоить массив переменной.  В следующем примере показано использование `new`.  
  
 [!code-cs[csProgGuideArrays#15](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_5.cs)]  
  
 Следующий пример присваивает значение конкретному элементу массива.  
  
 [!code-cs[csProgGuideArrays#16](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_6.cs)]  
  
 Аналогичным образом, в следующем примере получено значение конкретного элемента массива и оно назначено  переменной `elementValue`.  
  
 [!code-cs[csProgGuideArrays#42](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_7.cs)]  
  
 В следующем примере кода элементы массивов инициализируются значениями по умолчанию \(за исключением массивов массивов\).  
  
 [!code-cs[csProgGuideArrays#17](../../../csharp/programming-guide/arrays/codesnippet/CSharp/multidimensional-arrays_8.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)