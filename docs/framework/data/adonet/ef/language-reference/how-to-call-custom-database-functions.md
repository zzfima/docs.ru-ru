---
title: "Как вызывать пользовательские функции базы данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Как вызывать пользовательские функции базы данных
В данном разделе описаны процедуры вызова пользовательских функций, определенных в базе данных, из запросов LINQ to Entities.  
  
 Функции базы данных, вызываемые в запросах LINQ to Entities, выполняются в базе данных.  При выполнении функций в базе данных может увеличиться производительность приложений.  
  
 Процедура, приведенная ниже, обеспечивает высокоуровневую структуру вызова пользовательской функции базы данных.  В следующем примере подробно описаны шаги данной процедуры.  
  
### Вызов пользовательских функций, определенных в базе данных.  
  
1.  Создайте пользовательскую функцию в базе данных.  
  
     Дополнительные сведения о создании пользовательских функций в SQL Server см. в разделе [CREATE FUNCTION \(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkID=139871).  
  
2.  Объявите функцию на языке SSDL в EDMX\-файле.  Имя функции должно совпадать с именем функции, объявленной в базе данных.  
  
     Для получения дополнительной информации см. [Function Element \(SSDL\)](http://msdn.microsoft.com/ru-ru/b60cfc3d-8b93-423e-8c99-b867256640a4).  
  
3.  Добавьте соответствующий метод к классу в коде приложения и примените <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> к этому методу. Обратите внимание, что параметры атрибута <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> и <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> представляют собой имя пространства имен концептуальной модели и имя функции концептуальной модели соответственно.  При разрешении имени функции для LINQ учитывается регистр.  
  
4.  Вызовите метод в запросе LINQ to Entities.  
  
## Пример  
 В следующем примере показываются процедуры вызова пользовательской функции базы данных из запроса LINQ to Entities.  В этом примере используется модель School.  Дополнительные сведения о модели School см. в разделах [Creating the School Sample Database](http://msdn.microsoft.com/ru-ru/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0) и [Generating the School .edmx File](http://msdn.microsoft.com/ru-ru/c48b3907-a8be-4fe6-884c-e95af1852758).  
  
 Следующий код добавляет функцию `AvgStudentGrade` в образец базы данных.  
  
> [!NOTE]
>  Шаги вызова пользовательской функции базы данных одинаковы, независимо от сервера базы данных.  Однако следующий код предназначен специально для создания функции в базе данных SQL Server.  Код для создания пользовательской функции на других серверах баз данных может отличаться.  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## Пример  
 Затем объявите функцию на языке SSDL в EDMX\-файле.  в следующем коде объявляется функция `AvgStudentGrade` на языке SSDL:  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## Пример  
 Теперь следует создать метод и сопоставить его с функцией, объявленной на языке SSDL.  Метод в следующем классе сопоставляется с функцией, определенной на языке SSDL \(выше\) с помощью <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.  При вызове этого метода в базе данных выполняется соответствующая функция.  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## Пример  
 Наконец, вызовите метод в запросе LINQ to Entities.  Следующий код отображает в консоли фамилии студентов и средние баллы:  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## См. также  
 [.edmx File Overview](http://msdn.microsoft.com/ru-ru/f4c8e7ce-1db6-417e-9759-15f8b55155d4)   
 [Запросы в LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)