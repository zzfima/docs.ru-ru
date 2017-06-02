---
title: "Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms | Microsoft Docs"
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
  - "цвета, применение к элементам управления DataGrid"
  - "столбцы [Windows Forms], DataGrid - элемент управления"
  - "столбцы [Windows Forms], форматирование данных в элементе управления DataGrid"
  - "DataGrid - элемент управления [Windows Forms], основные стили"
  - "DataGrid - элемент управления [Windows Forms], форматирование"
  - "форматирование [Windows Forms]"
  - "таблицы [Windows Forms], форматирование данных в элементе управления DataGrid"
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем.  Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Выделение разными цветами различных частей элемента управления <xref:System.Windows.Forms.DataGrid> поможет облегчить чтение и понимание сведений.  Цветами можно выделять строки и столбцы.  Строки и столбцы можно также скрывать или отображать по необходимости.  
  
 Форматирование элемента управления <xref:System.Windows.Forms.DataGrid> состоит из трех основных этапов.  Можно настроить свойства для создания стиля отображения данных по умолчанию.  На этой основе можно затем изменить способ представления определенных таблиц во время выполнения.  Наконец, можно указать столбцы, отображаемые в сетке данных, а также цвета и другие параметры форматирования для них.  
  
 На первом этапе форматирования сетки данных можно задать свойства элемента управления <xref:System.Windows.Forms.DataGrid>.  Выбранные параметры цветов и форматирования составляют основу, в которую впоследствии можно вносить изменения, исходя из требований к отображению таблиц и столбцов.  
  
### Чтобы создать стиль по умолчанию для элемента управления DataGrid  
  
1.  Задайте нужным образом следующие свойства:  
  
    |Свойство.|Описание|  
    |---------------|--------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Свойство <xref:System.Windows.Forms.DataGrid.BackColor%2A> определяет цвет четных строк сетки.  Если в свойстве <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> задан другой цвет, все остальные строки выделяются этим цветом \(строки 1, 3, 5 и так далее\).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Фоновый цвет четных строк сетки \(строки 0, 2, 4, 6 и так далее\).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Если свойства <xref:System.Windows.Forms.DataGrid.BackColor%2A> и <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> определяют цвета строк сетки, то свойство <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> определяет цвет области, незанятой строками, которая видна, только когда сетка прокручена вниз или содержит небольшое количество строк.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Стиль границы сетки — одно из перечисляемых значений свойства <xref:System.Windows.Forms.BorderStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Фоновый цвет заголовка окна сетки, расположенного непосредственно над сеткой.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Шрифт заголовка в верхней части сетки.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Фоновый цвет заголовка окна сетки.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Шрифт текста в сетке.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Цвет шрифта, которым представлены данные в строках сетки.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Цвет линий сетки.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Стиль линий, разделяющих ячейки сетки — одно из перечисляемых значений свойства <xref:System.Windows.Forms.DataGridLineStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Фоновый цвет заголовков строк и столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Шрифт заголовков столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Цвет заголовков столбцов сетки, включая текст самих заголовков, а также знаки плюс и минус, служащие для развертывания и свертывания строк при просмотре нескольких связанных таблиц.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Цвет текста всех ссылок в сетке данных, включая ссылки на дочерние таблицы, имя отношения и так далее.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|Фоновый цвет родительских строк в дочерней таблице.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|Цвет текста родительских строк в дочерней таблице.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Определяет, отображаются ли названия таблицы и столбцов в родительской строке с помощью перечисления <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Стандартная ширина \(в пикселях\) столбцов сетки.  Установите это свойство, прежде чем сбрасывать свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> \(либо отдельно, либо с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\), иначе свойство не подействует.<br /><br /> Данное свойство не может иметь отрицательное значение.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Стандартная высота \(в пикселях\) строк сетки.  Установите это свойство, прежде чем сбрасывать свойства <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> \(либо отдельно, либо с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>\), иначе свойство не подействует.<br /><br /> Данное свойство не может иметь отрицательное значение.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ширина заголовков строк сетки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Фоновый цвет выделенной строки или ячейки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Цвет текста выделенной строки или ячейки.|  
  
    > [!NOTE]
    >  При настройке цветов элементов управления следует учесть, что выбор неудачных цветов \(например, красный и зеленый\) может затруднить работу с элементом управления.  Чтобы избежать этого, используйте цвета из палитры **Системные цвета**.  
  
     Следующие процедуры позволяют создать элемент управления <xref:System.Windows.Forms.DataGrid>, связанный с таблицей данных.  Дополнительные сведения см. в разделе [Привязка элемента управления Windows Forms DataGrid к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### Чтобы задать стили таблицы и столбца таблицы данных программным образом  
  
1.  Создайте новый стиль таблицы и задайте его свойства.  
  
2.  Создайте стиль столбца и задайте его свойства.  
  
3.  Добавьте стиль столбца в коллекцию стилей столбцов стиля таблицы.  
  
4.  Добавьте стиль таблицы в коллекцию стилей таблиц сетки данных.  
  
5.  В следующем примере создайте экземпляр нового <xref:System.Windows.Forms.DataGridTableStyle> и задайте его свойство <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>.  
  
6.  Создайте новый экземпляр стиля **GridColumnStyle** и задайте его свойство **MappingName**, а также некоторые другие свойства отображения и расположения.  
  
7.  Повторите шаги со 2 по 6 для каждого создаваемого стиля столбца.  
  
     В следующем примере проиллюстрировано создание <xref:System.Windows.Forms.DataGridTextBoxColumn>, поскольку в столбце должно отображаться имя.  Кроме того, в класс <xref:System.Windows.Forms.GridColumnStylesCollection> стиля таблицы добавляется стиль столбца, а в класс <xref:System.Windows.Forms.GridTableStylesCollection> сетки данных — стиль таблицы.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## См. также  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [Практическое руководство. Удаление или сокрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)