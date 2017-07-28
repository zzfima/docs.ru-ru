---
title: "Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных | Microsoft Docs"
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
  - "элементы управления с привязкой"
  - "элементы управления с привязкой, DataGrid - элемент управления"
  - "привязка данных, DataGrid - элемент управления"
  - "элементы управления с привязкой к данным, DataGrid"
  - "DataGrid - элемент управления [Windows Forms], привязка данных"
  - "наборы данных [Windows Forms], привязка данных к элементу управления DataGrid"
  - "элементы управления Windows Forms, привязка данных"
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Элемент управления Windows Forms <xref:System.Windows.Forms.DataGrid> разработан специально для отображения сведений из источника данных.  Элемент управления можно привязать во время выполнения, вызвав метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  Несмотря на то что данные можно открывать из различных источников, обычно в качестве источников используются наборы данных и представления данных.  
  
### Чтобы выполнить привязку данных для элемента управления DataGrid программными средствами  
  
1.  Напишите код для заполнения набора данных.  
  
     Если источником данных является набор данных или представление данных, основанное на таблице DataSet, добавьте код в форму для заполнения набора данных.  
  
     Текст программы зависит от расположения, из которого данные поступают в набор.  Если набор данных заполняется непосредственно из базы данных, обычно вызывается метод`Fill` адаптера данных, как в приведенном ниже примере, который заполняет набор данных с именем`DsCategories1`.  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     Если набор данных заполняется с помощью веб\-службы XML, обычно в коде создается экземпляр службы, а затем вызывается один из ее методов для извлечения набора данных.  Затем набор данных, полученный из веб\-службы XML, объединяется с локальным набором данных.  В следующем примере показано, как можно создать экземпляр веб\-службы XML с именем`CategoriesService`, вызвать его метод`GetCategories` и объединить полученный в результате этого набор данных с локальным набором данных`DsCategories1`:  
  
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
  
2.  Вызовите метод <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> элемента управления <xref:System.Windows.Forms.DataGrid> и передайте ему источник данных и член данных.  Если не требуется явно передавать член данных, передайте пустую строку.  
  
    > [!NOTE]
    >  При привязке сетки впервые, можно задать свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> элемента управления.  Однако если значения этих свойств уже определены, изменять их нельзя.  Таким образом, всегда рекомендуется пользоваться методом <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.  
  
     В следующем примере показано, как программными средствами выполнить привязку к таблице Customers в наборе данных`DsCustomers1`:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     Если таблица Customers единственная в наборе данных, сетку можно также привязать следующим способом:  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3.  \(Необязательно\). Добавьте в сетку требуемые стили таблиц и столбцов.  Если стили таблиц отсутствуют, таблица отобразится с минимальным форматированием, при этом все столбцы будут доступны для просмотра.  
  
## См. также  
 [Общие сведения об элементе управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md)