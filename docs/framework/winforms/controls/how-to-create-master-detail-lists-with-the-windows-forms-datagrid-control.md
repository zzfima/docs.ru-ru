---
title: Создание списков «основной/подробности» с помощью элемента управления DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: e8ab63d52d97a8a6e6f60da741186e3937350e1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76730980"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Практическое руководство. Создание основных или подробных списков с помощью элемента управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если <xref:System.Data.DataSet> содержит ряд связанных таблиц, можно использовать два элемента управления <xref:System.Windows.Forms.DataGrid> для отображения данных в формате "основной/подробности". Один <xref:System.Windows.Forms.DataGrid> обозначен как Главная сетка, а второй — сеткой сведений. При выборе записи в главном списке все связанные дочерние записи отображаются в списке подробностей. Например, если <xref:System.Data.DataSet> содержит таблицу Customers и связанную таблицу Orders, то необходимо указать таблицу Customers, которая будет главной сеткой, а таблица Orders — сетку сведений. При выборе клиента из главной сетки все заказы, связанные с этим клиентом в таблице Orders, будут отображаться в сетке сведений.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Настройка связи «основной/подробности» программным способом  
  
1. Создайте два новых элемента управления <xref:System.Windows.Forms.DataGrid> и задайте их свойства.  
  
2. Добавьте таблицы в набор данных.  
  
3. Объявите переменную типа <xref:System.Data.DataRelation> для представления отношения, которое необходимо создать.  
  
4. Создайте экземпляр связи, указав имя связи и указав таблицу, столбец и элемент, которые будут связывать две таблицы.  
  
5. Добавьте связь в коллекцию <xref:System.Data.DataSet.Relations%2A> объекта <xref:System.Data.DataSet>.  
  
6. Используйте метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> <xref:System.Windows.Forms.DataGrid>, чтобы привязать каждую сетку к <xref:System.Data.DataSet>.  
  
     В следующем примере показано, как задать отношение "основной/подробности" между таблицами Customers и Orders в ранее созданной <xref:System.Data.DataSet> (`ds`).  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
