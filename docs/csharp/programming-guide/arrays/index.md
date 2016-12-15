---
title: "Массивы (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#]"
  - "C# - язык, массивы"
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
caps.latest.revision: 33
caps.handback.revision: 33
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Массивы (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Можно сохранить несколько переменных одного типа в структуре данных массива.  Массив объявляется указанием типа элементов.  
  
 `type[] arrayName;`  
  
 В следующем примере показано создание одномерных, многомерных массивов и массивов массивов.  
  
 [!code-cs[csProgGuideArrays#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/index_1.cs)]  
  
## Общие сведения о массивах  
 Массив имеет следующие свойства.  
  
-   Массив может быть [одномерным](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md), [многомерным](../../../csharp/programming-guide/arrays/multidimensional-arrays.md) или [массивом массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md).  
  
-   Заданы количество измерений и длину каждого измерения, когда создается экземпляр массива.  Эти значения невозможно изменить во время существования экземпляра.  
  
-   Значения по умолчанию числовых элементов массива задано равным нулю, а элементы ссылок имеют значение NULL.  
  
-   Невыровненный массив является массивом массивов и поэтому его элементы являются ссылочными типами и инициализируются значением `null`.  
  
-   Индексация массивов начинается с нуля: массив с элементами `n` индексируется от `0` до `n-1`.  
  
-   Элементы массива могут быть любых типов, включая тип массива.  
  
-   Типы массива являются [ссылочными типами](../../../csharp/language-reference/keywords/reference-types.md), производными от абстрактного базового типа <xref:System.Array>.  Поскольку этот тип реализует <xref:System.Collections.IEnumerable> и <xref:System.Collections.Generic.IEnumerable%601>, в C\# во всех массивах можно использовать итерацию [foreach](../../../csharp/language-reference/keywords/foreach-in.md).  
  
## Связанные разделы  
  
-   [Массивы как объекты](../../../csharp/programming-guide/arrays/arrays-as-objects.md)  
  
-   [Использование оператора foreach с массивами](../../../csharp/programming-guide/arrays/using-foreach-with-arrays.md)  
  
-   [Передача массивов в качестве аргументов](../../../csharp/programming-guide/arrays/passing-arrays-as-arguments.md)  
  
-   [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md)  
  
-   [Дополнительные сведения о переменных](http://go.microsoft.com/fwlink/?LinkId=221230) в [Начало работы с Visual C\# 2010](http://go.microsoft.com/fwlink/?LinkId=221214)  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Коллекции](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)   
 [Array Collection Type](http://msdn.microsoft.com/ru-ru/8a9964de-8941-47b1-a3cf-a01bc88db9e8)