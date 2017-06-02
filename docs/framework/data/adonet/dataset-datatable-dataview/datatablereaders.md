---
title: "DataTableReaders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTableReaders
<xref:System.Data.DataTableReader> представляет содержимое объекта <xref:System.Data.DataTable> или <xref:System.Data.DataSet> в виде одного или нескольких результирующих наборов, предназначенных только для чтения и только для перенаправления.  
  
 При создании объекта **DataTableReader** из **DataTable** итоговый объект **DataTableReader** содержит один результирующий набор с такими же данными, как и объект **DataTable**, из которого он был создан, за исключением любых строк, помеченных как удаленные.  Столбцы представлены в таком же порядке, как и в исходном объекте **DataTable**.  
  
 Объект **DataTableReader** может содержать несколько результирующих наборов, если он был создан путем вызова <xref:System.Data.DataSet.CreateDataReader%2A>.  Результаты показаны в таком же порядке, как и объекты **DataTable** в коллекции <xref:System.Data.DataSet.Tables%2A> объекта **DataSet**.  
  
## В этом подразделе  
 [Создание DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Описание создания объекта **DataTableReader**.  
  
 [Навигация в объектах DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Описание использования метода **Read** для перехода по содержимому объекта **DataTableReader**.  
  
## См. также  
 [Получение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)