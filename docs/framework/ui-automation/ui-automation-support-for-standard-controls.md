---
title: "Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
caps.latest.revision: "11"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 71a5a2e4319debf1a4d8ddd08d7f0979443682b9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ui-automation-support-for-standard-controls"></a>Поддержка автоматизации пользовательского интерфейса для стандартных элементов управления
> [!NOTE]
>  Эта документация предназначена для разработчиков .NET Framework, желающих использовать управляемые классы [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , заданные в пространстве имен <xref:System.Windows.Automation> . Последние сведения о [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]см. в разделе [API автоматизации Windows. Автоматизация пользовательского интерфейса](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
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
|Static|Text|  
|Static|Изображение|  
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
|tooltips_class32|ToolTip|  
|#32774|ToolTip|  
|ReBarWindow32|ToolBar|  
|SysTreeView32|Дерево|  
|SysTreeView32|TreeItem|  
  
 **Примечание.** Элемент управления RichEdit поддерживается только для версий, поставляемых в составе [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (в RichEd20.dll версии 3.1 и более поздних версий и MsftEdit.dll версии 4.1 и более поздних версий).  
  
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
 Элементы управления[!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] предоставляется в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] через поставщики на стороне клиента в UIAutomationClientsideProviders.dll. Эта сборка автоматически регистрируется для использования с приложениями клиента автоматизации пользовательского интерфейса.  
  
 Как правило, элементы управления [!INCLUDE[TLA2#tla_winforms](../../../includes/tla2sharptla-winforms-md.md)] , которые являются управляемыми оболочками для общих элементов управления [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] , поддерживаются [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]. Поддерживаются следующие элементы управления.  
  
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
|ToolBar|  
|ToolTip|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|Веб-браузер|  
  
 Следующие элементы управления предоставляются в [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] только через их поддержку [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]. Некоторые функциональные возможности могут оказаться недоступными.  
  
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
 [UI Automation Control Types](../../../docs/framework/ui-automation/ui-automation-control-types.md)
