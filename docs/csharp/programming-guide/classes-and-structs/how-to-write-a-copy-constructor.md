---
title: "Практическое руководство. Создание конструктора копии (Руководство по программированию в C#) | Microsoft Docs"
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
  - "C# - язык, конструктор копии"
  - "конструктор копий [C#]"
ms.assetid: fba899b5-fc41-428e-a745-3ebdbf37990a
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Практическое руководство. Создание конструктора копии (Руководство по программированию в C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

В C\# не предусмотрен конструктор копии для объектов, однако его можно написать самостоятельно.  
  
## Пример  
 В следующем примере класс `Person` [](../../../csharp/language-reference/keywords/class.md "class (C# Reference)") определяет конструктор копии, который использует экземпляр `Person` в качестве аргумента.  Значения свойств аргумента присвоенные свойствам нового экземпляра `Person`.  Код содержит дополнительный конструктор копии, который отправляет свойства `Name` и `Age` экземпляра, который нужно скопировать конструктору экземпляра класса.  
  
 [!code-cs[csProgGuideObjects#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-write-a-copy-constructor_1.cs)]  
  
## См. также  
 <xref:System.ICloneable>   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Классы и структуры](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [Конструкторы](../../../csharp/programming-guide/classes-and-structs/constructors.md)   
 [Деструкторы](../../../csharp/programming-guide/classes-and-structs/destructors.md)