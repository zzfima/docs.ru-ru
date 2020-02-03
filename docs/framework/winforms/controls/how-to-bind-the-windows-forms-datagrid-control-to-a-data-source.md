---
title: Привязка элемента управления DataGrid к источнику данных
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
ms.openlocfilehash: 2634a6bd8ace36bcf7a49120162474a8c04b2b83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746686"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.DataGrid> специально разработан для вывода информации из источника данных. Элемент управления привязывается во время выполнения путем вызова метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>. Несмотря на то, что можно отображать данные из различных источников данных, наиболее типичными источниками являются наборы данных и представления.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Привязка данных к элементу управления DataGrid программным способом  
  
1. Напишите код для заполнения набора данных.  
  
     Если источник данных является набором данных или представлением данных, основанным на таблице набора данных, добавьте в форму код для заполнения набора данных.  
  
     Точный код, который вы используете, зависит от того, где набор данных получает данные. Если набор данных заполняется непосредственно из базы данных, обычно вызывается метод `Fill` адаптера данных, как показано в следующем примере, который заполняет набор данных с именем `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Если набор данных заполняется из веб-службы XML, обычно создается экземпляр службы в коде, а затем вызывается один из его методов для возврата набора данных. Затем вы объединяете набор данных из веб-службы XML в локальный набор данных. В следующем примере показано, как можно создать экземпляр веб-службы XML с именем `CategoriesService`, вызвать его метод `GetCategories` и объединить полученный набор данных в локальный набор данных с именем `DsCategories1`:  
  
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
  
2. Вызовите метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> элемента управления <xref:System.Windows.Forms.DataGrid>, передав ему источник данных и элемент данных. Если не нужно явно передавать элемент данных, передайте пустую строку.  
  
    > [!NOTE]
    > При первой привязке сетки можно задать свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> элемента управления. Однако вы не сможете сбросить эти свойства после их установки. Поэтому рекомендуется всегда использовать метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  
  
     В следующем примере показано, как можно программно выполнить привязку к таблице Customers в наборе данных с именем `DsCustomers1`.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления DataGrid](datagrid-control-overview-windows-forms.md)
- [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
