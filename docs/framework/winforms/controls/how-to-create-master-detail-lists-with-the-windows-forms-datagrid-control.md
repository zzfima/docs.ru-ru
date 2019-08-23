---
title: Практическое руководство. Создание списков «основной/подробности» с помощью элемента управления Windows Forms DataGrid
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
ms.openlocfilehash: f0fd95cf0cd66e9a5105c0b8ff77d8c536a5822d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914755"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a>Практическое руководство. Создание основных или подробных списков с помощью элемента управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Если содержит ряд связанных таблиц, можно использовать два <xref:System.Windows.Forms.DataGrid> элемента управления для отображения данных в формате "основной/подробности". <xref:System.Data.DataSet> Один <xref:System.Windows.Forms.DataGrid> из них обозначен как Главная сетка, а второй — сеткой сведений. При выборе записи в главном списке все связанные дочерние записи отображаются в списке подробностей. Например, если <xref:System.Data.DataSet> содержит таблицу Customers и связанную таблицу Orders, можно указать таблицу Customers, которая будет главной сеткой, а таблица Orders — сетку сведений. При выборе клиента из главной сетки все заказы, связанные с этим клиентом в таблице Orders, будут отображаться в сетке сведений.  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a>Настройка связи «основной/подробности» программным способом  
  
1. Создайте два новых <xref:System.Windows.Forms.DataGrid> элемента управления и задайте их свойства.  
  
2. Добавьте таблицы в набор данных.  
  
3. Объявите переменную типа <xref:System.Data.DataRelation> для представления отношения, которое необходимо создать.  
  
4. Создайте экземпляр связи, указав имя связи и указав таблицу, столбец и элемент, которые будут связывать две таблицы.  
  
5. Добавьте связь в <xref:System.Data.DataSet> <xref:System.Data.DataSet.Relations%2A> коллекцию объекта.  
  
6. Используйте метод класса, <xref:System.Windows.Forms.DataGrid> чтобы привязать каждую сетку к <xref:System.Data.DataSet>. <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>  
  
     В следующем примере показано, как задать связь «основной/подробности» между таблицами Customers и Orders в <xref:System.Data.DataSet> ранее`ds`созданной ().  
  
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

- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
