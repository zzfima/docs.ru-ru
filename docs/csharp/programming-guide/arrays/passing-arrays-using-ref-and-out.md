---
title: "Передача массивов при помощи параметров ref и out (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], передача с помощью операторов ref и out"
ms.assetid: 6a2b261e-a1cc-49a6-b4f0-6cacae385a1e
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Передача массивов при помощи параметров ref и out (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Как и все параметры [out](../../../csharp/language-reference/keywords/out.md), параметр `out` типа массива перед использованием необходимо присвоить, то есть он должен быть присвоен вызываемым объектом.  Например:  
  
 [!code-cs[csProgGuideArrays#39](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_1.cs)]  
  
 Как и все параметры [ref](../../../csharp/language-reference/keywords/ref.md), параметр `ref` типа массива должен быть явно присвоен вызывающим объектом.  Таким образом, явное присвоение вызываемым объектом не требуется.  Параметр `ref` типа массива в результате вызова может быть изменен.  Например, массиву можно присвоить значение [null](../../../csharp/language-reference/keywords/null.md), или же его можно инициализировать в другой массив.  Например:  
  
 [!code-cs[csProgGuideArrays#40](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_2.cs)]  
  
 В следующих двух примерах демонстрируются различия между параметрами `out` и `ref` при их использовании для передачи массивов в методы.  
  
## Пример  
 В следующем примере массив `theArray` объявляется в вызывающем объекте \(методе `Main`\) и инициализируется в методе `FillArray`.  Затем элементы массива возвращаются вызывающему объекту и отображаются.  
  
 [!code-cs[csProgGuideArrays#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_3.cs)]  
  
## Пример  
 В следующем примере массив `theArray` инициализируется в вызывающем объекте \(методе `Main`\) и передается в метод `FillArray` с помощью параметра `ref`.  Некоторые элементы массива в методе `FillArray` обновляются.  Затем элементы массива возвращаются вызывающему объекту и отображаются.  
  
 [!code-cs[csProgGuideArrays#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/passing-arrays-using-ref-and-out_4.cs)]  
  
## См. также  
 [ref](../../../csharp/language-reference/keywords/ref.md)   
 [Модификатор параметров out](../../../csharp/language-reference/keywords/out-parameter-modifier.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)