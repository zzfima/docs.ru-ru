---
title: "Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms | Microsoft Docs"
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
  - "ячейки, изменение значений ячеек в элементе управления DataGrid"
  - "DataGrid - элемент управления [Windows Forms], привязка данных"
  - "DataGrid - элемент управления [Windows Forms], динамическое изменение во время выполнения"
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 После создания элемента управления Windows Forms <xref:System.Windows.Forms.DataGrid> с помощью средств, доступных на этапе разработки, может возникнуть необходимость динамического изменения элементов управления объектов <xref:System.Data.DataSet> сетки во время выполнения.  Это может быть изменение как отдельных значений таблицы, так и источника данных, привязанного к элементу управления <xref:System.Windows.Forms.DataGrid>.  Изменение отдельных значений выполняется с помощью объекта <xref:System.Data.DataSet>, а не элемента управления <xref:System.Windows.Forms.DataGrid>.  
  
### Чтобы изменить данные программным образом  
  
1.  Выберите требуемую таблицу в объекте <xref:System.Data.DataSet>, а затем нужную строку и поле в таблице и укажите в ячейке новое значение.  
  
    > [!NOTE]
    >  Для выбора первой таблицы в объекте <xref:System.Data.DataSet> или первой строки ячейки введите 0.  
  
     В следующем примере показано, как изменить вторую запись первой строки набора данных, используя кнопку`Button1`.  Объекты <xref:System.Data.DataSet> \(`ds`\) и Tables \(`0` и`1`\) были созданы заранее.  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) Добавьте в конструктор формы следующий код, чтобы зарегистрировать обработчик событий.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     Во время выполнения можно воспользоваться методом <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> для привязки элемента управления <xref:System.Windows.Forms.DataGrid> к другому источнику данных.  Например, элементы управления данными [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] можно подключить к отдельным базам данных.  
  
### Чтобы изменить объект DataSource программным образом  
  
1.  Укажите для метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> имя источника данных и таблицу для привязки к нему.  
  
     В следующем примере показано, как с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> заменить источник данных на элемент управления данными [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] \(adoPubsAuthors\), связанный с таблицей Authors в базе данных Pubs.  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## См. также  
 [Объекты DataSet ADO.NET](../../../../docs/framework/data/adonet/ado-net-datasets.md)   
 [Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [Практическое руководство. Привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)