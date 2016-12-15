---
title: "Универсальные шаблоны (Руководство по программированию на C#) | Microsoft Docs"
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
  - "C# - язык, универсальные шаблоны"
  - "универсальные шаблоны [C#]"
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Универсальные шаблоны (Руководство по программированию на C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Универсальные шаблоны были добавлены в язык C\# версии 2.0 и среду CLR.  Универсальные шаблоны в платформе .NET Framework представляют концепцию параметров типов, которые позволяют разрабатывать классы и методы, не придерживающиеся спецификации одного или нескольких типов до тех пор, пока класс или метод не будет объявлен клиентским кодом и пока не будет создан его экземпляр.  Например, используя параметр универсального типа T можно написать отдельный класс, который другой клиентский код сможет использовать без риска привидения во время выполнения или операций упаковки\-преобразования, как показано в следующем примере:  
  
 [!code-cs[csProgGuideGenerics#1](../../../csharp/programming-guide/generics/codesnippet/CSharp/index_1.cs)]  
  
## Общие сведения об универсальных шаблонах  
  
-   Используйте универсальные типы для достижения максимального уровня повторного использования кода, безопасности типа и производительности.  
  
-   Наиболее частым случаем использования универсальных шаблонов является создание классов коллекции.  
  
-   Библиотека классов платформы .NET Framework содержит несколько новых универсальных классов коллекций в пространстве имен <xref:System.Collections.Generic>.  Их следует использовать по мере возможности вместо таких классов как <xref:System.Collections.ArrayList> в пространстве имен <xref:System.Collections>.  
  
-   Можно создавать собственные универсальные интерфейсы, классы, методы, события и делегаты.  
  
-   Доступ универсальных классов к методам можно ограничить определенными типами данных.  
  
-   Сведения о типах, используемых в универсальном типе данных, можно получить во время выполнения путем отражения.  
  
## Связанные разделы  
 Дополнительные сведения:  
  
-   [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)  
  
-   [Преимущества универсальных шаблонов](../../../csharp/programming-guide/generics/benefits-of-generics.md)  
  
-   [Параметры универсального типа](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
-   [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
-   [Универсальные классы](../../../csharp/programming-guide/generics/generic-classes.md)  
  
-   [Универсальные интерфейсы](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
-   [Универсальные методы](../../../csharp/programming-guide/generics/generic-methods.md)  
  
-   [Универсальные делегаты](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
-   [Ключевое слово default](../../../csharp/programming-guide/generics/default-keyword-in-generic-code.md)  
  
-   [Различия между шаблонами языка C\+\+ и универсальными шаблонами языка C\#](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
-   [Универсальные типы и отражение](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
-   [Универсальные типы во время выполнения](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
-   [Универсальные шаблоны в библиотеке классов платформы .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md)  
  
## Спецификация языка C\#  
 Дополнительные сведения см. в разделе [Спецификация языка C\#](../../../csharp/language-reference/language-specification.md).  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Типы](../../../csharp/programming-guide/types/index.md)   
 [\<typeparam\>](../../../csharp/programming-guide/xmldoc/typeparam.md)   
 [\<typeparamref\>](../../../csharp/programming-guide/xmldoc/typeparamref.md)