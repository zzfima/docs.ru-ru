---
title: "Добавление DataTable в DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 556d29a3-8fc9-4e38-b3ee-c188f7e7b155
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Добавление DataTable в DataSet
ADO.NET позволяет создавать объекты <xref:System.Data.DataTable> и добавлять их к существующему <xref:System.Data.DataSet>.  Можно задать данные ограничения для <xref:System.Data.DataTable>, используя свойства <xref:System.Data.DataTable.PrimaryKey%2A> и <xref:System.Data.DataColumn.Unique%2A>.  
  
## Пример  
 Следующий пример показывает, как создать объект <xref:System.Data.DataSet>, добавить новый объект <xref:System.Data.DataTable> к <xref:System.Data.DataSet>, а затем добавить к таблице три объекта <xref:System.Data.DataColumn>.  В конце код задает один столбец в качестве столбца первичного ключа.  
  
 [!code-csharp[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableAdd#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableAdd/VB/source.vb#1)]  
  
## Учет регистра  
 В <xref:System.Data.DataSet> могут существовать две или несколько таблиц или связей, имеющие одинаковые имена, которые, тем не менее, состоят из символов с разными регистрами.  В таких случаях ссылки по имени на таблицы и связи задаются с учетом регистра.  Например, если <xref:System.Data.DataSet> **dataSet** содержит таблицы **Table1** и **table1**, ссылка на таблицу по имени **Table1** выглядит как **dataSet.Tables\["Table1"\]**, а на **table1** \- как **dataSet.Tables\["table1"\]**.  Попытка сослаться на любую из таблиц как на **dataSet.Tables\["TABLE1"\]** вызывает исключение.  
  
 Это правило учета регистра не применяется, если только одна таблица или связь имеет какое\-то определенное имя.  Например, если набор данных <xref:System.Data.DataSet> содержит только таблицу **Table1**, можно сослаться на нее, используя формат **dataSet.Tables\["TABLE1"\]**.  
  
> [!NOTE]
>  Указанное правило применяется без учета значения свойства <xref:System.Data.DataSet.CaseSensitive%2A> объекта <xref:System.Data.DataSet>.  Свойство <xref:System.Data.DataSet.CaseSensitive%2A> применяется к данным в <xref:System.Data.DataSet> и затрагивает сортировку, поиск, фильтрацию, предписание ограничений и т. д.  
  
## Поддержка пространства имен  
 В версиях ADO.NET, выпущенных до версии 2.0, две таблицы не могли иметь одинаковое имя, даже если находились в разных пространствах имен.  Это ограничение было снято в ADO.NET 2.0.  Набор данных <xref:System.Data.DataSet> может содержать две таблицы, имеющие одинаковое значение свойства <xref:System.Data.DataTable.TableName%2A>, но различные значения свойства <xref:System.Data.DataTable.Namespace%2A>.  
  
## См. также  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)