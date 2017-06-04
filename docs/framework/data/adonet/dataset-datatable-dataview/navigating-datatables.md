---
title: "Навигация в объектах DataTable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Навигация в объектах DataTable
Объект <xref:System.Data.DataTableReader> получает содержимое одного или нескольких объектов <xref:System.Data.DataTable> в виде одного или нескольких однопроходных результирующих наборов, доступных только для чтения.  
  
 Объект <xref:System.Data.DataTableReader> может содержать несколько результирующих наборов, если он создан методом <xref:System.Data.DataSet.CreateDataReader%2A>.  Если имеется несколько результирующих наборов, метод <xref:System.Data.DataTableReader.NextResult%2A> продвигает курсор к следующему результирующему набору.  Это однопроходной процесс.  Вернуться к предыдущему результирующему набору невозможно.  
  
## Пример  
 В следующем примере метод `TestConstructor` создает два экземпляра <xref:System.Data.DataTable> `` .  Чтобы продемонстрировать работу конструктора для класса <xref:System.Data.DataTableReader>, данный образец создает новый объект **DataTableReader** на основе массива, содержащего две таблицы **DataTables**, и выполняет простую операцию, выводя содержимое первых столбцов в окно консоли.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## См. также  
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)