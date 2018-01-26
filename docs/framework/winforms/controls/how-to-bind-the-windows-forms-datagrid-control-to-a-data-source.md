---
title: "Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных"
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
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c136aca0eda9ea906ad8bf6853a263adf6130609
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a>Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Windows Forms <xref:System.Windows.Forms.DataGrid> управления разработан специально для отображения сведений из источника данных. Привязка элемента управления во время выполнения путем вызова <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод. Несмотря на то, что может отображать данные из различных источников данных, типичных причин являются наборы данных и представления данных.  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a>Чтобы выполнить привязку данных элемента управления DataGrid программным способом  
  
1.  Напишите код для заполнения набора данных.  
  
     Если источником данных является набор данных или представление данных, основанное на таблице набора данных, добавьте код в форму для заполнения набора данных.  
  
     Точный код, который вы используете зависит от того, где поступают в набор данных. Если набор данных заполняется непосредственно из базы данных, обычно вызывается `Fill` метод адаптера данных, как показано в следующем примере, который заполняет набор данных с именем `DsCategories1`:  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Если набор данных заполняется из веб-служб XML, вы обычно создается экземпляр службы в коде и затем вызовите один из его методов для возврата набора данных. Затем набор данных из XML-веб-службы, объединяется с набором данных локальный. В следующем примере показано, как можно создать экземпляр XML-веб-службы с именем `CategoriesService`, вызовите его `GetCategories` метод и слияния, результирующий набор данных с локальным набором данных вызывается `DsCategories1`:  
  
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
  
2.  Вызовите <xref:System.Windows.Forms.DataGrid> элемента управления <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод, передав ему источник данных и элемент данных. Если необходимо явным образом передать данные-член, необходимо передайте пустую строку.  
  
    > [!NOTE]
    >  При привязке сетки впервые, можно задать элемент управления <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойства. Тем не менее нельзя восстановить эти свойства, как только они были заданы. Таким образом, рекомендуется всегда использовать <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метода.  
  
     В следующем примере показано, как программным образом выполнить привязку к таблице Customers в набор данных с именем `DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Если в таблице Customers только таблицу в наборе данных, можно также привязать сетке таким образом:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  (Необязательно) Добавьте требуемые стили таблиц и столбцов в сетке. Если стили таблиц отсутствуют, появится таблица с минимальным форматированием и при этом все столбцы видимым.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Привязка данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)
