---
title: "value (Справочник по C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "value_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "value - ключевое слово [C#]"
ms.assetid: c99d6468-687f-4a46-89b4-a95e1b00bf6d
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# value (Справочник по C#)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Контекстно\-зависимое ключевое слово `value` используется для задания метода доступа в обычных объявлениях свойств.  Оно аналогично входному параметру метода.  Ключевое слово `value` ссылается на значение, которое клиентский код пытается присвоить свойству.  В следующем примере класс `MyDerivedClass` содержит свойство с именем `Name`, в котором используется параметр `value` для назначения новой строки резервному полю `name`.  С точки зрения клиентского кода данная операция выглядит как простое присвоение.  
  
 [!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/value_1.cs)]  
  
 Дополнительные сведения об использовании ключевого слова `value` см. в разделе [Свойства](../../../csharp/programming-guide/classes-and-structs/properties.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)