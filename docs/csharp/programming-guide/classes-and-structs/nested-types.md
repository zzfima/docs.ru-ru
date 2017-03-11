---
title: "Вложенные типы (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "вложенные типы [C#]"
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# Вложенные типы (Руководство по программированию на C#)
Тип, определенный внутри [класса](../../../csharp/language-reference/keywords/class.md) или [структуры](../../../csharp/language-reference/keywords/struct.md), называется вложенным типом.  Пример:  
  
 [!code-cs[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/nested-types_1.cs)]  
  
 Независимо от того, являются ли внешние типы классом или структурой, вложенные типы по умолчанию являются [private](../../../csharp/language-reference/keywords/private.md), но могут быть также [public](../../../csharp/language-reference/keywords/public.md), protected internal, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) или [private](../../../csharp/language-reference/keywords/private.md).  В предыдущем примере тип `Nested` недоступен для внешних типов, но он может быть являться открытым \(public\):  
  
 [!code-cs[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/nested-types_2.cs)]  
  
 Вложенный тип может получить доступ к вмещающему типу, а внутренний тип — к внешнему.  Чтобы получить доступ к вмещающему типу, передайте его в качестве конструктора во вложенный тип.  Пример:  
  
 [!code-cs[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/nested-types_3.cs)]  
  
 Вложенный тип имеет доступ ко всем членам, которые доступны вмещающему типу.  Он может получать доступ к закрытым и защищенным членам вмещающего типа, включая любые наследуемые защищенные члены.  
  
 В предыдущем объявлении полным именем класса `Nested` является `Container.Nested`.  Это имя используется для создания нового экземпляра вложенного класса, как показано ниже:  
  
 [!code-cs[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/csharp/nested-types_4.cs)]  
  
## См. также  
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)