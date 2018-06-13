---
title: Стили и шаблоны элемента DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], DataGrid
- ControlTemplate [WPF], DataGrid
- DataGrid [WPF], styles and templates
- templates [WPF], DataGrid
- styles [WPF], DataGrid
- parts [WPF], DataGrid
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
ms.openlocfilehash: 71c9b08407c6e570b42c4fbb7dc264829b5dc17c
ms.sourcegitcommit: 43924acbdbb3981d103e11049bbe460457d42073
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34457595"
---
# <a name="datagrid-styles-and-templates"></a>Стили и шаблоны элемента DataGrid
В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.DataGrid> элемента управления. Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления. Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="datagrid-parts"></a>Элементы управления DataGrid  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.DataGrid> элемента управления.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Строка, содержащая заголовки столбцов.|  
  
 При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.DataGrid>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>. ( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.DataGrid>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).  Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
 Шаблон по умолчанию для <xref:System.Windows.Controls.DataGrid> содержит <xref:System.Windows.Controls.ScrollViewer> элемента управления. Дополнительные сведения о частях определяется <xref:System.Windows.Controls.ScrollViewer>, в разделе [ScrollViewer стили и шаблоны](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md).  
  
## <a name="datagrid-states"></a>DataGrid состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DataGrid> элемента управления.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|Отключено|CommonStates|Элемент управления отключен.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagridcell-parts"></a>DataGridCell частей  
 <xref:System.Windows.Controls.DataGridCell> Элемент не имеет именованных частей.  
  
## <a name="datagridcell-states"></a>DataGridCell состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DataGridCell> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на ячейку.|  
|Focused|FocusStates|Ячейка имеет фокус.|  
|Без фокуса ввода|FocusStates|Ячейка имеет фокус|  
|Текущие|CurrentStates|Ячейка является текущей.|  
|Регулярное|CurrentStates|Ячейка не является текущей ячейки.|  
|Отображение|InteractionStates|Ячейка находится в режиме отображения.|  
|Редактирование|InteractionStates|Ячейка находится в режиме редактирования.|  
|Selected|SelectionStates|Ячейка выбрана.|  
|Unselected|SelectionStates|Ячейка не выбрана.|  
|InvalidFocused|ValidationStates|Ячейка не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Ячейка не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Ячейка является допустимой.|  
  
## <a name="datagridrow-parts"></a>DataGridRow частей  
 <xref:System.Windows.Controls.DataGridRow> Элемент не имеет именованных частей.  
  
## <a name="datagridrow-states"></a>DataGridRow состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DataGridRow> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на строку.|  
|MouseOver_Editing|CommonStates|Указатель мыши наведен на строку, и строка находится в режиме редактирования.|  
|MouseOver_Selected|CommonStates|Указатель мыши наведен на строку и выбрана строка.|  
|MouseOver_Unfocused_Editing|CommonStates|Указатель мыши наведен на строку, строка находится в режиме редактирования и не имеет фокуса.|  
|MouseOver_Unfocused_Selected|CommonStates|Указатель мыши наведен на строку, строка выбрана и не имеет фокуса.|  
|Normal_AlternatingRow|CommonStates|Строка является чередующейся.|  
|Normal_Editing|CommonStates|Строка находится в режиме редактирования.|  
|Normal_Selected|CommonStates|Выбрана строка.|  
|Unfocused_Editing|CommonStates|Строка находится в режиме редактирования и не имеет фокуса.|  
|Unfocused_Selected|CommonStates|Строка выбрана и не имеет фокуса.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagridrowheader-parts"></a>DataGridRowHeader частей  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Primitives.DataGridRowHeader> элемента.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка строки сверху.|  
|PART_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка строки снизу.|  
  
## <a name="datagridrowheader-states"></a>DataGridRowHeader состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.DataGridRowHeader> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на строку.|  
|MouseOver_CurrentRow|CommonStates|Указатель мыши наведен на строку и текущей строки.|  
|MouseOver_CurrentRow_Selected|CommonStates|Указатель мыши наведен на строку, и строка является текущей и выбранной.|  
|MouseOver_EditingRow|CommonStates|Указатель мыши наведен на строку, и строка находится в режиме редактирования.|  
|MouseOver_Selected|CommonStates|Указатель мыши наведен на строку и выбрана строка.|  
|MouseOver_Unfocused_CurrentRow_Selected|CommonStates|Указатель мыши наведен на строку, строка является текущей и выбранной и не имеет фокуса.|  
|MouseOver_Unfocused_EditingRow|CommonStates|Указатель мыши наведен на строку, строка находится в режиме редактирования и не имеет фокуса.|  
|MouseOver_Unfocused_Selected|CommonStates|Указатель мыши наведен на строку, строка выбрана и не имеет фокуса.|  
|Normal_CurrentRow|CommonStates|Строка является текущей строки.|  
|Normal_CurrentRow_Selected|CommonStates|Строка является текущей строки и выбран.|  
|Normal_EditingRow|CommonStates|Строка находится в режиме редактирования.|  
|Normal_Selected|CommonStates|Выбрана строка.|  
|Unfocused_CurrentRow_Selected|CommonStates|Строка является текущей, выбран и не имеет фокуса.|  
|Unfocused_EditingRow|CommonStates|Строка находится в режиме редактирования и не имеет фокуса.|  
|Unfocused_Selected|CommonStates|Строка выбрана и не имеет фокуса.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagridcolumnheaderspresenter-parts"></a>DataGridColumnHeadersPresenter частей  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> элемента.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Заполнитель для заголовков столбцов.|  
  
## <a name="datagridcolumnheaderspresenter-states"></a>DataGridColumnHeadersPresenter состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|InvalidFocused|ValidationStates|Ячейка не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Ячейка не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Ячейка является допустимой.|  
  
## <a name="datagridcolumnheader-parts"></a>Направление элемента DataGridColumnHeader частей  
 В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> элемента.  
  
|Отделение|Тип|Описание|  
|-|-|-|  
|PART_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка столбца слева.|  
|PART_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка столбца справа.|  
  
## <a name="datagridcolumnheader-states"></a>Направление элемента DataGridColumnHeader состояний  
 В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.DataGridColumnHeader> элемента.  
  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|-|-|-|  
|Норм.|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Нажато|CommonStates|Элемент управления нажат.|  
|SortAscending|SortStates|Столбец сортируется в порядке возрастания.|  
|SortDescending|SortStates|Столбец сортируется в порядке убывания.|  
|Без сортировки|SortStates|Столбец не отсортирован.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## <a name="datagrid-controltemplate-example"></a>Пример шаблона элемента управления DataGrid  
 В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.DataGrid> элемента управления и его связанных типов.  
  
 [!code-xaml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 В предыдущем примере используется один или несколько из следующих ресурсов.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Стили и шаблоны элемента управления](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
