---
title: "Запросы в LINQ to Entities"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 220416aa4e282cb342ee6080d9040f9f4818fbf0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="queries-in-linq-to-entities"></a>Запросы в LINQ to Entities
Запрос представляет собой выражение, извлекающее данные из источника данных. Запросы обычно выражаются на специализированном языке запросов, например SQL для реляционных баз данных и XQuery для XML. Поэтому разработчикам приходится учить новый язык запросов для каждого типа источника данных и формата данных, для которых выполняется запрос. Интегрированный в язык запрос (LINQ) предлагает упрощенную согласованную модель работы с данными для различных типов источников данных и различных форматов данных. Запросы LINQ всегда работают с программируемыми объектами.  
  
 Операция запроса LINQ состоит из трех действий: получение одного или нескольких источников данных, создание запроса и его выполнение.  
  
 К источникам данных, реализующим общий интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>, можно выполнять запрос с помощью LINQ. Экземпляры универсального <xref:System.Data.Objects.ObjectQuery%601> класс, который реализует универсальный <xref:System.Linq.IQueryable%601> интерфейсом, выступать в качестве источника данных для [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] запросов. Универсальный класс <xref:System.Data.Objects.ObjectQuery%601> представляет запрос, который возвращает коллекцию, включающую ноль или более типизированных объектов. Можно также разрешить компилятору вывести тип сущности, с помощью ключевого слова C# `var` (Dim в Visual Basic).  
  
 В запросе указываются данные, которые необходимо получить из источника данных. В запросе можно также указать, как следует сортировать, группировать и формировать возвращаемую информацию. В LINQ запрос хранится в переменной. Если запрос возвращает последовательность значений, то переменная запроса должна иметь тип данных, который может быть запрошен. Эта переменная запроса не выполняет никаких действий и не возвращает данные. Она только хранит информацию о запросе. После создания запроса его необходимо выполнить, чтобы получить данные.  
  
## <a name="query-syntax"></a>Синтаксис запроса  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]запросы могут создаваться в два разных синтаксиса: синтаксис выражений запросов и синтаксис запросов на основе методов. Синтаксис выражения запроса в C# 3.0 и Visual Basic 9.0 и состоит из набора предложений, написанных в декларативном стиле аналогично Transact-SQL или XQuery. Тем не менее среда CLR платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] не может прочитать выражение запроса сама. Таким образом, во время компиляции выражения запроса преобразуются в то, что понятно CLR - вызовы методов. Эти методы называются *стандартных операторов запроса*. Разработчик может вызывать их напрямую, используя синтаксис методов вместо синтаксиса запроса. Дополнительные сведения см. в разделе [Синтаксис запросов и синтаксис методов в LINQ](~/docs/csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Синтаксис выражений запросов  
 Выражения запроса используют декларативный синтаксис запроса. Этот синтаксис позволяет разработчикам писать запросы на высокоуровневом языке, по формату напоминающем Transact-SQL. С помощью синтаксиса выражения запроса можно выполнять даже сложную фильтрацию, упорядочение и группирование операций в источнике данных с помощью минимального программного кода. Для получения дополнительной информации [основные операции запроса (Visual Basic)](~/docs/visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Примеры, показывающие применение синтаксиса выражения запросов, см. в следующих разделах.  
  
-   [Примеры синтаксиса выражений запроса: проекции](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
-   [Примеры синтаксиса выражений запроса: фильтрация](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
-   [Примеры синтаксиса выражений запроса: упорядочение](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
-   [Примеры синтаксиса выражений запроса: Операторы статистических выражений](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [Примеры синтаксиса выражений запроса: секционирование](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
-   [Примеры синтаксиса выражений запроса: Операторы соединения](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
-   [Примеры синтаксиса выражений запроса: Операторы элементов](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
-   [Примеры синтаксиса выражений запроса: группирование](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
-   [Примеры синтаксиса выражений запроса: Отношения навигации](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Синтаксис запросов, основанных на методе  
 Другим способом создания запросов [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] является синтаксис запроса, основанного на методе. Запросов на основе методов представляет собой последовательность непосредственных вызовов методов операторов LINQ, передающих лямбда-выражения в качестве параметров. Дополнительные сведения см. в разделе [Лямбда-выражения](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Примеры, показывающие применение синтаксиса на основе методов, см. в следующих разделах.  
  
-   [Примеры синтаксиса запросов на основе методов: проекции](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
-   [Примеры синтаксиса запросов на основе методов: фильтрация](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
-   [Примеры синтаксиса запросов на основе методов: упорядочение](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
-   [Примеры синтаксиса запросов на основе методов: Операторы статистических выражений](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [Примеры синтаксиса запросов на основе методов: секционирование](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
-   [Примеры синтаксиса запросов на основе методов: преобразование](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
-   [Примеры синтаксиса запросов на основе методов: Операторы соединения](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
-   [Примеры синтаксиса запросов на основе методов: Операторы элементов](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
-   [Примеры синтаксиса запросов на основе методов: группирование](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
-   [Примеры синтаксиса запросов на основе методов: Навигационные связи](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>См. также  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)  
 [Приступая к работе с LINQ в C#](~/docs/csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Приступая к работе с LINQ в Visual Basic](~/docs/visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Параметры слияния Entity Framework и скомпилированные запросы](http://go.microsoft.com/fwlink/?LinkId=199591)
