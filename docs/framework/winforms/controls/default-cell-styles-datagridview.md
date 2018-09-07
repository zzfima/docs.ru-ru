---
title: Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: adee6ab283fb7e2fe9bbfcda78c9692621407e9e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44079430"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора
<xref:System.Windows.Forms.DataGridView> Элемент управления позволяет указать стилей ячейки по умолчанию и форматы данных для всего элемента управления, для определенных столбцов, для заголовков строк и столбцов и для чередующихся строк для создания эффекта книги ячейки. По умолчанию, установленным стилей для чередующихся строк и столбцов переопределены стили по умолчанию для всего элемента управления. Кроме того стили, заданные в коде для отдельных строк и ячеек, переопределяют стили по умолчанию.  
  
 Дополнительные сведения о стили ячеек, см. в разделе [стили ячеек элемента управления DataGridView Windows Forms в](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Установка стилей для чередующихся строк, см. в разделе [как: набор стилей для чередующихся строк в Windows Forms DataGridView элемента управления с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Можно также задать с помощью стилей <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойства влияют на все строки, которые будут добавлены к элементу управления. Дополнительные сведения о шаблоне строк см. в разделе [как: применение шаблонов строк для настройки строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Следующие процедуры требуют **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Установка стилей по умолчанию для всех ячеек в элементе управления  
  
1.  Выберите <xref:System.Windows.Forms.DataGridView> управления в конструкторе.  
  
2.  В **свойства** окно, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> свойство. **Построителя CellStyle** откроется диалоговое окно.  
  
3.  Определите стиль путем установки свойств, используя **предварительной версии** панели, чтобы подтвердить выбранные параметры.  
  
> [!NOTE]
>  Если стили оформления включены, заголовки строк и столбцов (за исключением <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются текущей темой, переопределяя <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> значения свойств.  
>   
>  Можно задать стили ячеек для нескольких выбранных <xref:System.Windows.Forms.DataGridView> элементы управления в конструкторе, но только если они имеют одинаковые значения для свойства стиля ячейки, нужно внести изменения. Если стили ячеек, отличаются для этого свойства, **свойства** windows из **построителя CellStyle** диалоговое окно будет пустым.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Установка стилей по умолчанию для ячеек в отдельных столбцах  
  
1.  Щелкните правой кнопкой мыши <xref:System.Windows.Forms.DataGridView> в конструкторе и выберите **Правка столбцов**.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  В **свойства столбца** сетки, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойство. **Построителя CellStyle** откроется диалоговое окно.  
  
4.  Определите стиль путем установки свойств, используя **предварительной версии** панели, чтобы подтвердить выбранные параметры.  
  
### <a name="to-format-data-in-cells"></a>Для форматирования данных в ячейках  
  
1.  Используйте один из приведенных выше процедур для отображения **построителя CellStyle** диалоговое окно, связанные со свойством стиль ячейки по умолчанию.  
  
2.  В **построителя CellStyle** диалоговом окне нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> свойство. **Строка формата** откроется диалоговое окно.  
  
3.  Выберите тип формата, а затем изменить сведения о типах (например, число десятичных разрядов), с помощью **пример** поле, чтобы подтвердить выбранные параметры.  
  
4.  При связывании <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных, которая, вероятнее всего содержать значения null, заполните **значение Null** текстовое поле. Это значение отображается в том случае, если значение ячейки равным пустой ссылкой (`Nothing` в Visual Basic) или <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [Практическое: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
