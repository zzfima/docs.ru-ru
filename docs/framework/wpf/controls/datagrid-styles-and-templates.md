---
title: "Стили и шаблоны элемента DataGrid | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ControlTemplate [WPF], DataGrid"
  - "DataGrid [WPF], стили и шаблоны"
  - "части [WPF], DataGrid"
  - "состояния [WPF], DataGrid"
  - "стили [WPF], DataGrid"
  - "шаблоны [WPF], DataGrid"
ms.assetid: 9cb31d63-f148-4d25-b079-816e73f988c7
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Стили и шаблоны элемента DataGrid
В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.DataGrid>.  Предусмотренный по умолчанию шаблон <xref:System.Windows.Controls.ControlTemplate> можно изменить, чтобы придать элементу управления уникальный внешний вид.  Дополнительные сведения см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## Части DataGrid  
 В следующей таблице перечислены именованные части элемента управления <xref:System.Windows.Controls.DataGrid>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_ColumnHeadersPresenter|<xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>|Строка, содержащая заголовки столбцов.|  
  
 При создании шаблона <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.DataGrid> шаблон может содержать часть <xref:System.Windows.Controls.ItemsPresenter> в элементе управления <xref:System.Windows.Controls.ScrollViewer>.  \(Элемент управления <xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в элементе управления <xref:System.Windows.Controls.DataGrid>; элемент управления <xref:System.Windows.Controls.ScrollViewer> обеспечивает прокрутку в элементе управления\).  Если элемент управления <xref:System.Windows.Controls.ItemsPresenter> не является непосредственным дочерним элементом элемента управления <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить элементу управления <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.  
  
 Шаблон элемента управления <xref:System.Windows.Controls.DataGrid> по умолчанию содержит элемент управления <xref:System.Windows.Controls.ScrollViewer>.  Дополнительные сведения о частях, определенных элементом управления <xref:System.Windows.Controls.ScrollViewer>, см. в разделе [Стили и шаблоны элемента ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md).  
  
## Состояния DataGrid  
 В следующей таблице перечислены визуальные состояния элемента управления <xref:System.Windows.Controls.DataGrid>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|Disabled|CommonStates|Элемент управления отключен.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## Части DataGridCell  
 Элемент <xref:System.Windows.Controls.DataGridCell> не имеет именованных частей.  
  
## Состояния DataGridCell  
 В следующей таблице перечислены визуальные состояния элемента <xref:System.Windows.Controls.DataGridCell>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на ячейку.|  
|Focused|FocusStates|Ячейка имеет фокус.|  
|Unfocused|FocusStates|Ячейка не имеет фокуса.|  
|Текущий|CurrentStates|Ячейка является текущей.|  
|Регулярное|CurrentStates|Ячейка не является текущей.|  
|Отображение|InteractionStates|Ячейка находится в режиме отображения.|  
|Редактирование|InteractionStates|Ячейка находится в режиме правки.|  
|Выбран|SelectionStates|Ячейка выбрана.|  
|Не выбран|SelectionStates|Ячейка не выбрана.|  
|InvalidFocused|ValidationStates|Ячейка не является допустимой и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Ячейка не является допустимой и не имеет фокуса.|  
|Valid|ValidationStates|Ячейка является допустимой.|  
  
## Части DataGridRow  
 Элемент <xref:System.Windows.Controls.DataGridRow> не имеет именованных частей.  
  
## Состояния DataGridRow  
 В следующей таблице перечислены визуальные состояния элемента <xref:System.Windows.Controls.DataGridRow>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на строку.|  
|MouseOver\_Editing|CommonStates|Указатель мыши наведен на строку, и строка находится в режиме правки.|  
|MouseOver\_Selected|CommonStates|Указатель мыши наведен на строку, и строка выбрана.|  
|MouseOver\_Unfocused\_Editing|CommonStates|Указатель мыши наведен на строку, строка находится в режиме правки и не имеет фокуса.|  
|MouseOver\_Unfocused\_Selected|CommonStates|Указатель мыши наведен на строку, строка выбрана и не имеет фокуса.|  
|Normal\_AlternatingRow|CommonStates|Строка является чередующейся.|  
|Normal\_Editing|CommonStates|Строка находится в режиме правки.|  
|Normal\_Selected|CommonStates|Строка выбрана.|  
|Unfocused\_Editing|CommonStates|Строка находится в режиме правки и не имеет фокуса.|  
|Unfocused\_Selected|CommonStates|Строка выбрана и не имеет фокуса.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## Части DataGridRowHeader  
 В следующей таблице перечислены именованные части элемента <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_TopHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка строки сверху.|  
|PART\_BottomHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка строки снизу.|  
  
## Состояния DataGridRowHeader  
 В следующей таблице перечислены визуальные состояния элемента <xref:System.Windows.Controls.Primitives.DataGridRowHeader>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши наведен на строку.|  
|MouseOver\_CurrentRow|CommonStates|Указатель мыши наведен на строку, и строка является текущей.|  
|MouseOver\_CurrentRow\_Selected|CommonStates|Указатель мыши наведен на строку, и строка является текущей и выбранной.|  
|MouseOver\_EditingRow|CommonStates|Указатель мыши наведен на строку, и строка находится в режиме правки.|  
|MouseOver\_Selected|CommonStates|Указатель мыши наведен на строку, и строка выбрана.|  
|MouseOver\_Unfocused\_CurrentRow\_Selected|CommonStates|Указатель мыши наведен на строку, строка является текущей и выбранной и не имеет фокуса.|  
|MouseOver\_Unfocused\_EditingRow|CommonStates|Указатель мыши наведен на строку, строка находится в режиме правки и не имеет фокуса.|  
|MouseOver\_Unfocused\_Selected|CommonStates|Указатель мыши наведен на строку, строка выбрана и не имеет фокуса.|  
|Normal\_CurrentRow|CommonStates|Строка является текущей.|  
|Normal\_CurrentRow\_Selected|CommonStates|Строка является текущей и выбранной.|  
|Normal\_EditingRow|CommonStates|Строка находится в режиме правки.|  
|Normal\_Selected|CommonStates|Строка выбрана.|  
|Unfocused\_CurrentRow\_Selected|CommonStates|Строка является текущей, строка выбрана и не имеет фокуса.|  
|Unfocused\_EditingRow|CommonStates|Строка находится в режиме правки и не имеет фокуса.|  
|Unfocused\_Selected|CommonStates|Строка выбрана и не имеет фокуса.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## Части DataGridColumnHeadersPresenter  
 В следующей таблице перечислены именованные части элемента <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_FillerColumnHeader|<xref:System.Windows.Controls.Primitives.DataGridColumnHeader>|Заполнитель для заголовков столбцов.|  
  
## Состояния DataGridColumnHeadersPresenter  
 В следующей таблице перечислены визуальные состояния элемента <xref:System.Windows.Controls.Primitives.DataGridColumnHeadersPresenter>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|InvalidFocused|ValidationStates|Ячейка не является допустимой и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Ячейка не является допустимой и не имеет фокуса.|  
|Valid|ValidationStates|Ячейка является допустимой.|  
  
## Части DataGridColumnHeader  
 В следующей таблице перечислены именованные части элемента <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
||||  
|-|-|-|  
|Часть|Тип|Описание|  
|PART\_LeftHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка столбца слева.|  
|PART\_RightHeaderGripper|<xref:System.Windows.Controls.Primitives.Thumb>|Элемент, используемый для изменения размера заголовка столбца справа.|  
  
## Состояния DataGridColumnHeader  
 В следующей таблице перечислены визуальные состояния элемента <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.  
  
||||  
|-|-|-|  
|Имя VisualState|Имя VisualStateGroup|Описание|  
|Обычные|CommonStates|Состояние по умолчанию.|  
|MouseOver|CommonStates|Указатель мыши расположен в элементе управления.|  
|Pressed|CommonStates|Элемент управления нажат.|  
|SortAscending|SortStates|Столбец сортируется в порядке возрастания.|  
|SortDescending|SortStates|Столбец сортируется в порядке убывания.|  
|Unsorted|SortStates|Столбец не сортируется.|  
|InvalidFocused|ValidationStates|Элемент управления не является допустимым и имеет фокус.|  
|InvalidUnfocused|ValidationStates|Элемент управления не является допустимым и не имеет фокуса.|  
|Valid|ValidationStates|Элемент управления является допустимым.|  
  
## Пример шаблона ControlTemplate элемента управления DataGrid  
 В следующем примере показано, как определить шаблон <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.DataGrid> и связанных с ним типов.  
  
 [!code-xml[ControlTemplateExamples#DataGrid](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/datagrid.xaml#datagrid)]  
  
 В предыдущем примере используется один или несколько следующих ресурсов.  
  
 [!code-xml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Полный пример см. по адресу          [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041) .  
  
## См. также  
 <xref:System.Windows.FrameworkElement.Style%2A>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Стили и шаблоны элемента Control](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)   
 [Настройка элементов управления](../../../../docs/framework/wpf/controls/control-customization.md)   
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)