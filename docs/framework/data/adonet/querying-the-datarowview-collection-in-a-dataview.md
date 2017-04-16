---
title: "Запрос к коллекции DataRowView в DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Запрос к коллекции DataRowView в DataView
Представление <xref:System.Data.DataView> обеспечивает доступ к перечисляемой коллекции объектов <xref:System.Data.DataRowView>.  Объект <xref:System.Data.DataRowView> предоставляет пользовательское представление объекта <xref:System.Data.DataRow> и отображает конкретную версию этого объекта <xref:System.Data.DataRow> в элементе управления.  В элементе управления, например <xref:System.Windows.Forms.DataGridView>, можно отобразить только одну версию объекта <xref:System.Data.DataRow>.  Доступ к объекту <xref:System.Data.DataRow>, представляемому объектом <xref:System.Data.DataRowView>, можно получить через свойство <xref:System.Data.DataRowView.Row%2A> объекта <xref:System.Data.DataRowView>.  При просмотре значений с помощью объекта <xref:System.Data.DataRowView> свойство <xref:System.Data.DataView.RowStateFilter%2A> определяет, какая версия строки базового объекта <xref:System.Data.DataRow> отображается.  Дополнительные сведения о доступе к различным версиям строк с помощью объекта <xref:System.Data.DataRow> см. в разделе [Состояния и версии строк](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  Поскольку коллекция объектов <xref:System.Data.DataRowView>, представляемых <xref:System.Data.DataView>, является перечислимой, для запросов к ней можно использовать [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].  
  
 В следующем примере выполняется запрос к таблице `Product` для вывода продуктов красного цвета и на основе этого запроса создается таблица.  Объект <xref:System.Data.DataView> создается из этой таблицы, а свойство <xref:System.Data.DataView.RowStateFilter%2A> задается для фильтрации удаленных и измененных строк.  Затем объект <xref:System.Data.DataView> используется в качестве источника для запроса LINQ, а объекты <xref:System.Data.DataRowView>, которые были изменены и удалены, привязываются к элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 В следующем примере таблица продуктов создается из представления, привязанного к элементу управления <xref:System.Windows.Forms.DataGridView>.  К объекту <xref:System.Data.DataView> выполняется запрос на получение продуктов красного цвета, а упорядоченные результаты привязываются к элементу управления <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## См. также  
 [Связывание с данными и LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)