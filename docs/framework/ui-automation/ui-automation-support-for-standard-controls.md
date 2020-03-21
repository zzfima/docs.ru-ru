---
title: Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 36028d589e98177f6a0e83092edd656860b1a8d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179853"
---
# <a name="ui-automation-support-for-standard-controls"></a>Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
> [!NOTE]
> Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](/windows/win32/winauto/entry-uiauto-win32).  
  
 Эта тема содержит [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] информацию о поддержке [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]стандартных элементов управления в приложениях, разработанных для платформ Форм Win32 и Windows.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>
## <a name="windows-presentation-foundation-controls"></a>Элементы представления Windows Presentation Foundation  
 Все элементы управления [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] , предоставляющие сведения или поддержку для взаимодействия с пользователем, имеют полную собственную поддержку [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Другие элементы, такие как панели, не являются видимыми для [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
<a name="Win32_Controls"></a>
## <a name="win32-controls"></a>Элементы управления Win32  
 Большинство элементов управления Win32 подвергаются [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через клиентов-поставщиков в UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Полная поддержка обеспечивается только для элементов управления из версии 6 *ComCtrl32.dll*.  
  
 Поддерживаются следующие элементы управления.  
  
|Имя класса|Тип элемента управления|  
|----------------|------------------|  
|Кнопка|Кнопка|  
|Кнопка|RadioButton|  
|Кнопка|Группа|  
|Кнопка|CheckBox|  
|Кнопка|Hyperlink|  
|Кнопка|SplitButton|  
|Кнопка|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Изменить|Документ|  
|Изменить|Изменить|  
|SysLink|Hyperlink|  
|Статические|текст|  
|Статические|Образ —|  
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
|RichEdit20A|Документ|  
|RichEdit20W|Документ|  
|RichEdit50W|Документ|  
|ScrollBar|Ползунок|  
|msctls_trackbar32|Ползунок|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|Вкладка|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|Кнопка|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|Разделитель|  
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|Панель инструментов|  
|SysTreeView32|Дерево|  
|SysTreeView32|TreeItem|  
  
 **Заметка** Управление RichEdit поддерживается только для версий, поставляемых с Windows Vista (в версии RichEd20.dll 3.1 и позже, и MsftEdit.dll версии 4.1 и позже).  
  
 Следующие элементы управления не поддерживаются.  
  
|Имя класса|Тип элемента управления|  
|----------------|------------------|  
|SysAnimate32|Образ —|  
|SysPager|Spinner|  
|SysDateTimePick32|Другой|  
|SysMonthCal32|Календарь|  
|MS_WINNOTE|Подсказка|  
|VBBubble|Подсказка|  
|ScrollBar (при использовании в качестве отдельного элемента управления)|Ползунок|  
|SuperGrid|Другой|  
  
<a name="Windows_Forms_Controls"></a>
## <a name="windows-forms-controls"></a>Элементы управления Windows Forms  
 Элементы управления Windows [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] Forms подвергаются воздействию через поставщиков со стороны клиентов в UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Как правило, элементы управления Windows Forms, управляемые обертками для общих элементов управления Win32, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]поддерживаются. Поддерживаются следующие элементы управления.  
  
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
|Панель инструментов|  
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Веб-браузер|  
  
 Следующие элементы [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] управления подвергаются только через их поддержку Microsoft Active Accessibility. Некоторые функциональные возможности могут оказаться недоступными.  
  
|Имя элемента управления|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Форма|  
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
  
## <a name="see-also"></a>См. также раздел

- [Типы элементов управления автоматизации пользовательского интерфейса](ui-automation-control-types.md)
