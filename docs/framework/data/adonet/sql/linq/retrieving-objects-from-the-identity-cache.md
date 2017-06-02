---
title: "Получение объектов из кэша идентификации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96c13903-ccb6-4a0e-ab6a-8ca955ca314d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Получение объектов из кэша идентификации
В этом разделе описаны типы запросов LINQ to SQL, которые возвращают объект из кэша идентификаторов, управляемого <xref:System.Data.Linq.DataContext>.  
  
 В LINQ to SQL в качестве одного из способов управления объектами <xref:System.Data.Linq.DataContext> регистрируют идентификаторы объектов в кэше идентификаторов во время выполнения запросов.  В некоторых случаях LINQ to SQL пытается получить объект из кэша идентификаторов перед выполнением запроса в базе данных.  
  
 Обычно, чтобы запрос LINQ to SQL мог вернуть объект из кэша идентификаторов, запрос должен быть основан на первичном ключе объекта и должен возвращать одиночный объект.  В частности, запрос должен иметь одну из общих форм, представленных далее.  
  
> [!NOTE]
>  Предварительно скомпилированные запросы не возвращают объекты из кэша идентификаторов.  Дополнительные сведения о предварительно скомпилированных запросах см. в разделах <xref:System.Data.Linq.CompiledQuery> и [Как сохранять и повторно использовать запросы](../../../../../../docs/framework/data/adonet/sql/linq/how-to-store-and-reuse-queries.md).  
  
 Чтобы получить объект из кэша идентификаторов, запрос должен иметь одну из следующих общих форм.  
  
-   <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `)`  
  
-   <xref:System.Data.Linq.Table%601> `.Function1(` `predicate` `).Function2()`  
  
 В этих общих формах параметры `Function1`, `Function2` и `predicate` определяются следующим образом.  
  
 Параметр `Function1` может иметь любое из следующих значений.  
  
-   <xref:System.Linq.Queryable.Where%2A>  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 Параметр `Function2` может иметь любое из следующих значений.  
  
-   <xref:System.Linq.Queryable.First%2A>  
  
-   <xref:System.Linq.Queryable.FirstOrDefault%2A>  
  
-   <xref:System.Linq.Queryable.Single%2A>  
  
-   <xref:System.Linq.Queryable.SingleOrDefault%2A>  
  
 Параметр `predicate` должен быть выражением, в котором свойство первичного ключа объекта устанавливается в постоянное значение.  Если первичный ключ определен в нескольких свойствах объекта, то в каждом свойстве должно быть задано постоянное значение.  Далее представлены примеры формы, которую должен принимать параметр `predicate`.  
  
-   `c => c.PK == constant_value`  
  
-   `c => c.PK1 == constant_value1 && c=> c.PK2 == constant_value2`  
  
## Пример  
 В следующем коде приводятся примеры типов запросов LINQ to SQL, которые получают объект из кэша идентификаторов.  
  
 [!code-csharp[L2S_QueryCache#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/l2s_querycache/cs/program.cs#1)]
 [!code-vb[L2S_QueryCache#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/l2s_querycache/vb/module1.vb#1)]  
  
## См. также  
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [Идентификация объекта](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)   
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Идентификация объекта](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)