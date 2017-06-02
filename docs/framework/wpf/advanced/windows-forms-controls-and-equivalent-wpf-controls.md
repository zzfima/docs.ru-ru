---
title: "Элементы управления Windows Forms и эквивалентные элементы управления WPF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "взаимодействие [WPF], Windows Forms"
  - "Windows Forms [WPF], взаимодействие с"
  - "Windows Forms, взаимодействие с WPF"
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 27
---
# Элементы управления Windows Forms и эквивалентные элементы управления WPF
Многие элементы управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют эквивалентные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], но некоторые элементы [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] не имеют эквивалентов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  В этом разделе сравниваются типы элементов управления, предоставляемых двумя технологиями.  
  
 Можно всегда использовать взаимодействие для размещения элементов управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)], не имеющих эквивалентов в приложениях, основанных на [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В следующей таблице показано, какие элементы управления и компоненты [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] имеют эквивалентные по функциональности элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
|Элемент управления Windows Forms|Эквивалентный элемент управления WPF|Заметки|  
|--------------------------------------|------------------------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox> с композицией.||  
|<xref:System.Windows.Forms.ColorDialog>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> не поддерживает автозаполнение.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|Элементы управления <xref:System.Windows.Controls.TextBox> и два элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.||  
|<xref:System.Windows.Forms.ErrorProvider>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|Элементы управления <xref:System.Windows.Controls.WrapPanel> или <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.FontDialog>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> не поддерживает дочерние окна.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|Эквивалент отсутствует.|Отсутствует справка F1. "  Справка "Что это такое?" заменяется всплывающей подсказкой.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Прокрутка встроена в контейнерные элементы управления.|  
|<xref:System.Windows.Forms.ImageList>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|Эквивалент отсутствует.|Для хранения гиперссылок в содержимом потока можно использовать класс <xref:System.Windows.Documents.Hyperlink>.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|Элемент управления <xref:System.Windows.Controls.ListView> предоставляет просмотр сведений только для чтения.|  
|<xref:System.Windows.Forms.MaskedTextBox>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|Стили элемента управления <xref:System.Windows.Controls.Menu> могут аппроксимировать поведение и внешний вид класса <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=fullName>.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.NumericUpDown>|Элементы управления <xref:System.Windows.Controls.TextBox> и два элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|Класс <xref:Microsoft.Win32.OpenFileDialog> — это программа\-оболочка [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для элемента управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].|  
|<xref:System.Windows.Forms.PageSetupDialog>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|Эквивалент отсутствует.||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|Класс <xref:Microsoft.Win32.SaveFileDialog> — это программа\-оболочка [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для элемента управления [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar> с композицией.||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar> с композицией.||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar> с композицией.||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar> с композицией.||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Прокрутка встроена в контейнерные элементы управления.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=fullName>|В элементе управления <xref:System.Windows.Controls.Frame> можно размещать HTML\-страницы.<br /><br /> Начиная с версии [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], в элементе управления <xref:System.Windows.Controls.WebBrowser?displayProperty=fullName> можно размещать HTML\-страницы; этот элемент управления также можно использовать вместо элемента управления <xref:System.Windows.Controls.Frame>.|  
  
## См. также  
 <xref:System.Windows.Forms.Integration.ElementHost>   
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>   
 [Конструктор WPF для разработчиков Windows Forms](http://msdn.microsoft.com/ru-ru/47ad0909-e89b-4996-b4ac-874d929f94ca)   
 [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)   
 [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)   
 [Миграция и взаимодействие систем](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)