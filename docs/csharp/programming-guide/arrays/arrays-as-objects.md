---
title: "Массивы как объекты (Руководство по программированию на C#) | Microsoft Docs"
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
  - "массивы [C#], как объекты"
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
caps.latest.revision: 17
caps.handback.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Массивы как объекты (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В C\# массивы фактически являются объектами, а не только адресуемыми областями непрерывной памяти, как в C и C\+\+.  <xref:System.Array> является абстрактным базовым типом всех типов массивов.  Можно использовать свойства и другие члены класса, которые имеет <xref:System.Array>.  В примере используется свойство <xref:System.Array.Length%2A> для получения длины массива.  В следующем коде длина массива `numbers`, равная `5`, присваивается переменной `lengthOfNumbers`:  
  
 [!code-cs[csProgGuideArrays#3](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_1.cs)]  
  
 Класс <xref:System.Array> позволяет использовать много других полезных методов и свойств для выполнения сортировки, поиска и копирования массивов.  
  
## Пример  
 В этом примере свойство <xref:System.Array.Rank%2A> используется для отображения числа измерений массива.  
  
 [!code-cs[csProgGuideArrays#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/arrays-as-objects_2.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Одномерные массивы](../../../csharp/programming-guide/arrays/single-dimensional-arrays.md)   
 [Многомерные массивы](../../../csharp/programming-guide/arrays/multidimensional-arrays.md)   
 [Массивы массивов](../../../csharp/programming-guide/arrays/jagged-arrays.md)