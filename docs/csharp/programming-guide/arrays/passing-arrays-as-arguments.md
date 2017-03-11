---
title: "Передача массивов в качестве аргументов (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], передача в качестве аргументов"
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Передача массивов в качестве аргументов (Руководство по программированию на C#)
Массивы можно передавать в качестве аргументов для параметров методов.  Поскольку массивы являются ссылочными типами, метод может изменять значение элементов.  
  
## Передача одномерных массивов в качестве аргументов  
 Инициализированный одномерный массив можно передать в метод.  Например, следующая инструкция передает массив в метод печати.  
  
 [!code-cs[csProgGuideArrays#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_1.cs)]  
  
 В следующем примере кода показана частичная реализация метода печати.  
  
 [!code-cs[csProgGuideArrays#33](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_2.cs)]  
  
 Инициализацию и передачу нового массива можно выполнить в рамках одного шага, как показано в следующем примере.  
  
 [!code-cs[CsProgGuideArrays#35](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_3.cs)]  
  
## Пример  
  
### Описание  
 В следующем примере массив строк инициализируется и передается в качестве аргумента метода `PrintArray`.  Затем метод отображает элементы этого массива.  Затем вызываются методы `ChangeArray` и `ChangeArrayElement` для демонстрации того, что отправка аргумента массива по значению не запрещает вносить изменения в элементы массива.  
  
### Код  
 [!code-cs[csProgGuideArrays#30](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_4.cs)]  
  
## Передача многомерных массивов в качестве аргументов  
 Инициализированный многомерный массив передается методу так же, как и одномерный массив.  
  
 [!code-cs[csProgGuideArrays#41](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_5.cs)]  
  
 В следующем примере кода показано частичное объявление метода печати, который принимает в качестве аргумента двумерный массив.  
  
 [!code-cs[csProgGuideArrays#36](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_6.cs)]  
  
 Инициализацию и передачу нового массива можно выполнить в рамках одного шага, как показано в следующем примере.  
  
 [!code-cs[csProgGuideArrays#32](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_7.cs)]  
  
## Пример  
  
### Описание  
 В следующем примере двумерный массив целых чисел инициализируется и передается в метод `Print2DArray`.  Затем метод отображает элементы этого массива.  
  
### Код  
 [!code-cs[csProgGuideArrays#31](../../../csharp/programming-guide/arrays/codesnippet/csharp/passing-arrays-as-argume_8.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)