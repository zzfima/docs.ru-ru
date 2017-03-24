---
title: "Оператор (ссылка C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "[]_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "оператор индекса [C#]"
  - "квадратные скобки [ ] - оператор [C#]"
  - "[] - оператор [C#]"
  - "оператор индексирования [C#]"
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# Оператор (ссылка C#)
Квадратные скобки \(`[]`\) используются для массивов, индексаторов и атрибутов.  Кроме того, они могут использоваться с указателями.  
  
## Заметки  
 Тип массива указывается перед оператором `[]`:  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_1.cs)]  
  
 Для доступа к элементу массива его индекс необходимо заключить в скобки:  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_2.cs)]  
  
 Если индекс массива выходит за границы диапазона, происходит вызов исключения.  
  
 Перегрузка оператора индексирования массива невозможна; однако типы могут определять индексаторы и свойства, принимающие один или более параметров.  Параметры индексатора заключаются в квадратные скобки, как и индексы массива, но, в отличие от индексов массива, которые должны быть целочисленными, эти параметры могут быть любого типа.  
  
 Например, в платформе .NET Framework определен тип `Hashtable`, связывающий ключи и значения произвольного типа.  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_3.cs)]  
  
 Также квадратные скобки используются для определения [Атрибуты](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md):  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_4.cs)]  
  
 Квадратные скобки можно использовать для создания индекса из указателя.  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/CSharp/index-operator_5.cs)]  
  
 Проверка границ не выполняется.  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [Массивы](../../../csharp/programming-guide/arrays/index.md)   
 [Индексаторы](../../../csharp/programming-guide/indexers/index.md)   
 [небезопасное](../../../csharp/language-reference/keywords/unsafe.md)   
 [Оператор fixed](../../../csharp/language-reference/keywords/fixed-statement.md)