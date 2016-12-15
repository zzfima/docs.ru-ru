---
title: "Массивы массивов (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], неравномерный"
  - "неравномерные массивы [C#]"
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
caps.latest.revision: 24
caps.handback.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Массивы массивов (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Массив массивов — это массив, элементы которого сами являются массивами.  Элементы массива массивов могут иметь различные размеры и измерения.  Массивы массивов иногда также называются "невыровненными массивами". В следующих примерах показано, как выполняется объявление, инициализация и доступ к массивам массивов.  
  
 Ниже показано объявление одномерного массива, включающего три элемента, каждый из которых является одномерным массивом целых чисел.  
  
 [!code-cs[csProgGuideArrays#19](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_1.cs)]  
  
 Перед использованием `jaggedArray` его элементы нужно инициализировать.  Сделать это можно следующим образом.  
  
 [!code-cs[csProgGuideArrays#20](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_2.cs)]  
  
 Каждый элемент представляет собой одномерный массив целых чисел.  Первый элемент массива состоит из пяти целях чисел, второй — из четырех и третий — из двух.  
  
 Для заполнения элементов массива значениями можно также использовать инициализаторы, при этом размер массива знать не требуется.  Примеры.  
  
 [!code-cs[csProgGuideArrays#21](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_3.cs)]  
  
 Также массив можно инициализировать путем объявления.  
  
 [!code-cs[csProgGuideArrays#22](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_4.cs)]  
  
 Также можно использовать сокращенную форму.  Обратите внимание, что при инициализации элементов оператор `new` опускать нельзя, так как инициализации по умолчанию для этих элементов не существует.  
  
 [!code-cs[csProgGuideArrays#23](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_5.cs)]  
  
 Невыровненный массив является массивом массивов и поэтому его элементы являются ссылочными типами и инициализируются значением `null`.  
  
 Доступ к отдельным элементам массива выполняется следующим образом.  
  
 [!code-cs[csProgGuideArrays#24](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_6.cs)]  
  
 Массивы массивов можно смешивать с многомерными массивами.  Ниже показано объявление и инициализация одномерного массива массивов, состоящего из трех двумерных элементов различного размера.  Дополнительные сведения о двумерных массивах см. в разделе [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md).  
  
 [!code-cs[csProgGuideArrays#25](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_7.cs)]  
  
 Доступ к отдельным элементам выполняется как показано в примере ниже, где отображено значение элемента `[1,0]` первого массива \(значение `5`\).  
  
 [!code-cs[csProgGuideArrays#26](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_8.cs)]  
  
 Метод `Length` возвращает число массивов, содержащихся в массиве массивов.  Например, если объявить предыдущий массив, мы получим следующее.  
  
 [!code-cs[csProgGuideArrays#27](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_9.cs)]  
  
 возвращает значение 3.  
  
## Пример  
 В этом примере выполняется создание массива, элементы которого сами являются массивами.  Каждый элемент массива имеет собственный размер.  
  
 [!code-cs[csProgGuideArrays#18](../../../csharp/programming-guide/arrays/codesnippet/CSharp/jagged-arrays_10.cs)]  
  
## См. также  
 <xref:System.Array>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)