---
title: "Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2785b666039b9a8594e86cdd3a6fb25b9c382158
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора
<xref:System.Windows.Forms.DataGridView> Элемент управления позволяет установить стили для ячейки по умолчанию и форматы данных для всего элемента управления, для определенных столбцов, для заголовков строк и столбцов и для чередующихся строк для создания эффекта бухгалтерской книги ячейки. Стили по умолчанию для всего элемента управления, переопределяются, по умолчанию стилей для чередующихся строк и столбцов. Кроме того стили, которые можно установить в коде для отдельных строк и ячеек, переопределяют стили по умолчанию.  
  
 Дополнительные сведения о стилях ячеек см. в разделе [стили ячеек в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md). Установка стилей для чередующихся строк, в разделе [как: набор стилей для чередующихся строк Windows Forms управления DataGridView с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md).  
  
 Можно также задать с помощью стилей <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойство влияет на все строки, которые будут добавлены к элементу управления. Дополнительные сведения о шаблоне строк см. в разделе [как: применение шаблонов строк для настройки строк в элементе управления DataGridView Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md).  
  
 Следующие процедуры требуют **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Установка стилей по умолчанию для всех ячеек в элементе управления  
  
1.  Выберите <xref:System.Windows.Forms.DataGridView> управления в конструкторе.  
  
2.  В **свойства** окно, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> свойства. **Построитель стилей ячеек** откроется диалоговое окно.  
  
3.  Определите стиль путем установки свойств, используя **предварительного просмотра** панели, чтобы подтвердить выбранные параметры.  
  
> [!NOTE]
>  Если включены визуальные стили, заголовки строк и столбцов (за исключением <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются текущей темой, переопределяя <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> значения свойств.  
>   
>  Можно установить стили ячеек для нескольких выбранных <xref:System.Windows.Forms.DataGridView> элементы управления с помощью конструктора, но только если они имеют одинаковые значения для свойства стиля ячейки, нужно будет изменить. Если все стили ячеек различаются для этого свойства, **свойства** окна **построитель стилей ячеек** диалоговое окно будет пустым.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Установка стилей по умолчанию для ячеек в отдельных столбцах  
  
1.  Щелкните правой кнопкой мыши <xref:System.Windows.Forms.DataGridView> в конструкторе и выберите **Правка столбцов**.  
  
2.  Выберите столбец из **выбранные столбцы** списка.  
  
3.  В **свойства столбца** сетки, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> свойство. **Построитель стилей ячеек** откроется диалоговое окно.  
  
4.  Определите стиль путем установки свойств, используя **предварительного просмотра** панели, чтобы подтвердить выбранные параметры.  
  
### <a name="to-format-data-in-cells"></a>Форматирование данных в ячейках  
  
1.  Используйте один из приведенных выше процедур для отображения **построитель стилей ячеек** диалоговое окно, связанные со свойством стиль ячейки по умолчанию.  
  
2.  В **построитель стилей ячеек** диалогового окна нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> свойство. **Строка формата** откроется диалоговое окно.  
  
3.  Выберите тип формата, затем измените детали типа (например, число десятичных разрядов), с помощью **пример** флажок, чтобы подтвердить выбранные параметры.  
  
4.  При связывании <xref:System.Windows.Forms.DataGridView> управления к источнику данных, который должен содержать значения null, заполните **значение Null** текстовое поле. Это значение отображается в том случае, если значение ячейки равно пустой ссылке (`Nothing` в Visual Basic) или <xref:System.DBNull.Value?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Стили ячеек элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [Как: Создание проекта приложения Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [Практическое руководство. Добавление элементов управления в формы Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
