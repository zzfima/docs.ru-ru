---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: c59352f908c5f4a1fd2ca6dd631d26bb5d69f09a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441221"
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
  
 Полная поддержка предоставляется только для элементов управления с версии 6 ComCtrl32.dll (доступной в [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] и более поздних версиях).  
  
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
|Правка|Document|  
|Правка|Правка|  
|SysLink|Гиперссылка|  
|Статические|Text|  
|Статические|Изображение|  
|SysIPAddress32|Другой|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|Списка|  
|ListBox|Списка|  
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
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|Toolbar|  
|SysTreeView32|Дерево|  
|SysTreeView32|TreeItem|  
  
 **Note** The RichEdit control is supported only for versions shipped with Windows Vista (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).  
  
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
 Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Поддерживаются следующие элементы управления.  
  
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
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Веб-браузер|  
  
 The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for Microsoft Active Accessibility. Некоторые функциональные возможности могут оказаться недоступными.  
  
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
|Разделитель|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>См. также

- [Типы элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types.md)
