---
title: Установка стилей ячеек и форматов данных по умолчанию для элемента управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: ca602fa15e4648550bfa171a9c3abd057e930eca
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731369"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора

Элемент управления <xref:System.Windows.Forms.DataGridView> позволяет указать стили ячеек по умолчанию и форматы данных ячеек для всего элемента управления, для конкретных столбцов, для заголовков строк и столбцов, а также для чередующихся строк, чтобы создать результат книги учета. Стили по умолчанию, заданные для всего элемента управления, переопределяются стилями по умолчанию, заданными для столбцов и чередующихся строк. Кроме того, стили, заданные в коде для отдельных строк и ячеек, переопределяют стили по умолчанию.

Дополнительные сведения о стилях ячеек см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md). Сведения о задании стилей для чередующихся строк см. в разделе [как задать чередующиеся стили строк для элемента управления Windows Forms DataGridView с помощью конструктора](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).

Можно также задать стили с помощью свойства <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>, чтобы повлиять на все строки, которые будут добавлены в элемент управления. Дополнительные сведения о шаблоне строк см. в разделе [как использовать шаблон строк для настройки строк в элементе управления Windows Forms DataGridView](use-the-row-template-to-customize-rows-in-the-datagrid.md).

Для следующих процедур требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>. Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Установка стилей по умолчанию для всех ячеек в элементе управления

1. Выберите элемент управления <xref:System.Windows.Forms.DataGridView> в конструкторе.

2. В окне **Свойства** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>. Откроется диалоговое окно **Построитель** полей.

3. Определите стиль, задав свойства с помощью панели **предварительного просмотра** , чтобы подтвердить выбор.

> [!NOTE]
> Если включены стили оформления, заголовки строк и столбцов (за исключением <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются по текущей теме, переопределяя значения свойств <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A>.
>
> Стили ячеек для нескольких выбранных элементов управления <xref:System.Windows.Forms.DataGridView> можно задать с помощью конструктора, но только в том случае, если они имеют одинаковые значения для свойства стиля ячейки, которое необходимо изменить. Если стили ячеек для этого свойства различаются, окна **свойств** диалогового окна " **Построитель** стилей" будут пустыми.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Установка стилей по умолчанию для ячеек в отдельных столбцах

1. Щелкните правой кнопкой мыши элемент управления <xref:System.Windows.Forms.DataGridView> в конструкторе и выберите пункт **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A>. Откроется диалоговое окно **Построитель** полей.

4. Определите стиль, задав свойства с помощью панели **предварительного просмотра** , чтобы подтвердить выбор.

### <a name="to-format-data-in-cells"></a>Форматирование данных в ячейках

1. Используйте одну из описанных выше процедур для вывода диалогового окна « **Построитель** стилей ячеек», связанного со свойством стиля ячейки по умолчанию.

2. В диалоговом окне « **Построитель** полей» нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>. Откроется диалоговое окно **Формат строки** .

3. Выберите тип формата, затем измените сведения о типе (например, число отображаемых десятичных знаков), используя **образец** для подтверждения выбора.

4. При привязке <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных, который, скорее всего, будет содержать значения NULL, заполните текстовое поле **значение NULL** . Это значение отображается, если значение ячейки равно пустой ссылке (`Nothing` в Visual Basic) или <xref:System.DBNull.Value?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Практическое руководство. Добавление элементов управления в формы Windows Forms](how-to-add-controls-to-windows-forms.md)
