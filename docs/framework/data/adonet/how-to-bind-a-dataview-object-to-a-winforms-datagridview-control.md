---
title: "Как привязать объект DataView к элементу управления Windows Forms DataGridView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как привязать объект DataView к элементу управления Windows Forms DataGridView
Элемент управления <xref:System.Windows.Forms.DataGridView> предоставляет мощный и гибкий способ отображения данных в табличном формате.  Элемент управления <xref:System.Windows.Forms.DataGridView> поддерживает стандартную модель привязки данных Windows Forms, поэтому он выполняет привязку к <xref:System.Data.DataView> и другим различным источникам данных.  Однако в большинстве случаев выполняется привязка к компоненту <xref:System.Windows.Forms.BindingSource>, управляющему взаимодействием с источником данных.  
  
 Дополнительные сведения об элементе управления <xref:System.Windows.Forms.DataGridView> см. в разделе [Общие сведения об элементе управления DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).  
  
### Соединение элемента управления DataGridView с объектом DataView  
  
1.  Реализуйте метод, обрабатывающий получение данных из базы данных.  В следующем примере реализован метод `GetData`, инициализирующий компонент <xref:System.Data.SqlClient.SqlDataAdapter> и использующий его для заполнения объекта <xref:System.Data.DataSet>.  Убедитесь, что переменной `connectionString` присвоено значение, соответствующее базе данных.  Потребуется доступ к SQL Server с установленным образцом базы данных AdventureWorks.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2.  В обработчике событий <xref:System.Windows.Forms.Form.Load> формы привяжите элемент управления <xref:System.Windows.Forms.DataGridView> к компоненту <xref:System.Windows.Forms.BindingSource> и вызовите метод `GetData` для получения данных из базы данных.  Объект <xref:System.Data.DataView> создается на основе запроса [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] к объекту <xref:System.Data.DataTable> с именем Contact, а затем привязывается к компоненту <xref:System.Windows.Forms.BindingSource>.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## См. также  
 [Связывание с данными и LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)