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
ms.openlocfilehash: 99acef0a7b29228ddf0406352ff5a88b77294b00
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966667"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Применение различных цветов к различным частям <xref:System.Windows.Forms.DataGrid> элемента управления помогает упростить чтение и анализ информации. Цвет может применяться к строкам и столбцам. Строки и столбцы также можно скрыть или показать по собственному усмотрению.  
  
 Существует три основных аспекта форматирования <xref:System.Windows.Forms.DataGrid> элемента управления. Можно задать свойства, чтобы установить стиль по умолчанию, в котором будут отображаться данные. С этого основания можно настроить способ отображения определенных таблиц во время выполнения. Наконец, можно изменить столбцы, отображаемые в сетке данных, а также цвета и другие отображаемые параметры форматирования.  
  
 В качестве начального шага при форматировании сетки данных можно задать свойства <xref:System.Windows.Forms.DataGrid> самого себя. Эти варианты цвета и формата образуют основу, из которой можно вносить изменения в зависимости от отображаемых таблиц и столбцов данных.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Установка стиля по умолчанию для элемента управления DataGrid  
  
1. При необходимости задайте следующие свойства:  
  
    |Свойство.|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> Свойство определяет цвет строк сетки с четными номерами. Если для <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства задан другой цвет, для каждой другой строки задается этот новый цвет (строки 1, 3, 5 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Цвет фона строк сетки с четными номерами (строки 0, 2, 4, 6 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|В то время как <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> <xref:System.Windows.Forms.DataGrid.BackColor%2A> и определяют цвет строк в сетке, свойство определяет цвет области нонров, которая отображается только при прокрутке сетки вниз, или если в таблице содержатся только несколько строк. Сетка.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Стиль границы сетки, одно из <xref:System.Windows.Forms.BorderStyle> значений перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Цвет фона заголовка окна сетки, который появляется непосредственно над сеткой.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Шрифт заголовка в верхней части сетки.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Цвет фона заголовка окна сетки.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Шрифт, используемый для вывода текста в сетке.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Цвет шрифта, отображаемого данными в строках сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Цвет линий сетки сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Стиль строк, разделяющих ячейки сетки, одно из <xref:System.Windows.Forms.DataGridLineStyle> значений перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Цвет фона заголовков строк и столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Шрифт, используемый для заголовков столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Цвет переднего плана для заголовков столбцов сетки, включая текст заголовка столбца и знаки плюса/минуса (для расширения строк при отображении нескольких связанных таблиц).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Цвет текста всех ссылок в сетке данных, включая ссылки на дочерние таблицы, имя связи и т. д.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|В дочерней таблице это цвет фона родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|В дочерней таблице это цвет переднего плана для родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Определяет, отображаются ли имена таблиц и столбцов в родительской строке с помощью <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Стандартная ширина (в пикселях) столбцов сетки. Установите это свойство перед сбросом <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойств и <xref:System.Windows.Forms.DataGrid.DataMember%2A> ( <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> отдельно или с помощью метода), либо свойство не будет действовать.<br /><br /> Свойству нельзя присвоить значение меньше 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Высота строки (в пикселях) в сетке. Установите это свойство перед сбросом <xref:System.Windows.Forms.DataGrid.DataSource%2A> свойств и <xref:System.Windows.Forms.DataGrid.DataMember%2A> ( <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> отдельно или с помощью метода), либо свойство не будет действовать.<br /><br /> Свойству нельзя присвоить значение меньше 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ширина заголовков строк сетки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Если выбрана строка или ячейка, это цвет фона.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Если выбрана строка или ячейка, это цвет переднего плана.|  
  
    > [!NOTE]
    > Помните, что при настройке цветов элементов управления можно сделать элемент управления недоступным из-за плохого выбора цвета (например, красный и зеленый). Чтобы избежать этой проблемы, используйте цвета, доступные в палитре **системные цвета** .  
  
     В следующих процедурах предполагается, что <xref:System.Windows.Forms.DataGrid> форма имеет элемент управления, привязанный к таблице данных. Дополнительные сведения см. [в разделе привязка Windows Forms элемента управления DataGrid к источнику данных](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Задание стиля таблицы и столбца таблицы данных программным способом  
  
1. Создайте новый стиль таблицы и задайте его свойства.  
  
2. Создайте стиль столбца и задайте его свойства.  
  
3. Добавьте стиль столбца в коллекцию стилей столбцов стиля таблицы.  
  
4. Добавьте стиль таблицы в коллекцию табличных стилей сетки данных.  
  
5. В приведенном ниже примере создайте экземпляр нового <xref:System.Windows.Forms.DataGridTableStyle> и задайте его <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство.  
  
6. Создайте новый экземпляр **гридколумнстиле** и задайте его **MappingName** (и другие свойства макета и экрана).  
  
7. Повторите шаги с 2 по 6 для каждого стиля столбца, который нужно создать.  
  
     В следующем примере показано, как <xref:System.Windows.Forms.DataGridTextBoxColumn> создается, поскольку имя отображается в столбце. Кроме того, вы добавляете стиль столбца к <xref:System.Windows.Forms.GridColumnStylesCollection> стилю таблицы и добавляете стиль <xref:System.Windows.Forms.GridTableStylesCollection> таблицы в сетку данных.  
  
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

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Практическое руководство. Удаление или скрытие столбцов в элементе управления Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
