---
title: "Ограничение new (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "new constraint - ключевое слово [C#]"
ms.assetid: 58850b64-cb97-4136-be50-1f3bc7fc1da9
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Ограничение new (Справочник по C#)
Ограничение `new` указывает, что аргумент любого типа в объявлении общего класса должен иметь открытый конструктор без параметров.  Использовать ограничение new можно только в том случае, если тип не является абстрактным.  
  
## Пример  
 Ограничение `new` применяется к параметру типа, когда общий класс создает новые экземпляры этого типа, как показано в следующем примере.  
  
 [!code-cs[csrefKeywordsOperator#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_1.cs)]  
  
## Пример  
 При использовании ограничения `new()` с другими ограничениями его нужно указывать последним.  
  
 [!code-cs[csrefKeywordsOperator#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-constraint_2.cs)]  
  
 Дополнительные сведения см. в разделе [Ограничения параметров типа](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md).  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 <xref:System.Collections.Generic>   
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Ключевые слова операторов](../../../csharp/language-reference/keywords/operator-keywords.md)   
 [Универсальные шаблоны](../../../csharp/programming-guide/generics/index.md)