---
title: Запросы в LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: e6d4b5d1095deb80a866bb0e3821ea10578d7925
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933735"
---
# <a name="queries-in-linq-to-entities"></a>Запросы в LINQ to Entities
Запрос представляет собой выражение, извлекающее данные из источника данных. Запросы обычно выражаются на специализированном языке запросов, например SQL для реляционных баз данных и XQuery для XML. Поэтому разработчикам приходится учить новый язык запросов для каждого типа источника данных и формата данных, для которых выполняется запрос. Интегрированный в язык запрос (LINQ) предлагает упрощенную согласованную модель работы с данными для различных типов источников данных и различных форматов данных. Запросы LINQ всегда работают с программируемыми объектами.  
  
 Операция запроса LINQ состоит из трех действий: получение одного или нескольких источников данных, создание запроса и его выполнение.  
  
 К источникам данных, реализующим общий интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>, можно выполнять запрос с помощью LINQ. Экземпляры универсального <xref:System.Data.Objects.ObjectQuery%601> класса, реализующего универсальный <xref:System.Linq.IQueryable%601> интерфейс, служат источником данных для запросов LINQ to Entities. Универсальный класс <xref:System.Data.Objects.ObjectQuery%601> представляет запрос, который возвращает коллекцию, включающую ноль или более типизированных объектов. Можно также разрешить компилятору выводить тип сущности с помощью C# ключевого слова `var` (Dim в Visual Basic).  
  
 В запросе указываются данные, которые необходимо получить из источника данных. В запросе можно также указать, как следует сортировать, группировать и формировать возвращаемую информацию. В LINQ запрос хранится в переменной. Если запрос возвращает последовательность значений, то переменная запроса должна иметь тип данных, который может быть запрошен. Эта переменная запроса не выполняет никаких действий и не возвращает данные. Она только хранит информацию о запросе. После создания запроса его необходимо выполнить, чтобы получить данные.  
  
## <a name="query-syntax"></a>Синтаксис запроса  
 Создание запросов LINQ to Entities может производиться с использованием синтаксиса выражений запросов или синтаксиса запросов на основе методов. Синтаксис выражений запросов впервые пойдет C# в 3,0 и Visual Basic 9,0. Он состоит из набора предложений, написанных в декларативном синтаксисе, аналогичном TRANSACT-SQL или XQuery. Однако .NET Framework среды CLR не может считать сам синтаксис выражения запроса. Таким образом, во время компиляции выражения запроса преобразуются в то, что понятно CLR - вызовы методов. Эти методы называются стандартными *операторами запросов*. Разработчик может вызывать их напрямую, используя синтаксис методов вместо синтаксиса запроса. Дополнительные сведения см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](../../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Синтаксис выражений запросов  
 Выражения запроса используют декларативный синтаксис запроса. Этот синтаксис позволяет разработчикам писать запросы на высокоуровневом языке, по формату напоминающем Transact-SQL. С помощью синтаксиса выражения запроса можно выполнять даже сложную фильтрацию, упорядочение и группирование операций в источнике данных с помощью минимального программного кода. Дополнительные сведения об [основных операциях запросов (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Примеры, показывающие применение синтаксиса выражения запросов, см. в следующих разделах.  
  
- [Примеры синтаксиса выражений запросов: Отображения](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
- [Примеры синтаксиса выражений запросов: Записей](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
- [Примеры синтаксиса выражений запросов: Упорядочение](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
- [Примеры синтаксиса выражений запросов: Агрегатные операторы](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
- [Примеры синтаксиса выражений запросов: Секционирования](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
- [Примеры синтаксиса выражений запросов: Операторы Join](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
- [Примеры синтаксиса выражений запросов: Операторы элементов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
- [Примеры синтаксиса выражений запросов: Группа](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
- [Примеры синтаксиса выражений запросов: Навигация по связям](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Синтаксис запросов, основанных на методе  
 Другим способом составления LINQ to Entities запросов является использование запросов на основе методов. Синтаксис запросов на основе методов представляет собой последовательность прямых вызовов методов операторов LINQ, передавая лямбда-выражения в качестве параметров. Дополнительные сведения см. в разделе [Лямбда-выражения](../../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Примеры, показывающие применение синтаксиса на основе методов, см. в следующих разделах.  
  
- [Примеры синтаксиса запросов на основе методов: Отображения](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
- [Примеры синтаксиса запросов на основе методов: Записей](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
- [Примеры синтаксиса запросов на основе методов: Упорядочение](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
- [Примеры синтаксиса запросов на основе методов: Агрегатные операторы](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Примеры синтаксиса запросов на основе методов: Секционирования](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
- [Примеры синтаксиса запросов на основе методов: Образовывать](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
- [Примеры синтаксиса запросов на основе методов: Операторы Join](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
- [Примеры синтаксиса запросов на основе методов: Операторы элементов](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
- [Примеры синтаксиса запросов на основе методов: Группа](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
- [Примеры синтаксиса запросов на основе методов: Навигация по связям](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>См. также

- [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
- [Приступая к работе с LINQ в C#](../../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Приступая к работе с LINQ в Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Entity Framework параметров слияния и скомпилированных запросов](https://go.microsoft.com/fwlink/?LinkId=199591)
