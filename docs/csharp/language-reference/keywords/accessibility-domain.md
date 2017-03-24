---
title: "Область доступности (Справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "домен доступности [C#]"
ms.assetid: 8af779c1-275b-44be-a864-9edfbca71bcc
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Область доступности (Справочник по C#)
Область доступности члена определяет, в каких разделах программы может присутствовать ссылка на этот член.  Если член является вложенным членом другого типа, его область доступности определяется как [уровнем доступности](../../../csharp/language-reference/keywords/accessibility-levels.md) самого члена, так и доменом доступности типа, непосредственно содержащего вложенный тип.  
  
 Домен специальных возможностей типа верхнего уровня — это по крайней мере текст программы проекта в котором он объявлен.  Т.е. домен включает все исходные файлы данного проекта.  Домен доступности вложенного типа — это, по крайней мере, текст программы типа, в котором он объявлен.  Таким образом, доменом является тело типа, включающее все вложенные типы.  Домен доступности вложенного типа никогда не выходит за границы домена доступности содержащего его типа.  Эти принципы продемонстрированы в следующем примере.  
  
## Пример  
 Этот пример содержит тип верхнего уровня `T1` и два вложенных класса: `M1` и `M2`.  Классы содержат поля, имеющие различную объявленную доступность.  В методе `Main` после каждого оператора следует комментарий, указывающий домен доступности для каждого члена.  Обратите внимание, что операторы, ссылающиеся на недоступные члены, закомментированы.  Если необходимо просмотреть сообщения об ошибках, выдаваемые компилятором при попытке ссылки на недоступный член, удаляйте комментарии по одному.  
  
 [!code-cs[csrefKeywordsModifiers#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/accessibility-domain_1.cs)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Ключевые слова C\#](../../../csharp/language-reference/keywords/index.md)   
 [Модификаторы доступа](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [Уровни доступности](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [Ограничения на использование уровней доступности](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md)   
 [Модификаторы доступа](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [закрытый](../../../csharp/language-reference/keywords/private.md)   
 [защищенные](../../../csharp/language-reference/keywords/protected.md)   
 [внутренние](../../../csharp/language-reference/keywords/internal.md)