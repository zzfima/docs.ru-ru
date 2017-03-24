---
title: "Параметры универсального типа (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "универсальные шаблоны [C#], параметры типа"
  - "параметры типа [C#]"
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
caps.latest.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 23
---
# Параметры универсального типа (Руководство по программированию на C#)
В определении универсального типа или метода параметры типа представляют собой заполнитель для определенного типа, задаваемого клиентом при создании переменной универсального типа.  Универсальный класс, такой как `GenericList<T>` listed in [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md), нельзя использовать "как есть", поскольку он является не типом а, скорее, чертежом типа.  Для работы с `GenericList<T>` в клиентском коде необходимо объявить и создать конструируемый тип, указав в угловых скобках аргумент типа.  Аргумент\-тип для этого конкретного класса может быть любым типом, распознаваемым компилятором.  Можно создать любое количество экземпляров конструируемых типов, и каждый из них может использовать разные аргументы типа, как показано далее.  
  
 [!code-cs[csProgGuideGenerics#7](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_1.cs)]  
  
 В каждом экземпляре `GenericList<T>` каждое вхождение `T` в классе будет заменено во время выполнения аргументом типа.  С помощью данной замены было создано три отдельных типобезопасных и эффективных объекта, использующих определение класса.  Дополнительные сведения о выполнении этой замены в CLR см. раздел [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).  
  
## Рекомендации по именованию параметра типа  
  
-   При именовании параметров универсальных типов **используйте** описательные имена, если только однобуквенное имя не является полностью понятным без пояснений, вследствие чего нет необходимости применять описательное имя.  
  
     [!code-cs[csProgGuideGenerics#8](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_2.cs)]  
  
-   Для типов с однобуквенными параметрами **рекомендуется** использовать "T" в качестве имени параметра типа.  
  
     [!code-cs[csProgGuideGenerics#9](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_3.cs)]  
  
-   К описательным именам параметров типа **добавляйте** префикс "T".  
  
     [!code-cs[csProgGuideGenerics#10](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-type-parameters_4.cs)]  
  
-   В имени параметра **рекомендуется** указывать ограничения, накладываемые на параметр типа.  Например, параметр, предназначенный только для `ISession`, может называться `TSession`.  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)   
 [Различия между шаблонами языка C\+\+ и универсальными шаблонами языка C\#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)