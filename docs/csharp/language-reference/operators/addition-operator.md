---
title: "Оператор + (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+ - оператор [C#]"
  - "оператор сложения [C#]"
  - "оператор объединения [C#]"
ms.assetid: 93e56486-bb42-43c1-bd43-60af11e64e67
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# Оператор + (справочник по C#)
Оператор `+` может функционировать как унарный или как бинарный оператор.  
  
## Заметки  
 Унарные операторы `+` предопределены для всех числовых типов.  Результатом использования унарного оператора `+` для числового типа является просто значение операнда.  
  
 Бинарные операторы `+` предопределены для числовых и строковых типов.  Для числовых типов оператор "\+" вычисляет сумму двух его операндов.  Если один или оба операнда имеют строковый тип, оператор "\+" соединяет строковые представления операндов.  
  
 Для типов делегатов также используется бинарный оператор `+`, который выполняет соединение делегатов.  
  
 Пользовательские типы могут вызвать перегрузку унарного оператора `+` и бинарного `+` операторов.  Операции над целыми типами обычно разрешены в перечислениях.  Дополнительные сведения см. в разделе [оператор](../../../csharp/language-reference/keywords/operator.md).  
  
## Пример  
 [!code-cs[csRefOperators#28](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#28)]  
  
## Спецификация языка C\#  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [оператор](../../../csharp/language-reference/keywords/operator.md)