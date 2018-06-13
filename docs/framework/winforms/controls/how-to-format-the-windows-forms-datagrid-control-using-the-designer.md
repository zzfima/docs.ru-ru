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
ms.openlocfilehash: c6069c2557ac220a37db7f16917a029d6fa49522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541324"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Практическое руководство. Форматирование элемента управления DataGrid в формах Windows Forms с помощью конструктора
> [!NOTE]
>  Элемент управления <xref:System.Windows.Forms.DataGridView> заменяет элемент управления <xref:System.Windows.Forms.DataGrid> и расширяет его функциональные возможности; однако при необходимости элемент управления <xref:System.Windows.Forms.DataGrid> можно сохранить для обратной совместимости и использования в будущем. Дополнительные сведения см. в разделе [Различия элементов управления DataGridView и DataGrid в Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Выделение разными цветами различных частей <xref:System.Windows.Forms.DataGrid> управления позволяет облегчить чтение и понимание сведений. Цвет могут применяться к строкам и столбцам. Строки и столбцы можно также скрывать или отображать по необходимости.  
  
 Состоит из трех основных этапов форматирования <xref:System.Windows.Forms.DataGrid> управления:  
  
-   Можно установить свойства, чтобы создать стиль по умолчанию, в котором отображаются данные.  
  
-   На этой основе можно настроить способ отображения некоторых таблицах во время выполнения.  
  
-   Наконец можно изменить столбцы, которые отображаются в сетке данных, а также цвета и другие элементы, которые отображается.  
  
 На первом этапе форматирования сетки данных можно задать свойства <xref:System.Windows.Forms.DataGrid> сам. Эти параметры цветов и форматирования составляют основу, из которой затем можно внести изменения в зависимости от данных таблиц и столбцов, отображаемых.  
  
 В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGrid> элемента управления. Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). В [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> управления не находится в **элементов** по умолчанию. Дополнительные сведения см. в разделе [как: Добавление элементов в область элементов](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Чтобы создать стиль по умолчанию для элемента управления DataGrid  
  
1.  Выберите элемент управления <xref:System.Windows.Forms.DataGrid>.  
  
2.  В **свойства** задайте следующие свойства, соответствующим образом.  
  
    |Свойство.|Описание|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|`BackColor` Свойство определяет цвет строк сетки с четными номерами. При задании <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> другой цвет, все остальные строки является свойство цветом (строки 1, 3, 5 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Цвет фона строк сетки с четными номерами (строки 0, 2, 4, 6 и т. д.).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|В то время как <xref:System.Windows.Forms.DataGrid.BackColor%2A> и <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> свойства определяет цвет строк в сетке <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> свойство определяет цвет области за пределами области строк, которая видна только нижней сетке выполняется прокрутка или если только небольшое число строк содержащиеся в сетке.|  
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
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Основной цвет заголовков столбцов сетки, включая текст заголовка столбца и знак плюс (+) и минуса (-) глифы, которые можно разворачивать и сворачивать строки при нескольких связанных таблиц отображаются.|  
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
    >  При настройке цветов элементов управления, можно сделать элемент управления недоступен из-за выбор неудачных цветов (например, красный и зеленый). Используйте цвета на **системных цветов** палитру цветов, чтобы избежать этой проблемы.  
  
     В следующей процедуре требуется <xref:System.Windows.Forms.DataGrid> элемент управления привязан к таблице данных. Дополнительные сведения см. в разделе [как: привязка элемента управления DataGrid в Windows Forms к источнику данных](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Чтобы задать стиль таблицы и столбца таблицы данных во время разработки  
  
1.  Выберите <xref:System.Windows.Forms.DataGrid> элемент управления в форме.  
  
2.  В **свойства** выберите <xref:System.Windows.Forms.DataGrid.TableStyles%2A> свойство и нажмите кнопку **многоточие** (![экрана VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) кнопки.  
  
3.  В **редактор коллекции DataGridTableStyle** диалоговое окно, нажмите кнопку **добавить** Добавление стиля таблицы в коллекцию.  
  
     С **редактор коллекции DataGridTableStyle**, можно добавить и удалить таблицы стилей, отображения набора и свойства макета и набор сопоставление имени для стилей таблиц.  
  
4.  Задать <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> свойства имя сопоставления для каждого стиля таблицы.  
  
     Имя сопоставления позволяет указать, какой стиль таблицы следует использовать в какой таблице.  
  
5.  В **редактор коллекции DataGridTableStyle**выберите <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> свойство и нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton ")).  
  
6.  В **редактор коллекции DataGridColumnStyle** диалогового окна поле, добавьте стили столбцов в созданный стиль таблицы.  
  
     С **редактор коллекции DataGridColumnStyle**, можно добавлять и удалять стили столбцов, задавать свойства отображения и макета и задайте имя сопоставления и строки форматирования для данных столбцов.  
  
    > [!NOTE]
    >  Дополнительные сведения о строках форматирования см. в разделе [типы форматирования](../../../../docs/standard/base-types/formatting-types.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [Практическое руководство. Удаление или скрытие столбцов элемента управления DataGridView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [Элемент управления DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
