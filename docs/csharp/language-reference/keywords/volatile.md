---
title: "volatile (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "volatile_CSharpKeyword"
  - "volatile"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "volatile - ключевое слово [C#]"
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
caps.latest.revision: 29
caps.handback.revision: 29
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# volatile (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Ключевое слово `volatile` указывает, что поле может быть изменено несколькими потоками, выполняющимися одновременно.  Поля, объявленные как `volatile`, не проходят оптимизацию компилятором, которая предусматривает доступ посредством отдельного потока.  Это гарантирует наличие наиболее актуального значения в поле в любое время.  
  
 Как правило, модификатор `volatile` используется для поля, обращение к которому выполняется через несколько потоков без использования оператора [lock](../../../csharp/language-reference/keywords/lock-statement.md) для сериализации доступа.  
  
 Ключевое слово `volatile` можно применять к полям следующих типов.  
  
-   Ссылочные типы.  
  
-   Типы указателей \(в небезопасном контексте\).  Обратите внимание, что несмотря на то, что сам указатель может быть "volatile", объект, на который он указывает, таковым быть не может.  Другими словами, нельзя объявить указатель "volatile".  
  
-   Типы, такие как sbyte, byte, short, ushort, int, uint, char, float и bool.  
  
-   Тип перечисления с одним из следующих базовых типов: byte, sbyte, short, ushort, int или uint.  
  
-   Параметры универсальных типов, являющиеся ссылочными типами.  
  
-   <xref:System.IntPtr> и <xref:System.UIntPtr>.  
  
 Ключевое слово volatile можно применить только к полям класса или структуры.  Локальные переменные не могут быть объявлены как `volatile`.  
  
## Пример  
 В следующем примере показано как объявить открытую переменную поля в качестве `volatile`.  
  
 [!code-cs[csrefKeywordsModifiers#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_1.cs)]  
  
## Пример  
 В следующем примере демонстрируется создание вспомогательного или рабочего потока и использование его для выполнения обработки параллельно с основным потоком.  Дополнительные сведения о многопоточности см. в разделах [Threading](../Topic/Managed%20Threading.md) и [Потоки](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md).  
  
 [!code-cs[csProgGuideThreading#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/volatile_2.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)