---
title: "Как: Создание основной подробности списков с элемента управления DataGrid в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63cb647e2ed6dcbc97fab15db3166b55c52f635a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Практическое руководство. Создание основных или подробных списков с помощью элемента управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если ваш <xref:System.Data.DataSet> содержит набор связанных таблиц, можно использовать два <xref:System.Windows.Forms.DataGrid> элементы управления для отображения данных в формате иерархического. Один <xref:System.Windows.Forms.DataGrid> назначен в качестве основной сетки, а второй для сетки сведений. При выборе элемента в главном списке все связанные дочерние записи отображаются в списке сведений. Например если ваш <xref:System.Data.DataSet> содержит таблицу Customers и связанную таблицу Orders, можно указать таблицу Customers основной сетки, а таблицу Orders, чтобы быть в таблице сведений. При выборе клиента в основной сетке все заказы, относящиеся к этому клиенту в таблице Orders будет отображаться в таблице сведений.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Чтобы установить отношение главный/подчиненный программными средствами  
  
1.  Создайте два новых <xref:System.Windows.Forms.DataGrid> элементов управления и задавать их свойства.  
  
2.  Добавление таблиц в наборе данных.  
  
3.  Объявите переменную типа <xref:System.Data.DataRelation> для представления связи, необходимо создать.  
  
4.  Создайте экземпляр связи, задав имя для связи и указав таблицу, столбец и элемент, который будет связывать обе таблицы.  
  
5.  Добавить отношение к <xref:System.Data.DataSet> объекта <xref:System.Data.DataSet.Relations%2A> коллекции.  
  
6.  Используйте <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод <xref:System.Windows.Forms.DataGrid> для привязки каждой сетки к <xref:System.Data.DataSet>.  
  
     Приведенный ниже показано, как задать связь между таблицами Customers и Orders в ранее созданные иерархического <xref:System.Data.DataSet> (`ds`).  
  
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
  
## <a name="see-also"></a>См. также  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
