---
title: Практическое руководство. Форматирование элемента управления DataGrid в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: d6e31d55ab271376501064c3aa9a9ce38c14063d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039741"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Форматирование элемента управления DataGrid в формах Windows Forms с помощью конструктора

> [!NOTE]
> Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Применение различных цветов к различным частям <xref:System.Windows.Forms.DataGrid> элемента управления помогает упростить чтение и анализ информации. Цвет может применяться к строкам и столбцам. Строки и столбцы также можно скрыть или показать по собственному усмотрению.

Существует три основных аспекта форматирования <xref:System.Windows.Forms.DataGrid> элемента управления:

- Можно задать свойства, чтобы установить стиль по умолчанию, в котором будут отображаться данные.

- С этого основания можно настроить способ отображения определенных таблиц во время выполнения.

- Наконец, можно изменить столбцы, отображаемые в сетке данных, а также цвета и другие отображаемые параметры форматирования.

В качестве начального шага при форматировании сетки данных можно задать свойства <xref:System.Windows.Forms.DataGrid> самого себя. Эти варианты цвета и формата образуют основу, из которой можно вносить изменения в зависимости от отображаемых таблиц и столбцов данных.

Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGrid> элемент управления. Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms. В Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> элемент управления не находится на **панели элементов** по умолчанию. Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов на панель элементов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).


### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Установка стиля по умолчанию для элемента управления DataGrid

1. Выберите элемент управления <xref:System.Windows.Forms.DataGrid>.

2. В окне **Свойства** задайте следующие свойства, если это уместно.

    |Свойство.|Описание|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|`BackColor` Свойство определяет цвет строк сетки с четными номерами. Если для <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства задан другой цвет, для каждой другой строки задается этот новый цвет (строки 1, 3, 5 и т. д.).|
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Цвет фона строк сетки с четными номерами (строки 0, 2, 4, 6 и т. д.).|
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|В то время как <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> <xref:System.Windows.Forms.DataGrid.BackColor%2A> и определяют цвет строк в сетке, свойство определяет цвет области за пределами области строк, которая отображается только при прокрутке сетки вниз, или если только несколько строк содержится в сетке.|
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
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Цвет переднего плана для заголовков столбцов сетки, включая текст заголовка столбца и знаки плюса (+) и минус (-), которые расширяют и сворачиваются строки при отображении нескольких связанных таблиц.|
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
    > При настройке цветов элементов управления можно сделать этот элемент недоступным из-за плохого выбора цвета (например, красный и зеленый). Чтобы избежать этой проблемы, используйте цвета, доступные в палитре **системные цвета** .

    Для следующей процедуры требуется <xref:System.Windows.Forms.DataGrid> элемент управления, привязанный к таблице данных. Дополнительные сведения см. в разделе [Практическое руководство. Привязка Windows Forms элемента управления DataGrid к источнику](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)данных.

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Задание стиля таблицы и столбца таблицы данных во время разработки

1. <xref:System.Windows.Forms.DataGrid> Выберите элемент управления в форме.

2. В окне **Свойства** выберите <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойство и нажмите кнопку **с многоточием** ![(...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)).

3. В диалоговом окне **Редактор коллекции DataGridTableStyle** нажмите кнопку **Добавить** , чтобы добавить стиль таблицы в коллекцию.

     С помощью **редактора коллекции DataGridTableStyle**можно добавлять и удалять стили таблиц, задавать свойства отображения и макета, а также задавать имя сопоставления для стилей таблиц.

4. Задайте для <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойства имя сопоставления для каждого стиля таблицы.

     Имя сопоставления используется для указания того, какой стиль таблицы следует использовать с таблицей.

5. В **редакторе коллекции DataGridTableStyle**выберите <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> свойство и нажмите кнопку с многоточием (![...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png))

6. В диалоговом окне **Редактор коллекции DataGridColumnStyle** добавьте стили столбцов к созданному стилю таблицы.

     С помощью **редактора коллекции DataGridColumnStyle**можно добавлять и удалять стили столбцов, задавать свойства отображения и макета, а также задавать имя сопоставления и строки форматирования для столбцов данных.

    > [!NOTE]
    > Дополнительные сведения о строках форматирования см. в разделе [Типы форматирования](../../../standard/base-types/formatting-types.md).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Практическое руководство. Удаление или скрытие столбцов в элементе управления Windows Forms DataGrid](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Элемент управления DataGrid](datagrid-control-windows-forms.md)
