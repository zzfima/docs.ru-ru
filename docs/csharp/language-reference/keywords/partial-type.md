---
title: "разделяемый (тип) (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "partialtype"
  - "partialtype_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "разделяемые типы [C#]"
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
caps.latest.revision: 24
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 24
---
# разделяемый (тип) (Справочник по C#)
Определения разделяемых типов позволяют разделять определения для классов, структур и интерфейсов на несколько файлов.  
  
 В File1.cs:  
  
 [!code-cs[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 В File2.cs объявление:  
  
 [!code-cs[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## Заметки  
 Разделение типа класса, структуры или интерфейса на несколько файлов может пригодиться при работе с крупными проектами или с автоматически созданным кодом, например с кодом [Windows Forms Designer](http://msdn.microsoft.com/ru-ru/3c3d61f8-f36c-4d41-b9c3-398376fabb15).  Разделяемый тип может содержать [разделяемый метод](../../../csharp/language-reference/keywords/partial-method.md).  Дополнительные сведения см. в разделе [Разделяемые классы и методы](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Модификаторы](../../../csharp/language-reference/keywords/modifiers.md)   
 [Введение в универсальные шаблоны](../../../csharp/programming-guide/generics/introduction-to-generics.md)