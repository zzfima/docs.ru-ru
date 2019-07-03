---
title: LINQ to Entities
ms.date: 03/30/2017
ms.assetid: 641f9b68-9046-47a1-abb0-1c8eaeda0e2d
ms.openlocfilehash: 8a69d74966b99d78b4a7addaa4323d61d82ce8d5
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539777"
---
# <a name="linq-to-entities"></a>LINQ to Entities
LINQ to Entities обеспечивает поддержку LINQ при запросах к сущностям. Компонент позволяет разработчикам писать запросы к концептуальной модели Entity Framework на языке Visual Basic или Visual C#. Запросы к платформе Entity Framework представляются в виде дерева команд запроса, выполняемого на контексте объектов. Технология LINQ to Entities преобразует запросы Language-Integrated Queries (LINQ) в запросы в виде дерева команд, выполняет эти запросы на платформе Entity Framework и возвращает объекты, которые могут использоваться как платформой Entity Framework, так и технологией LINQ. Далее описывается процесс создания и исполнения запроса в технологии LINQ to Entities.  
  
1. Создайте экземпляр запроса <xref:System.Data.Objects.ObjectQuery%601> на основе объектного контекста <xref:System.Data.Objects.ObjectContext>.  
  
2. Создайте запрос по технологии LINQ to Entities на языке C# или Visual Basic с помощью экземпляра <xref:System.Data.Objects.ObjectQuery%601>.  
  
3. Преобразуйте стандартные операторы и выражения запросов LINQ в деревья команд.  
  
4. Выполните запрос в виде дерева команд применительно к источнику данных. Все исключения, возникшие в источнике данных во время выполнения, передаются непосредственно клиенту.  
  
5. Верните результаты запроса обратно клиенту.  
  
## <a name="constructing-an-objectquery-instance"></a>Создание экземпляра ObjectQuery  
 Универсальный класс <xref:System.Data.Objects.ObjectQuery%601> представляет собой запрос, возвращающий коллекцию, содержащую ноль, одну или несколько типизированных сущностей. Как правило, запрос объектов создается на основе существующего контекста объекта, а не вручную, и всегда принадлежит этому контексту объекта. В этом контексте содержится информация о соединении и метаданных, необходимая для создания и выполнения запроса. Универсальный класс <xref:System.Data.Objects.ObjectQuery%601> реализует общий интерфейс <xref:System.Linq.IQueryable%601>, методы построителя которого позволяют пошагово строить запросы LINQ. Можно также разрешить компилятору вывести тип сущностей при помощи ключевого слова C# `var` (`Dim` в Visual Basic, если разрешено выведение локальных типов).  
  
## <a name="composing-the-queries"></a>Составление запросов  
 Экземпляры универсального класса <xref:System.Data.Objects.ObjectQuery%601>, реализующего общий интерфейс <xref:System.Linq.IQueryable%601>, служат источниками данных для запросов по технологии LINQ to Entities. В запросе точно указывается, какие данные надо получить из источника. В запросе можно также указать, как следует сортировать, группировать и формировать возвращаемую информацию. В LINQ запрос хранится в переменной. Эта переменная запроса не выполняет никаких действий и не возвращает данные. Она только хранит информацию о запросе. После создания запроса его необходимо выполнить, чтобы получить данные.  
  
 Создание запросов LINQ to Entities может производиться с использованием синтаксиса выражений запросов или синтаксиса запросов на основе методов. Синтаксические конструкции выражения запроса и запроса на основе методов впервые появились в версиях языков C# 3.0 и Visual Basic 9.0.  
  
 Дополнительные сведения см. в разделе [запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md).  
  
## <a name="query-conversion"></a>Преобразование запросов  
 Для выполнения запроса в технологии LINQ to Entities на платформе Entity Framework запрос LINQ нужно преобразовать в дерево команд, которое можно выполнить на платформе Entity Framework.  
  
 Запросы LINQ to Entities состоят из стандартных операторов запросов LINQ (такие как <xref:System.Linq.Queryable.Select%2A>, <xref:System.Linq.Queryable.Where%2A>, и <xref:System.Linq.Queryable.GroupBy%2A>) и выражений (x > 10, Contact.LastName и т. д.). Операторы LINQ не определяются классом, а являются методами класса. В LINQ выражения могут содержать любые конструкции, допустимые для типов в пределах пространства имен <xref:System.Linq.Expressions>, а по расширению - любые конструкции, которые могут быть представлены лямбда-функциями. Это надмножество выражений, допустимых для платформы Entity Framework, множество которых по определению ограничено допустимыми операциями над базой данных и поддерживается посредством <xref:System.Data.Objects.ObjectQuery%601>.  
  
 На платформе Entity Framework и операторы, и выражения представляются одной иерархией типов, которая затем помещается в дерево команд. Дерево команд используется платформой Entity Framework для выполнения запроса. Если запрос LINQ не удается выразить в виде дерева команд, при преобразовании запроса будет создано исключение. Преобразование запросов LINQ to Entities включает два промежуточных преобразования - стандартных операторов запросов и выражений.  
  
 Для ряда стандартных операторов запроса LINQ не существует допустимых эквивалентов в технологии LINQ to Entities. Попытки использования этих операторов приведут к возникновению исключения в процессе перевода запроса. Список поддерживаемых операторы LINQ to Entities, см. в разделе [поддерживаемые и неподдерживаемые методы LINQ (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md).  
  
 Дополнительные сведения об использовании стандартных операторов запросов в LINQ to Entities см. в разделе [стандартных операторов запросов в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md).  
  
 Как правило, выражения технологии LINQ to Entities вычисляются на сервере, поэтому нельзя ожидать, что поведение выражений будет соответствовать семантике среды CLR. Дополнительные сведения см. в разделе [выражения в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md).  
  
 Сведения о том, как вызовы методов CLR сопоставляются с каноническими функциями в источнике данных, см. в разделе [методов CLR с сопоставление канонической функции](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md).  
  
 Сведения о том, как вызов каноническую, базы данных и пользовательские функции из LINQ в запросы сущностей, см. в разделе [вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md).  
  
## <a name="query-execution"></a>Выполнение запроса  
 После создания пользователем запроса LINQ он преобразуется в представление, совместимое с Entity Framework (в виде дерева команд), которое затем выполняется для источника данных. Во время выполнения запроса все выражения (или компоненты) этого запроса вычисляются на клиенте либо на сервере. Это относится и к выражениям, используемым для материализации результатов и для проекции сущностей. Дополнительные сведения см. в разделе [выполнения запроса](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md). Сведения о том, как повысить производительность путем компилирования запроса один раз и затем выполнить его несколько раз с разными параметрами см. в разделе [компилированные запросы (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md).  
  
## <a name="materialization"></a>Материализация  
 Материализацией называется процесс возвращения результатов запроса клиенту в виде типов CLR. В LINQ to Entities результаты запроса никогда не возвращаются в виде записей данных. Для этого всегда используется базовый тип CLR, который был определен пользователем или платформой Entity Framework или создан компилятором (анонимный тип). Вся материализация объектов проводится платформой Entity Framework. Все ошибки, вызванные невозможностью сопоставления между платформой Entity Framework и средой CLR, вызовут создание исключений во время материализации объекта.  
  
 Результаты запроса обычно возвращаются в одной из следующих форм.  
  
- Коллекция, содержащая ноль или более типизированных объектов сущностей, либо проекция сложных типов, определенных в концептуальной модели.  
  
- Типы CLR, поддерживаемые [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)].  
  
- Встроенные коллекции.  
  
- Анонимные типы.  
  
 Дополнительные сведения см. в разделе [результаты запроса](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)  
  
 [Выражения в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)  
  
 [Вызов функций в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
  
 [Компилированные запросы (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/compiled-queries-linq-to-entities.md)  
  
 [Выполнение запроса](../../../../../../docs/framework/data/adonet/ef/language-reference/query-execution.md)  
  
 [Результаты запроса](../../../../../../docs/framework/data/adonet/ef/language-reference/query-results.md)  
  
 [Стандартные операторы запроса в запросах LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/standard-query-operators-in-linq-to-entities-queries.md)  
  
 [Сопоставление методов CLR с каноническими функциями](../../../../../../docs/framework/data/adonet/ef/language-reference/clr-method-to-canonical-function-mapping.md)  
  
 [Поддерживаемые и неподдерживаемые методы LINQ (LINQ to Entities)](../../../../../../docs/framework/data/adonet/ef/language-reference/supported-and-unsupported-linq-methods-linq-to-entities.md)  
  
 [Рекомендации и известные проблемы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)  
  
## <a name="see-also"></a>См. также

- [Рекомендации и известные проблемы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)
- [LINQ — C#](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ — Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/index.md)
- [LINQ и ADO.NET](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)
- [ADO.NET Entity Framework](../../../../../../docs/framework/data/adonet/ef/index.md)
