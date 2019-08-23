---
title: Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
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
ms.openlocfilehash: bac24c2dd622ea780408e902d08708ac09561044
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922727"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления <xref:System.Windows.Forms.DataGrid> Windows Forms специально разработан для вывода информации из источника данных. Элемент управления привязывается во время выполнения путем вызова <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метода. Несмотря на то, что можно отображать данные из различных источников данных, наиболее типичными источниками являются наборы данных и представления.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Привязка данных к элементу управления DataGrid программным способом  
  
1. Напишите код для заполнения набора данных.  
  
     Если источник данных является набором данных или представлением данных, основанным на таблице набора данных, добавьте в форму код для заполнения набора данных.  
  
     Точный код, который вы используете, зависит от того, где набор данных получает данные. Если набор данных заполняется непосредственно из базы данных, обычно вызывается `Fill` метод адаптера данных, как показано в следующем примере, который заполняет набор данных с именем: `DsCategories1`  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Если набор данных заполняется из веб-службы XML, обычно создается экземпляр службы в коде, а затем вызывается один из его методов для возврата набора данных. Затем вы объединяете набор данных из веб-службы XML в локальный набор данных. В следующем примере показано, как создать экземпляр веб-службы XML с именем `CategoriesService`, вызвать его `GetCategories` метод и объединить полученный набор данных в локальный набор данных с именем `DsCategories1`:  
  
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
  
2. Вызовите <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод элементауправления,передавемуисточникданныхиэлементданных.<xref:System.Windows.Forms.DataGrid> Если не нужно явно передавать элемент данных, передайте пустую строку.  
  
    > [!NOTE]
    > При первой привязке сетки можно задать свойства элемента управления <xref:System.Windows.Forms.DataGrid.DataSource%2A> и. <xref:System.Windows.Forms.DataGrid.DataMember%2A> Однако вы не сможете сбросить эти свойства после их установки. Поэтому рекомендуется всегда использовать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод.  
  
     В следующем примере показано, как можно программно выполнить привязку к таблице Customers в `DsCustomers1`наборе данных с именем:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Если таблица Customers является единственной таблицей в наборе данных, можно также привязать сетку таким образом:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. Используемых Добавьте соответствующие стили таблиц и столбцов в сетку. Если стили таблиц отсутствуют, вы увидите таблицу, но с минимальным форматированием и отображением всех столбцов.  
  
## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления Windows Forms DataGrid](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
