---
title: Привязать управление DataGrid к источнику данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182245"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGrid> Windows Forms специально разработан для отображения информации из источника данных. Вы связываете элемент управления во <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> время выполнения, вызывая метод. Хотя данные можно отображать из различных источников данных, наиболее типичными источниками являются наборы данных и представления данных.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Связать данные управления DataGrid программно  
  
1. Напишите код для заполнения набора данных.  
  
     Если источником данных является набор данных или представление данных на основе таблицы набора данных, добавьте код в форму для заполнения набора данных.  
  
     Точный код, который вы используете, зависит от того, где набор данных получает данные. Если набор данных заполняется непосредственно из базы данных, обычно вы вызываете `Fill` метод адаптера данных, `DsCategories1`как в следующем примере, который заполняет набор данных под названием:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Если набор данных заполняется из веб-службы XML, обычно создается экземпляр службы в коде, а затем звоните одному из ее методов, чтобы вернуть набор данных. Затем вы объединяете набор данных из Веб-службы XML в локальный набор данных. Ниже приводится, как можно создать экземпляр веб-службы XML под названием, `CategoriesService`вызвать его `GetCategories` метод `DsCategories1`и объединить полученный набор данных в локальный набор данных под названием:  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. Вызовите <xref:System.Windows.Forms.DataGrid> <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод управления, передав его источнику данных и члену данных. Если вам не нужно явно передавать элемент данных, передайте пустую строку.  
  
    > [!NOTE]
    > Если вы впервые привязываете сетку, можно <xref:System.Windows.Forms.DataGrid.DataSource%2A> установить элемент управления и <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойства. Однако вы не можете сбросить эти свойства после их установки. Поэтому рекомендуется всегда использовать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод.  
  
     Следующий пример показывает, как можно программно привязаться к `DsCustomers1`таблице Клиентов в наборе данных под названием:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Если таблица Клиентов является единственной таблицей в наборе данных, можно связать сетку таким образом:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. (Необязательно) Добавьте в сетку соответствующие стили таблицы и столбцов. Если нет стилей таблицы, вы увидите таблицу, но с минимальным форматированием и со всеми видимыми столбцов.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
