---
title: "Универсальные методы и массивы (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "массивы [C#], универсальные шаблоны"
  - "универсальные шаблоны [C#], массивы"
ms.assetid: 7d956536-3851-41b5-94ad-3e7c0a5fe485
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Универсальные методы и массивы (Руководство по программированию на C#)
В C\# версии 2.0 и более поздней версии одномерные массивы с нижней границей, равной нулю, автоматически реализуют <xref:System.Collections.Generic.IList%601>.  Это позволяет создавать универсальные методы, которые могут использовать тот же код для итерации массивов и других типов коллекции.  Данный метод особенно полезен для чтения данных в коллекциях.  Интерфейс <xref:System.Collections.Generic.IList%601> нельзя использовать для добавления или удаления элементов из массива.  При попытке вызова метода <xref:System.Collections.Generic.IList%601>, такого как <xref:System.Collections.Generic.IList%601.RemoveAt%2A>, в массиве в данном контексте, возникнет исключение.  
  
 В следующем примере кода показано, как отдельный универсальный метод, принимающий входной параметр <xref:System.Collections.Generic.IList%601>, может выполнять итерацию списка и массива – в данном случае массива целых чисел.  
  
 [!code-cs[csProgGuideGenerics#35](../../../csharp/programming-guide/generics/codesnippet/csharp/generics-and-arrays_1.cs)]  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)