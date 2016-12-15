---
title: "Ключевое слово default в универсальном коде (Руководство по программированию на C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "default - ключевое слово [C#], обобщенное программирование"
  - "универсальные шаблоны [C#], default - ключевое слово"
ms.assetid: b9daf449-4e64-496e-8592-6ed2c8875a98
caps.latest.revision: 22
caps.handback.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Ключевое слово default в универсальном коде (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В универсальных классах и методах одной из существующих проблем является назначение параметризованному типу T значения по умолчанию, если заранее неизвестны следующие моменты.  
  
-   Является ли T ссылочным типом или типом значения.  
  
-   Ели T является типом значения, будет ли он числовым значением или структурой.  
  
 При заданной переменной t параметризованного типа T оператор t \= null действителен, если только T является ссылочным типом, а t \= 0 будет справедливо только для числовых типов значений, но не для структур.  Решением является использование ключевого слова `default`, которое вернет значение null для ссылочных типов и "0" — для числовых типов значений.  Для структур оно вернет каждого члена со значением "0" или null в зависимости от их типа — тип значения или ссылочный тип.  Для типов, допускающих значение null, ключевое слово default вернет значение <xref:System.Nullable%601?displayProperty=fullName>, которое инициализируется как любая структура.  
  
 В следующем примере из класса `GenericList<T>` демонстрируется использование ключевого слова `default`.  Дополнительные сведения содержатся в разделе [Общие сведения об универсальных шаблонах](../../../csharp/programming-guide/generics/introduction-to-generics.md).  
  
 [!code-cs[csProgGuideGenerics#41](../../../csharp/programming-guide/generics/codesnippet/CSharp/default-keyword-in-generic-code_1.cs)]  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md)   
 [Универсальные шаблоны](../Topic/Generics%20in%20the%20.NET%20Framework.md)