---
title: "Связывание с данными и LINQ to DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Связывание с данными и LINQ to DataSet
*Привязка данных* \- это процесс установления соединения между интерфейсом приложения и бизнес\-логикой.  Если для привязки заданы правильные настройки, а изменения значений данных сопровождаются правильными уведомлениями, привязанные к данным элементы автоматически отражают изменения.  Объект <xref:System.Data.DataSet> \- это находящееся в памяти представление данных, обеспечивающее согласованную реляционную программную модель, независимо от источника содержащихся в нем данных.  Объект <xref:System.Data.DataView> в ADO.NET 2.0 позволяет сортировать и фильтровать данные, хранящиеся в таблице <xref:System.Data.DataTable>.  Эта функциональность часто используется в приложениях связывания данных.  С помощью объекта <xref:System.Data.DataView> можно представлять данные в таблице с различными порядками сортировки, а также фильтровать данные по состоянию строки или на основе критерия фильтра.  Дополнительные сведения об объекте <xref:System.Data.DataView> см. в разделе [Объекты DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 Технология [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] позволяет создавать сложные и мощные запросы к объектам <xref:System.Data.DataSet> с помощью [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)].  Однако запрос [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] возвращает перечисление объектов <xref:System.Data.DataRow>, которое непросто использовать в сценариях привязки. Для упрощения привязки можно создать на основе запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] объект <xref:System.Data.DataView>.  Этот объект <xref:System.Data.DataView> использует параметры фильтрации и сортировки, указанные в запросе, но лучше приспособлен для привязки данных.  [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] расширяет возможности объекта <xref:System.Data.DataView>, предоставляя фильтрацию и сортировку [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] на основе выражений, что позволяет выполнять более сложные и мощные операции фильтрации и сортировки, чем фильтрация и сортировка на основе строк.  
  
 Обратите внимание, что объект <xref:System.Data.DataView> представляет непосредственно запрос, а не представление на основе запроса.  Объект <xref:System.Data.DataView> привязывается к элементу управления в пользовательском интерфейсе, так же как и <xref:System.Windows.Forms.DataGrid> или <xref:System.Windows.Forms.DataGridView>, обеспечивая простую модель привязки данных.  Объект <xref:System.Data.DataView> можно также создать на основе объекта <xref:System.Data.DataTable>, задав представление таблицы по умолчанию.  
  
## Содержание  
 [Создание объекта DataView](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Содержит сведения о создании объекта <xref:System.Data.DataView>.  
  
 [Фильтрация с помощью DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Описывает фильтрацию с помощью объекта <xref:System.Data.DataView>.  
  
 [Сортировка с помощью DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Описывает сортировку с помощью объекта <xref:System.Data.DataView>.  
  
 [Запрос к коллекции DataRowView в DataView](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Содержит сведения о запросах к коллекции <xref:System.Data.DataRowView>, предоставляемой объектом <xref:System.Data.DataView>.  
  
 [Производительность DataView](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Содержит сведения об объекте <xref:System.Data.DataView> и производительности.  
  
 [Как привязать объект DataView к элементу управления Windows Forms DataGridView](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Содержит описание процесса привязки объекта <xref:System.Data.DataView> к элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
## См. также  
 [Руководство по программированию](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)