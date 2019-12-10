---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 314526c1164f70e6b261df1a6f11ddce2b5fa240
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960081"
---
# <a name="ui-automation-support-for-standard-controls"></a>Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 В этом разделе содержатся сведения о поддержке [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] стандартных элементов управления в приложениях, разработанных для платформ [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]и [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>Элементы представления Windows Presentation Foundation  
 Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Элементы управления Win32  
 Большинство элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Полная поддержка предоставляется только для элементов управления из *ComCtrl32. dll*версии 6.  
  
 Поддерживаются следующие элементы управления.  
  
|Имя класса|Тип элемента управления|  
|----------------|------------------|  
|Кнопка|Кнопка|  
|Кнопка|RadioButton|  
|Кнопка|Группа|  
|Кнопка|CheckBox|  
|Кнопка|Гиперссылка|  
|Кнопка|SplitButton|  
|Кнопка|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Edit|Document|  
|Edit|Edit|  
|SysLink|Гиперссылка|  
|Статические|Текст|  
|Статические|Изображение|  
|SysIPAddress32|Другой|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Список|  
|ListBox|Список|  
|ListBox|ListItem|  
|#32768|Меню|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|Документ. См. примечание.|  
|RichEdit20A|Document|  
|RichEdit20W|Document|  
|RichEdit50W|Document|  
|ScrollBar|Slider|  
|msctls_trackbar32|Slider|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Вкладка|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Кнопка|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Separator|  
|tooltips_class32|Подсказка|  
|#32774|Подсказка|  
|ReBarWindow32|Toolbar|  
|SysTreeView32|Дерево|  
|SysTreeView32|TreeItem|  
  
 **Примечание** . Элемент управления RichEdit поддерживается только для версий, поставляемых с Windows Vista (в библиотеки RICHED20. dll версии 3,1 и более поздних версий и Мсфтедит. dll версии 4,1 и более поздних версий).  
  
 Следующие элементы управления не поддерживаются.  
  
|Имя класса|Тип элемента управления|  
|----------------|------------------|  
|SysAnimate32|Изображение|  
|SysPager|Spinner|  
|SysDateTimePick32|Другой|  
|SysMonthCal32|Календарь|  
|MS_WINNOTE|ToolTip|  
|VBBubble|ToolTip|  
|ScrollBar (при использовании в качестве отдельного элемента управления)|Slider|  
|SuperGrid|Другой|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Элементы управления Windows Forms  
 Windows Forms элементы управления предоставляются для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] с помощью поставщиков на стороне клиента в UIAutomationClientsideProviders. dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Как правило, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]поддерживаются элементы управления Windows Forms, которые являются управляемыми оболочками для [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] стандартных элементов управления. Поддерживаются следующие элементы управления.  
  
|Имя класса|  
|----------------|  
|Кнопка|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|Метка|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|ProgressBar|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Таймер|  
|Toolbar|  
|Подсказка|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Веб-браузер|  
  
 Следующие элементы управления доступны для [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только с помощью поддержки Microsoft Active Accessibility. Некоторые функциональные возможности могут оказаться недоступными.  
  
|Имя элемента|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Form|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|Panel|  
|PictureBox|  
|PrintDocument|  
|PrintPreview-Control|  
|PrintPreview-Dialog|  
|PropertyGrid|  
|UserControl|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|Функции разделения|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>См. также:

- [Типы элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types.md)
