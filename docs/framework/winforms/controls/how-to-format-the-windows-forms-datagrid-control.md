---
title: Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: ffcb84059dfceb85cdb347c3ddf1b80ab96c2aac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540453"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Выделение разными цветами различных частей <xref:System.Windows.Forms.DataGrid> управления позволяет облегчить чтение и понимание сведений. Цвет могут применяться к строкам и столбцам. Строки и столбцы можно также скрывать или отображать по необходимости.  
  
 Состоит из трех основных этапов форматирования <xref:System.Windows.Forms.DataGrid> элемента управления. Можно установить свойства, чтобы создать стиль по умолчанию, в котором отображаются данные. На этой основе можно настроить способ отображения некоторых таблицах во время выполнения. Наконец можно изменить столбцы, которые отображаются в сетке данных, а также цвета и другие элементы, которые отображается.  
  
 На первом этапе форматирования сетки данных можно задать свойства <xref:System.Windows.Forms.DataGrid> сам. Эти параметры цветов и форматирования составляют основу, из которой затем можно внести изменения в зависимости от данных таблиц и столбцов, отображаемых.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Чтобы создать стиль по умолчанию для элемента управления DataGrid  
  
1.  При необходимости задайте следующие свойства:  
  
    |Свойство.|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> Свойство определяет цвет строк сетки с четными номерами. При задании <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> другой цвет, все остальные строки является свойство цветом (строки 1, 3, 5 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Цвет фона строк сетки с четными номерами (строки 0, 2, 4, 6 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|В то время как <xref:System.Windows.Forms.DataGrid.BackColor%2A> и <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства определяет цвет строк в сетке <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> свойство определяет цвет области, незанятой строками, который отображается, только когда выполняется прокрутка нижней сетке, или только несколько строк, содержащихся в Сетка.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Стиль границ сетки, один из <xref:System.Windows.Forms.BorderStyle> значений перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Цвет фона названия окна сетки, расположенного непосредственно над сеткой.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Шрифт заголовка в верхней части сетки.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Цвет фона названия окна сетки.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Шрифт, используемый для отображения текста в сетке.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Цвет шрифта, которым данные в строках сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Цвет линий сетки сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Задает стиль линий, разделяющих ячейки сетки — одно из <xref:System.Windows.Forms.DataGridLineStyle> значений перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Цвет фона заголовков строк и столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Шрифт, используемый для заголовков столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Основной цвет заголовков столбцов сетки, включая текст заголовка столбца и глифы плюс/минус (для расширения строк при отображении нескольких связанных таблиц).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Цвет текста всех ссылок в сетке данных, включая ссылки на дочерние таблицы, имя отношения и т. д.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|В дочерней таблице это цвет фона родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|В дочерней таблице это основной цвет родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Определяет, отображаются ли имена таблиц и столбцов в родительской строке с помощью параметра <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Стандартная ширина (в пикселях) столбцов сетки. Присвойте этому свойству перед сбросом <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойств (либо отдельно, либо с помощью <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод), или свойство не будет действовать.<br /><br /> Свойство не может быть присвоено значение меньше 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Высота строки (в пикселях) строки в сетке. Присвойте этому свойству перед сбросом <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> свойств (либо отдельно, либо с помощью <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> метод), или свойство не будет действовать.<br /><br /> Свойство не может быть присвоено значение меньше 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ширина заголовков строк сетки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|При выборе строки или ячейки, это цвет фона.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|При выборе строки или ячейки, это цвет переднего плана.|  
  
    > [!NOTE]
    >  Следует помнить, при настройке цветов элементов управления, что можно сделать элемент управления недоступен из-за выбор неудачных цветов (например, красный и зеленый). Используйте цвета на **системных цветов** палитру цветов, чтобы избежать этой проблемы.  
  
     Следующие процедуры позволяют создать <xref:System.Windows.Forms.DataGrid> элемент управления привязан к таблице данных. Дополнительные сведения см. в разделе [привязки элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Задание стиля таблицы и столбца таблицы данных программным способом  
  
1.  Создайте новый стиль таблицы и задайте его свойства.  
  
2.  Создайте стиль столбца и задайте его свойства.  
  
3.  Добавьте стиль столбца в коллекцию стилей столбцов стиля таблицы.  
  
4.  Добавьте стиль таблицы в коллекцию стилей таблиц сетки данных.  
  
5.  В следующем примере создайте экземпляр нового <xref:System.Windows.Forms.DataGridTableStyle> и задайте его <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство.  
  
6.  Создать новый экземпляр **GridColumnStyle** и задайте его **MappingName** (и некоторые другие свойства отображения и).  
  
7.  Повторите шаги 2 – 6 для каждого стиля столбца, который требуется создать.  
  
     В следующем примере показан способ <xref:System.Windows.Forms.DataGridTextBoxColumn> создается, поскольку имя будет отображаться в столбце. Кроме того, добавить стиль столбца <xref:System.Windows.Forms.GridColumnStylesCollection> стиля таблицы и добавьте стиль таблицы для <xref:System.Windows.Forms.GridTableStylesCollection> сетки данных.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
