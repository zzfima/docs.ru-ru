---
title: "Оператор ?? (справочник по C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "??_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "?? - оператор [C#]"
  - "объединенный оператор [C#]"
  - "условное AND - оператор (&&) [C#]"
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# Оператор ?? (справочник по C#)
Оператор `??` называется оператором объединения со значением NULL.  Он возвращает левый операнд, если этот операнд не имеет значение NULL; в противном случае возвращается правый операнд.  
  
## Заметки  
 Тип, допускающий значение NULL, может представлять значение из домена типа или иметь неопределенное значение \(в последнем случае значение равно NULL\).  Синтаксические возможности оператора `??` можно использовать для возврата соответствующего значения \(правого операнда\), если тип левого операнда допускает значение NULL и левый операнд имеет значение NULL.  Если без использования оператора `??` попытаться присвоить тип, допускающий значение NULL, типу, не допускающему такое значение, то во время компиляции появится ошибка.  Если используется приведение типов и допускающий значение NULL тип в данный момент не определен, будет создано исключение `InvalidOperationException`.  
  
 Дополнительные сведения см. в разделе [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md).  
  
 Результат выполнения оператора ?? не считается константой, даже если оба его аргумента являются константами.  
  
## Пример  
 [!code-cs[csRefOperators#53](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#53)]  
  
## См. также  
 [Справочник по C\#](../../../csharp/language-reference/index.md)   
 [Руководство по программированию на C\#](../../../csharp/programming-guide/index.md)   
 [Операторы C\#](../../../csharp/language-reference/operators/index.md)   
 [Типы, допускающие значения NULL](../../../csharp/programming-guide/nullable-types/index.md)   
 [What Exactly Does 'Lifted' mean?](http://go.microsoft.com/fwlink/?LinkID=112382)