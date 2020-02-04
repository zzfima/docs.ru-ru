---
title: Элементы управления Windows Forms и эквивалентные элементы управления WPF
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 729f893a94688f4a1d8b0a770a3624b27ddfe1c1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794081"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a>Элементы управления Windows Forms и эквивалентные элементы управления WPF
Многие элементы управления Windows Forms имеют эквивалентные элементы управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], но некоторые элементы управления Windows Forms не имеют эквивалентов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. В этом разделе сравниваются типы элементов управления, предоставляемые двумя технологиями.  
  
 Вы всегда можете использовать взаимодействие для размещения элементов управления Windows Forms, которые не имеют эквивалентов в приложениях на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 В следующей таблице показано, какие элементы управления и компоненты Windows Forms имеют эквивалентные функции управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
|элемент управления Windows Forms|Эквивалентный элемент управления WPF|Заметки|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox>с использованием композиции.||  
|<xref:System.Windows.Forms.ColorDialog>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> не поддерживает автоматическое завершение.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> и два элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.||  
|<xref:System.Windows.Forms.ErrorProvider>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> или <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.FontDialog>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> не поддерживает дочерние окна.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|Эквивалентный элемент управления отсутствует.|Справка F1 отсутствует. Текст справки «что это такое» заменяется подсказками.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Прокрутка встроена в контейнерные элементы управления.|  
|<xref:System.Windows.Forms.ImageList>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|Эквивалентный элемент управления отсутствует.|Для размещения гиперссылок внутри содержимого нефиксированного формата можно использовать класс <xref:System.Windows.Documents.Hyperlink>.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|Элемент управления <xref:System.Windows.Controls.ListView> предоставляет представление сведений только для чтения.|  
|<xref:System.Windows.Forms.MaskedTextBox>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|стиль <xref:System.Windows.Controls.Menu> элементов управления может приблизительно повлиять на поведение и внешний вид класса <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType>.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> и два элемента управления <xref:System.Windows.Controls.Primitives.RepeatButton>.||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|Класс <xref:Microsoft.Win32.OpenFileDialog> является [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ной оболочкой вокруг элемента управления Win32.|  
|<xref:System.Windows.Forms.PageSetupDialog>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|Эквивалентный элемент управления отсутствует.||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|Класс <xref:Microsoft.Win32.SaveFileDialog> является [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]ной оболочкой вокруг элемента управления Win32.|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar>с использованием композиции.||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar>с использованием композиции.||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar>с использованием композиции.||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar>с использованием композиции.||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|Прокрутка встроена в контейнерные элементы управления.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>|Элемент управления <xref:System.Windows.Controls.Frame> может размещать HTML-страницы.<br /><br /> Начиная с .NET Framework 3,5 с пакетом обновления 1 (SP1), элемент управления <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> может размещать HTML-страницы и также выполнять резервное копирование элемента управления <xref:System.Windows.Controls.Frame>.|  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Конструктор WPF для разработчиков Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))
- [Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [Миграция и взаимодействие систем](migration-and-interoperability.md)
