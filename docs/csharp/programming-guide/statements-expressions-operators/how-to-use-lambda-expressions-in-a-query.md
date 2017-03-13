---
title: "Практическое руководство. Использование лямбда-выражений в запросах (Руководство по программированию на C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "лямбда-выражения [C#], в LINQ"
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# Практическое руководство. Использование лямбда-выражений в запросах (Руководство по программированию на C#)
Лямбда\-выражения не используются непосредственно в синтаксисе запросов, но их можно использовать в вызовах методов, а выражения запросов могут содержать вызовы методов.  Некоторые операции запросов могут быть выражены только с помощью синтаксиса методов.  Дополнительные сведения о различиях между синтаксисом запросов и синтаксисом методов см. в разделе [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## Пример  
 В следующем примере показано использование лямбда\-выражения в запросе на основе метода с помощью стандартного оператора запроса <xref:System.Linq.Enumerable.Where%2A?displayProperty=fullName>.  Обратите внимание, что в этом примере метод <xref:System.Linq.Enumerable.Where%2A> имеет входной параметр делегата типа <xref:System.Func%601>, а этот делегат получает на вход целое число и возвращает логическое значение.  Лямбда\-выражение может быть преобразовано в тип этого делегата.  Если бы это был запрос [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] с использованием метода <xref:System.Linq.Queryable.Where%2A?displayProperty=fullName>, то следовало бы использовать параметр `Expression<Func\<int,bool>>`, но лямбда\-выражение было бы точно таким же.  Дополнительные сведения о типах выражений см. в разделе <xref:System.Linq.Expressions.Expression?displayProperty=fullName>.  
  
 [!code-cs[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## Пример  
 В следующем примере показано использование лямбда\-выражения в вызове метода в выражении запроса.  Лямбда\-выражение здесь необходимо использовать, поскольку стандартный оператор запроса <xref:System.Linq.Enumerable.Sum%2A> нельзя вызвать с помощью синтаксиса запроса.  
  
 Запрос сначала группирует учащихся их уровню согласно перечислению `GradeLevel`.  Затем для каждой группы добавляются итоговые оценки для каждого учащегося.  Для этого требуются две операции `Sum`.  Внутренняя операция `Sum` вычисляет итоговую оценку каждого студента, а внешняя операция `Sum` вычисляет общую оценку для всех учащихся в группе.  
  
 [!code-cs[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## Компиляция кода  
 Чтобы запустить этот код, вставьте метод его в класс `StudentClass` в [Практическое руководство. Запрос коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md) и вызовите его из метода `Main`.  
  
## См. также  
 [Лямбда\-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [Деревья выражений](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)