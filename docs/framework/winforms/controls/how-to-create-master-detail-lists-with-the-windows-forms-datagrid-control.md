---
title: "Практическое руководство. Создание основных или подробных списков с помощью элемента управления DataGrid в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGrid - элемент управления [Windows Forms], списки типа "основной-подробности""
  - "списки типа "основной-подробности""
  - "связанные таблицы, отображение данных в элементе управления DataGrid"
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Создание основных или подробных списков с помощью элемента управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если объект <xref:System.Data.DataSet> содержит набор связанных таблиц, для представления данных в формате сводки\/основных сведений можно использовать два элемента управления <xref:System.Windows.Forms.DataGrid>.  В этом случае один элемент управления <xref:System.Windows.Forms.DataGrid> является основной сеткой, а второй — сеткой сведений.  При выборе записи в основном списке все связанные дочерние записи отображаются в списке сведений.  Например, если в объекте <xref:System.Data.DataSet> находятся таблица "Customers" и связанная таблица "Orders", таблицу "Customers" можно указать в качестве основной сетки, а таблицу "Orders" — в качестве сетки сведений.  При выборе заказчика в основной сетке все заказы, связанные с ним в таблице "Orders", отобразятся в сетке сведений.  
  
### Чтобы настроить связь сводки с основными сведениями программным образом  
  
1.  Создайте два новых элемента управления <xref:System.Windows.Forms.DataGrid> и задайте их свойства.  
  
2.  Добавьте таблицы в набор данных.  
  
3.  Объявите переменную типа <xref:System.Data.DataRelation> для представления создаваемой связи.  
  
4.  Создайте экземпляр связи, указав ее имя и задав таблицу, столбец и элемент, который будет связывать обе таблицы.  
  
5.  Добавьте связь в коллекцию <xref:System.Data.DataSet.Relations%2A> объекта <xref:System.Data.DataSet>.  
  
6.  Используйте метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> у <xref:System.Windows.Forms.DataGrid> для привязки каждой сетки к <xref:System.Data.DataSet>.  
  
     В следующем примере показано, как настроить связь основных сведений\/сводки между таблицами Customers и Orders в ранее созданном объекте <xref:System.Data.DataSet> \(`ds`\).  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)