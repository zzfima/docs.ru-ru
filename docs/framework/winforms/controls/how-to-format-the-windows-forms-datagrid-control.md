---
title: Форматирование элемента управления DataGrid
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
ms.openlocfilehash: 30342a89f3176255fa7217ccbbbd91c166ff7f35
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732957"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Применение различных цветов к различным частям элемента управления <xref:System.Windows.Forms.DataGrid> может помочь упростить чтение и анализ информации. Цвет может применяться к строкам и столбцам. Строки и столбцы также можно скрыть или показать по собственному усмотрению.  
  
 Существует три основных аспекта форматирования элемента управления <xref:System.Windows.Forms.DataGrid>. Можно задать свойства, чтобы установить стиль по умолчанию, в котором будут отображаться данные. С этого основания можно настроить способ отображения определенных таблиц во время выполнения. Наконец, можно изменить столбцы, отображаемые в сетке данных, а также цвета и другие отображаемые параметры форматирования.  
  
 В качестве начального шага при форматировании сетки данных можно задать свойства самого <xref:System.Windows.Forms.DataGrid>. Эти варианты цвета и формата образуют основу, из которой можно вносить изменения в зависимости от отображаемых таблиц и столбцов данных.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Установка стиля по умолчанию для элемента управления DataGrid  
  
1. При необходимости задайте следующие свойства:  
  
    |Идентификаторы|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Свойство <xref:System.Windows.Forms.DataGrid.BackColor%2A> определяет цвет строк сетки с четными номерами. Если для свойства <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> задан другой цвет, для каждой другой строки задается этот новый цвет (строки 1, 3, 5 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Цвет фона строк сетки с четными номерами (строки 0, 2, 4, 6 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|В то время как свойства <xref:System.Windows.Forms.DataGrid.BackColor%2A> и <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> определяют цвет строк в сетке, свойство <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> определяет цвет области нонров, который отображается только при прокрутке сетки вниз, или если в сетке содержатся только несколько строк.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Стиль границы сетки, одно из значений перечисления <xref:System.Windows.Forms.BorderStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Цвет фона заголовка окна сетки, который появляется непосредственно над сеткой.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Шрифт заголовка в верхней части сетки.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Цвет фона заголовка окна сетки.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Шрифт, используемый для вывода текста в сетке.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Цвет шрифта, отображаемого данными в строках сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Цвет линий сетки сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Стиль строк, разделяющих ячейки сетки, одно из значений перечисления <xref:System.Windows.Forms.DataGridLineStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Цвет фона заголовков строк и столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Шрифт, используемый для заголовков столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Цвет переднего плана для заголовков столбцов сетки, включая текст заголовка столбца и знаки плюса/минуса (для расширения строк при отображении нескольких связанных таблиц).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Цвет текста всех ссылок в сетке данных, включая ссылки на дочерние таблицы, имя связи и т. д.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|В дочерней таблице это цвет фона родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|В дочерней таблице это цвет переднего плана для родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Определяет, отображаются ли имена таблиц и столбцов в родительской строке с помощью перечисления <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Стандартная ширина (в пикселях) столбцов сетки. Задайте это свойство перед сбросом свойств <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> (либо отдельно, либо с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>), либо свойство не будет действовать.<br /><br /> Свойству нельзя присвоить значение меньше 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Высота строки (в пикселях) в сетке. Задайте это свойство перед сбросом свойств <xref:System.Windows.Forms.DataGrid.DataSource%2A> и <xref:System.Windows.Forms.DataGrid.DataMember%2A> (либо отдельно, либо с помощью метода <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>), либо свойство не будет действовать.<br /><br /> Свойству нельзя присвоить значение меньше 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ширина заголовков строк сетки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Если выбрана строка или ячейка, это цвет фона.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Если выбрана строка или ячейка, это цвет переднего плана.|  
  
    > [!NOTE]
    > Помните, что при настройке цветов элементов управления можно сделать элемент управления недоступным из-за плохого выбора цвета (например, красный и зеленый). Чтобы избежать этой проблемы, используйте цвета, доступные в палитре **системные цвета** .  
  
     В следующих процедурах предполагается, что в форме имеется элемент управления <xref:System.Windows.Forms.DataGrid>, привязанный к таблице данных. Дополнительные сведения см. [в разделе привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Задание стиля таблицы и столбца таблицы данных программным способом  
  
1. Создайте новый стиль таблицы и задайте его свойства.  
  
2. Создайте стиль столбца и задайте его свойства.  
  
3. Добавьте стиль столбца в коллекцию стилей столбцов стиля таблицы.  
  
4. Добавьте стиль таблицы в коллекцию табличных стилей сетки данных.  
  
5. В приведенном ниже примере создайте экземпляр нового <xref:System.Windows.Forms.DataGridTableStyle> и задайте его свойство <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>.  
  
6. Создайте новый экземпляр **гридколумнстиле** и задайте его **MappingName** (и другие свойства макета и экрана).  
  
7. Повторите шаги с 2 по 6 для каждого стиля столбца, который нужно создать.  
  
     В следующем примере показано, как создается <xref:System.Windows.Forms.DataGridTextBoxColumn>, поскольку имя отображается в столбце. Кроме того, можно добавить стиль столбца к <xref:System.Windows.Forms.GridColumnStylesCollection> стиля таблицы, а также добавить стиль таблицы в <xref:System.Windows.Forms.GridTableStylesCollection> сетки данных.  
  
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
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
