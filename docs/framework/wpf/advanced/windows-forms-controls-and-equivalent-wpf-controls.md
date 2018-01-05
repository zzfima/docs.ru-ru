---
title: "Элементы управления Windows Forms и эквивалентные элементы управления WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04807b849af07a6882689e98ca9ca57d4b6840ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="36e9e-102">Элементы управления Windows Forms и эквивалентные элементы управления WPF</span><span class="sxs-lookup"><span data-stu-id="36e9e-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="36e9e-103">Многие [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления имеют эквивалента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элементы управления, но некоторые [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы не имеют эквивалентов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="36e9e-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="36e9e-104">В этом разделе сравниваются типы элементов управления, предоставляемые две технологии.</span><span class="sxs-lookup"><span data-stu-id="36e9e-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="36e9e-105">Вы всегда можете использовать взаимодействие для размещения [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементов управления, которые не имеют эквивалентов в вашей [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-приложений на основе.</span><span class="sxs-lookup"><span data-stu-id="36e9e-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="36e9e-106">В следующей таблице показаны которой [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элементы управления и компоненты имеют эквивалента [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] управления функцией.</span><span class="sxs-lookup"><span data-stu-id="36e9e-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="36e9e-107">элемент управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36e9e-107">Windows Forms control</span></span>|<span data-ttu-id="36e9e-108">Эквивалентный элемент управления WPF</span><span class="sxs-lookup"><span data-stu-id="36e9e-108">WPF equivalent control</span></span>|<span data-ttu-id="36e9e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="36e9e-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="36e9e-110">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="36e9e-111"><xref:System.Windows.Controls.ListBox>с помощью композиции.</span><span class="sxs-lookup"><span data-stu-id="36e9e-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="36e9e-112">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="36e9e-113"><xref:System.Windows.Controls.ComboBox>не поддерживает автозаполнение.</span><span class="sxs-lookup"><span data-stu-id="36e9e-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="36e9e-114"><xref:System.Windows.Controls.TextBox>и двумя <xref:System.Windows.Controls.Primitives.RepeatButton> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="36e9e-115">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="36e9e-116"><xref:System.Windows.Controls.WrapPanel> или <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="36e9e-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="36e9e-117">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="36e9e-118">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="36e9e-119"><xref:System.Windows.Window>не поддерживает дочерние окна.</span><span class="sxs-lookup"><span data-stu-id="36e9e-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="36e9e-120">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-120">No equivalent control.</span></span>|<span data-ttu-id="36e9e-121">Отсутствует справка F1.</span><span class="sxs-lookup"><span data-stu-id="36e9e-121">No F1 Help.</span></span> <span data-ttu-id="36e9e-122">«Что это такое» справки заменяется всплывающей подсказкой.</span><span class="sxs-lookup"><span data-stu-id="36e9e-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="36e9e-123">Прокрутка встроена в контейнерные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="36e9e-124">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="36e9e-125">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-125">No equivalent control.</span></span>|<span data-ttu-id="36e9e-126">Можно использовать <xref:System.Windows.Documents.Hyperlink> класса для хранения гиперссылок в содержимом нефиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="36e9e-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="36e9e-127"><xref:System.Windows.Controls.ListView> Управления содержит представления сведения только для чтения.</span><span class="sxs-lookup"><span data-stu-id="36e9e-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="36e9e-128">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="36e9e-129"><xref:System.Windows.Controls.Menu>стили элемента управления могут использоваться для аппроксимации поведение и внешний вид <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> класса.</span><span class="sxs-lookup"><span data-stu-id="36e9e-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="36e9e-130">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="36e9e-131"><xref:System.Windows.Controls.TextBox>и двумя <xref:System.Windows.Controls.Primitives.RepeatButton> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="36e9e-132"><xref:Microsoft.Win32.OpenFileDialog> Класс [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] оболочка [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="36e9e-133">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="36e9e-134">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="36e9e-135">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="36e9e-136">Эквивалент отсутствует.</span><span class="sxs-lookup"><span data-stu-id="36e9e-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="36e9e-137"><xref:Microsoft.Win32.SaveFileDialog> Класс [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] оболочка [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="36e9e-138"><xref:System.Windows.Controls.ToolBar>с помощью композиции.</span><span class="sxs-lookup"><span data-stu-id="36e9e-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="36e9e-139"><xref:System.Windows.Controls.ToolBar>с помощью композиции.</span><span class="sxs-lookup"><span data-stu-id="36e9e-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="36e9e-140"><xref:System.Windows.Controls.ToolBar>с помощью композиции.</span><span class="sxs-lookup"><span data-stu-id="36e9e-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="36e9e-141"><xref:System.Windows.Controls.ToolBar>с помощью композиции.</span><span class="sxs-lookup"><span data-stu-id="36e9e-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="36e9e-142">Прокрутка встроена в контейнерные элементы управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="36e9e-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="36e9e-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="36e9e-144"><xref:System.Windows.Controls.Frame> Элемент управления может содержать HTML-страниц.</span><span class="sxs-lookup"><span data-stu-id="36e9e-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="36e9e-145">Начиная с версии [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> управления может разместить HTML-страницы, а также резервное копирование <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="36e9e-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36e9e-146">См. также</span><span class="sxs-lookup"><span data-stu-id="36e9e-146">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="36e9e-147">Конструктор WPF для Windows Forms разработчики</span><span class="sxs-lookup"><span data-stu-id="36e9e-147">WPF Designer for Windows Forms Developers</span></span>](http://msdn.microsoft.com/en-us/47ad0909-e89b-4996-b4ac-874d929f94ca)  
 [<span data-ttu-id="36e9e-148">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="36e9e-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="36e9e-149">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36e9e-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)  
 [<span data-ttu-id="36e9e-150">Миграция и взаимодействие систем</span><span class="sxs-lookup"><span data-stu-id="36e9e-150">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)
