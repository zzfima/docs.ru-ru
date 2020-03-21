---
title: Управление DataGrid формата
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
ms.openlocfilehash: 180f837c7d60f49af880faefc05da262be061d12
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182137"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>Практическое руководство. Форматирование элемента управления DataGrid в Windows Forms
> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Применение различных цветов к <xref:System.Windows.Forms.DataGrid> различным частям элемента управления может помочь сделать информацию в ней легче читать и интерпретировать. Цвет можно наносить на строки и столбцы. Строки и столбцы также могут быть скрыты или показаны по вашему усмотрению.  
  
 Существует три основных аспекта <xref:System.Windows.Forms.DataGrid> форматирования управления. Можно настроить свойства для определения стиля по умолчанию, в котором отображаются данные. С этой базы можно настроить способ отображения определенных таблиц во время выполнения. Наконец, можно изменить, какие столбцы отображаются в сетке данных, а также цвета и другие форматирования, которые отображаются.  
  
 В качестве первого шага в форматировании сетки <xref:System.Windows.Forms.DataGrid> данных можно установить свойства самой. Эти выборы цветов и форматов образуют базу, из которой можно вносить изменения в зависимости от отображаемых таблиц данных и столбцов.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Установить стиль по умолчанию для управления DataGrid  
  
1. Установите следующие свойства по мере необходимости:  
  
    |Свойство|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|Свойство <xref:System.Windows.Forms.DataGrid.BackColor%2A> определяет цвет четных строк сетки. При установке <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства на другой цвет, каждый другой ряд установлен на этот новый цвет (строки 1, 3, 5, и так далее).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Цвет фона четных рядов сетки (ряды 0, 2, 4, 6 и так далее).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|В то <xref:System.Windows.Forms.DataGrid.BackColor%2A> <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> время как и свойства определяют цвет строк <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> в сетке, свойство определяет цвет области nonrow, которая видна только при прокрутке сетки внизу, или если в сетке содержится только несколько рядов.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Пограничный стиль сетки, одно <xref:System.Windows.Forms.BorderStyle> из значений перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Фоновый цвет подписи окна сетки, которая появляется непосредственно над сеткой.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Шрифт подписи в верхней части сетки.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Фоновый цвет подписи к окну сетки.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|Шрифт, используемый для отображения текста в сетке.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Цвет шрифта, отображаемый данными в рядах сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Цвет линий сетки сетки данных.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Стиль линий, разделяющих ячейки сетки, <xref:System.Windows.Forms.DataGridLineStyle> одно из значений перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Цвет фона строки и заголовки столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Шрифт, используемый для заголовков столбцов.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Цвет переднего плана заголовков столбца сетки, включая текст заголовка столбца и глифы плюс/минус (для расширения строк при отображении нескольких связанных таблиц).|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Цвет текста всех ссылок в сетке данных, включая ссылки на детские таблицы, имя отношения и так далее.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|В таблице ребенка это цвет фона родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|В детском столе это цвет переднего плана родительских строк.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Определяет, отображаются ли имена таблицы и столбца <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> в родительском ряду с помощью перечисления.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Стандартная ширина (в пикселях) столбцов сетки. Установите это свойство <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> перед сбросом и <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> свойствами (либо отдельно, либо методом), иначе свойство не будет иметь эффекта.<br /><br /> Свойство не может быть установлено на значение менее 0.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Высота строки (в пикселях) строк в сетке. Установите это свойство <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> перед сбросом и <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> свойствами (либо отдельно, либо методом), иначе свойство не будет иметь эффекта.<br /><br /> Свойство не может быть установлено на значение менее 0.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ширина строки заголовки сетки.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|При выборе строки или ячейки это цвет фона.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|При выборе строки или ячейки это цвет переднего плана.|  
  
    > [!NOTE]
    > Имейте в виду, при настройке цветов элементов управления, что можно сделать управление недоступным, из-за плохого выбора цвета (например, красный и зеленый). Используйте цвета, доступные в палитре **цвета системы,** чтобы избежать этой проблемы.  
  
     Следующие процедуры предполагают, <xref:System.Windows.Forms.DataGrid> что ваша форма имеет элемент управления, привязанный к таблице данных. Для получения дополнительной информации [см.](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>Налажить таблицу таблицы данных в таблице таблицы данных программно  
  
1. Создайте новый стиль таблицы и установите его свойства.  
  
2. Создайте стиль столбца и установите его свойства.  
  
3. Добавьте стиль столбца в коллекцию стилей столбцов в стиле таблицы.  
  
4. Добавьте стиль таблицы в коллекцию стилей таблицы сетки данных.  
  
5. В приведенном ниже примере создайте экземпляр нового <xref:System.Windows.Forms.DataGridTableStyle> и установите его <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойство.  
  
6. Создайте новый экземпляр **GridColumnStyle** и установите его **MappingName** (и некоторые другие свойства макета и отображения).  
  
7. Повторите шаги 2-6 для каждого стиля столбца, который вы хотите создать.  
  
     Следующий пример иллюстрирует, <xref:System.Windows.Forms.DataGridTextBoxColumn> как создается имя, потому что имя должно отображаться в столбце. Кроме того, к стилю <xref:System.Windows.Forms.GridColumnStylesCollection> таблицы добавляется стиль столбца и <xref:System.Windows.Forms.GridTableStylesCollection> добавляется стиль таблицы в сетку данных.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
