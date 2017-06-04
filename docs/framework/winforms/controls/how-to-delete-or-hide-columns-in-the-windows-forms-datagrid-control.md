---
title: "Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms | Microsoft Docs"
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
  - "столбцы [Windows Forms], удаление в таблицах данных"
  - "столбцы [Windows Forms], скрытие"
  - "таблицы данных, удаление столбцов"
  - "таблицы данных, скрытие столбцов"
  - "DataGrid - элемент управления [Windows Forms], удаление столбцов"
  - "DataGrid - элемент управления [Windows Forms], скрытие столбцов"
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Можно программно удалить или скрыть столбцы в элементе управления Windows Forms <xref:System.Windows.Forms.DataGrid>, используя свойства и методы объектов <xref:System.Windows.Forms.GridColumnStylesCollection> и <xref:System.Windows.Forms.DataGridColumnStyle> \(которые являются членами класса <xref:System.Windows.Forms.DataGridTableStyle>\).  
  
 Удаленные или скрытые столбцы остаются в источнике данных, к которому привязана сетка, и доступ к ним можно получить с помощью программных средств.  Эти столбцы не отражаются в элементе управления DataGrid.  
  
> [!NOTE]
>  Если в приложении нет доступа к определенным столбцам данных, и их не требуется отображать в элементе управления DataGrid, возможно их не следует включать в источник данных.  
  
### Чтобы удалить столбец из элемента управления DataGrid программным способом, выполните следующие действия:  
  
1.  В области объявлений формы объявите новый экземпляр класса <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2.  Укажите в свойстве <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=fullName> таблицу из источника данных, к которой требуется применить стиль.  Предполагается, что свойство <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName>, используемое в следующем примере, уже задано.  
  
3.  Добавьте новый объект <xref:System.Windows.Forms.DataGridTableStyle> в коллекцию стилей таблиц элемента управления DataGrid.  
  
4.  Вызовите метод <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> коллекции <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>, указав индекс столбца, который необходимо удалить.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### Чтобы скрыть столбец в элементе управления DataGrid программным способом, выполните следующие действия:  
  
1.  В области объявлений формы объявите новый экземпляр класса <xref:System.Windows.Forms.DataGridTableStyle>.  
  
2.  Задайте для свойства <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> элемента управления <xref:System.Windows.Forms.DataGridTableStyle> таблицу в источнике данных, к которой необходимо применить стиль.  Предполагается, что свойство <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName>, используемое в следующем примере кода, уже задано.  
  
3.  Добавьте новый объект <xref:System.Windows.Forms.DataGridTableStyle> в коллекцию стилей таблиц элемента управления DataGrid.  
  
4.  Скройте столбец, присвоив свойству`Width` значение 0 и указав индекс скрываемого столбца.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## См. также  
 [Практическое руководство. Изменение данных, отображаемых во время выполнения, в элементе управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)   
 [Практическое руководство. Добавление таблиц и столбцов в элемент управления DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)