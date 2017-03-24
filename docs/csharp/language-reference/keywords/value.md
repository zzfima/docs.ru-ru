---
title: "value (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "value_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "value - ключевое слово [C#]"
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# value (Справочник по C#)
Контекстно\-зависимое ключевое слово `value` используется для задания метода доступа в обычных объявлениях свойств.  Оно аналогично входному параметру метода.  Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.  В следующем примере класс `MyDerivedClass` содержит свойство с именем `Name`, в котором используется параметр `value` для назначения новой строки резервному полю `name`.  С точки зрения клиентского кода данная операция выглядит как простое присвоение.  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)