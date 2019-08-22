---
title: Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 6d7d867b7c9e83b68589e046565bfb0199692f5f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69658503"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Практическое руководство. Установка стилей для ячейки по умолчанию и форматов данных в элементе управления DataGridView формы Windows Forms с помощью конструктора

<xref:System.Windows.Forms.DataGridView> Элемент управления позволяет задавать стили ячеек по умолчанию и форматы данных ячеек для всего элемента управления, для конкретных столбцов, для заголовков строк и столбцов, а также для чередующихся строк для создания результата книги. Стили по умолчанию, заданные для всего элемента управления, переопределяются стилями по умолчанию, заданными для столбцов и чередующихся строк. Кроме того, стили, заданные в коде для отдельных строк и ячеек, переопределяют стили по умолчанию.

Дополнительные сведения о стилях ячеек см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md). Чтобы задать стили для чередующихся строк, см [. раздел как Установите чередующиеся стили строк для элемента управления Windows Forms DataGridView с помощью конструктора](set-alternating-row-styles-for-the-datagrid-using-the-designer.md).

Можно также задать стили с помощью <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> свойства, чтобы повлиять на все строки, которые будут добавлены в элемент управления. Дополнительные сведения о шаблоне строк см. в [разделе как Используйте шаблон строки для настройки строк в элементе управления](use-the-row-template-to-customize-rows-in-the-datagrid.md)Windows Forms DataGridView.

Для следующих процедур требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.

### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Установка стилей по умолчанию для всех ячеек в элементе управления

1. <xref:System.Windows.Forms.DataGridView> Выберите элемент управления в конструкторе.

2. В окне **Свойства** нажмите кнопку![с многоточием (кнопку с многоточием (...) в окно свойств Visual Studio. <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>](./media/visual-studio-ellipsis-button.png)) рядом со свойством, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>или <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> . Откроется диалоговое окно Построитель полей.

3. Определите стиль, задав свойства с помощью панели **предварительного просмотра** , чтобы подтвердить выбор.

> [!NOTE]
> Если включены стили оформления, заголовки строк и столбцов (кроме <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>) автоматически определяются по текущей теме, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> переопределяя значения свойств и <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> .
>
> Стили ячеек для нескольких выбранных <xref:System.Windows.Forms.DataGridView> элементов управления можно задать с помощью конструктора, но только в том случае, если они имеют одинаковые значения для свойства стиля ячейки, которое необходимо изменить. Если стили ячеек для этого свойства различаются, окна **свойств** диалогового окна " **Построитель** стилей" будут пустыми.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Установка стилей по умолчанию для ячеек в отдельных столбцах

1. Щелкните <xref:System.Windows.Forms.DataGridView> правой кнопкой мыши элемент управления в конструкторе и выберите пункт **изменить столбцы**.

2. Выберите столбец из списка **Выбранные столбцы** .

3. В сетке **Свойства столбца** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> со свойством. Откроется диалоговое окно Построитель полей.

4. Определите стиль, задав свойства с помощью панели **предварительного просмотра** , чтобы подтвердить выбор.

### <a name="to-format-data-in-cells"></a>Форматирование данных в ячейках

1. Используйте одну из описанных выше процедур для вывода диалогового окна «Построитель стилей ячеек», связанного со свойством стиля ячейки по умолчанию.

2. В диалоговом окне Построитель полей, нажмите кнопку с многоточием![(кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> свойством. Откроется диалоговое окно **Формат строки** .

3. Выберите тип формата, затем измените сведения о типе (например, число отображаемых десятичных знаков), используя **образец** для подтверждения выбора.

4. При привязке <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных, который, скорее всего, будет содержать значения NULL, заполните текстовое поле **значение NULL** . Это значение отображается, если значение ячейки равно пустой ссылке (`Nothing` в Visual Basic) или. <xref:System.DBNull.Value?displayProperty=nameWithType>

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Стили ячеек элемента управления DataGridView в Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Практическое руководство. Установка чередующихся стилей строк для элемента управления Windows Forms DataGridView с помощью конструктора](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).
- [Практическое руководство. Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md)
