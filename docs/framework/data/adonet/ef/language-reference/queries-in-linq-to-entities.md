---
title: "Запросы в LINQ to Entities | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Запросы в LINQ to Entities
Запрос представляет собой выражение, извлекающее данные из источника данных.  Запросы обычно выражаются на специализированном языке запросов, например SQL для реляционных баз данных и XQuery для XML.  Поэтому разработчикам приходится учить новый язык запросов для каждого типа источника данных и формата данных, для которых выполняется запрос.  Интегрированный в язык запрос \(LINQ\) предлагает упрощенную согласованную модель работы с данными для различных типов источников данных и различных форматов данных.  Запросы LINQ всегда работают с программируемыми объектами.  
  
 Операция запроса LINQ состоит из трех действий: получение одного или нескольких источников данных, создание запроса и его выполнение.  
  
 К источникам данных, реализующим общий интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Linq.IQueryable%601>, можно выполнять запрос с помощью LINQ.  Экземпляры универсального класса <xref:System.Data.Objects.ObjectQuery%601>, реализующего общий интерфейс <xref:System.Linq.IQueryable%601>, служат источником данных для запросов [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)].  Универсальный класс <xref:System.Data.Objects.ObjectQuery%601> представляет запрос, который возвращает коллекцию, включающую ноль или более типизированных объектов.  Можно также разрешить компилятору вывести тип сущности при помощи ключевого слова C\# `var` \(Dim в Visual Basic\).  
  
 В запросе указываются данные, которые необходимо получить из источника данных.  В запросе можно также указать, как следует сортировать, группировать и формировать возвращаемую информацию.  В LINQ запрос хранится в переменной.  Если запрос возвращает последовательность значений, то переменная запроса должна иметь тип данных, который может быть запрошен.  Эта переменная запроса не выполняет никаких действий и не возвращает данные. Она только хранит информацию о запросе.  После создания запроса его необходимо выполнить, чтобы получить данные.  
  
## Синтаксис запроса  
 Запросы [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] могут быть составлены одним из двух способов: с использованием синтаксиса выражения запроса и с использованием синтаксиса запросов на основе методов.  Синтаксис выражения запроса появился в языках C\# 3.0 и Visual Basic 9.0 и состоит из набора предложений, написанных в декларативном стиле, как в языках Transact\-SQL или XQuery.  Тем не менее среда CLR платформы [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] не может прочитать выражение запроса сама.  Таким образом, во время компиляции выражения запроса преобразуются в то, что понятно CLR \- вызовы методов.  Эти методы называются *стандартными операторами запроса*.  Разработчик может вызывать их напрямую, используя синтаксис методов вместо синтаксиса запроса. Дополнительные сведения см. в разделе [Query Syntax and Method Syntax in LINQ](../Topic/Query%20Syntax%20and%20Method%20Syntax%20in%20LINQ%20\(C%23\).md).  
  
### Синтаксис выражений запросов  
 Выражения запроса используют декларативный синтаксис запроса.  Этот синтаксис позволяет разработчикам писать запросы на высокоуровневом языке, по формату напоминающем Transact\-SQL.  С помощью синтаксиса выражения запроса можно выполнять даже сложную фильтрацию, упорядочение и группирование операций в источнике данных с помощью минимального программного кода.  Дополнительные сведения см. в разделе [Основные операции запроса \(Visual Basic\)](../Topic/Basic%20Query%20Operations%20\(Visual%20Basic\).md).  Примеры, показывающие применение синтаксиса выражения запросов, см. в следующих разделах.  
  
-   [Примеры синтаксиса выражений запросов: проекция](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-projection.md)  
  
-   [Примеры синтаксиса выражений запросов: фильтрация](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-filtering.md)  
  
-   [Примеры синтаксиса выражений запросов: упорядочение](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-ordering.md)  
  
-   [Примеры синтаксиса выражений запросов: агрегатные операторы](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-aggregate-operators.md)  
  
-   [Примеры синтаксиса выражений запросов: секционирование](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-partitioning.md)  
  
-   [Примеры синтаксиса выражений запросов: операторы соединения](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-join-operators.md)  
  
-   [Примеры синтаксиса выражений запросов: операторы работы с элементами \(язык LINQ to Entities\)](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-element-operators.md)  
  
-   [Примеры синтаксиса выражений запросов: группирование](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-grouping.md)  
  
-   [Примеры синтаксиса выражений запросов: навигация по связям](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expression-syntax-examples-navigating-relationships.md)  
  
### Синтаксис запросов, основанных на методе  
 Другим способом создания запросов [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] является синтаксис запроса, основанного на методе.  Он представляет собой последовательность непосредственных вызовов методов операторов LINQ, передающих лямбда\-выражения в качестве параметров.  Дополнительные сведения см. в разделе [Лямбда\-выражения](../Topic/Lambda%20Expressions%20\(C%23%20Programming%20Guide\).md).  Примеры, показывающие применение синтаксиса на основе методов, см. в следующих разделах.  
  
-   [Примеры синтаксиса запросов на основе методов: проекция](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-projection.md)  
  
-   [Примеры синтаксиса запросов на основе методов: фильтрация](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-filtering.md)  
  
-   [Примеры синтаксиса запросов на основе методов: упорядочение](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-ordering.md)  
  
-   [Примеры синтаксиса запросов на основе методов: статистические операторы](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-aggregate-operators.md)  
  
-   [Примеры синтаксиса запросов на основе методов: секционирование](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-partitioning.md)  
  
-   [Примеры синтаксиса запросов на основе методов: преобразование](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-conversion.md)  
  
-   [Примеры синтаксиса запросов на основе методов: операторы соединения](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-join-operators.md)  
  
-   [Примеры синтаксиса запросов на основе методов: операторы работы с элементами](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-element-operators.md)  
  
-   [Примеры синтаксиса запросов на основе методов: группирование](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-grouping.md)  
  
-   [Примеры синтаксиса запросов на основе методов: навигация по связям](../../../../../../docs/framework/data/adonet/ef/language-reference/method-based-query-syntax-examples-navigating-relationships.md)  
  
## См. также  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)   
 [Getting Started with LINQ in C\#](../Topic/Getting%20Started%20with%20LINQ%20in%20C%23.md)   
 [Getting Started with LINQ in Visual Basic](../Topic/Getting%20Started%20with%20LINQ%20in%20Visual%20Basic.md)   
 [Параметры слияния Entity Framework и скомпилированные запросы](http://go.microsoft.com/fwlink/?LinkId=199591)