---
title: Как выполнить Руководство по программированию на C#. Использование лямбда-выражений в запросах
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [C#], in LINQ
ms.assetid: 3cac4d25-d11f-4abd-9e7c-0f02e97ae06d
ms.openlocfilehash: 9b8adfde95cd2122136cb75e97b4113ee1d80cf9
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238810"
---
# <a name="how-to-use-lambda-expressions-in-a-query-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Использование лямбда-выражений в запросах
Использовать лямбда-выражения непосредственно в синтаксисе запросов нельзя, однако их включают в вызовы методов, а те, в свою очередь, могут содержаться в выражениях запросов. Фактически некоторые операции запросов могут быть выражены только в синтаксисе методов. Дополнительные сведения о различиях между синтаксисом запросов и синтаксисом методов см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует, как можно применить лямбда-выражение в запросе, основанном на методе, с помощью стандартного оператора запросов <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>. Обратите внимание на то, что метод <xref:System.Linq.Enumerable.Where%2A> в этом примере имеет входной параметр с типом делегата <xref:System.Func%601>, а этот делегат принимает на вход целое число и возвращает логическое значение. Лямбда-выражение может быть преобразовано в этот делегат. Если вы примените запрос [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], в котором используется метод <xref:System.Linq.Queryable.Where%2A?displayProperty=nameWithType>, параметр будет иметь тип `Expression<Func<int,bool>>`, но лямбда-выражение останется точно таким же. Дополнительные сведения о типах выражений см. в статье <xref:System.Linq.Expressions.Expression?displayProperty=nameWithType>.  
  
 [!code-csharp[csProgGuideLINQ#1](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_1.cs)]  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как использовать лямбда-выражение в вызове метода выражения запроса. Мы вынуждены использовать лямбда-выражения, поскольку синтаксис запросов не позволяет вызвать стандартный оператор запроса <xref:System.Linq.Enumerable.Sum%2A>.  
  
 Сначала запрос группирует учащихся по успеваемости, как задано в перечислении `GradeLevel`. Затем для каждой группы он добавляет итоговые оценки каждого учащегося. Для этого требуются две операции `Sum`. Внутренняя операция `Sum` вычисляет общий результат для каждого учащегося, а внешняя операция `Sum` рассчитывает промежуточный общий результат по всем учащимся в группе.  
  
 [!code-csharp[csProgGuideLINQ#2](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-lambda-expressions-in-a-query_2.cs)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить этот код, скопируйте и вставьте метод в `StudentClass`, описанный в практическом руководстве по [ созданию запроса коллекции объектов](../../../csharp/programming-guide/linq-query-expressions/how-to-query-a-collection-of-objects.md), и вызовите его из метода `Main`.  
  
## <a name="see-also"></a>См. также

- [Лямбда-выражения](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
- [Expression Trees (C#)](../concepts/expression-trees/index.md) (Деревья выражений (C#))  
