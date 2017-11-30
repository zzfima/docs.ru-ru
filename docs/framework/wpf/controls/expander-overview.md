---
title: "Общие сведения об элементе управления Expander"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff0a4432f6de8458e89132bbf46bab7568a04b60
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="expander-overview"></a>Общие сведения об элементе управления Expander
<xref:System.Windows.Controls.Expander> Управления обеспечивает способ предоставления содержимого в развертываемой области, имеющей вид окна и включающей заголовок.  
  
  
<a name="CreatinganExpanderinXAML"></a>   
## <a name="creating-a-simple-expander"></a>Создание простого элемента управления Expander  
 В следующем примере демонстрируется создание простой <xref:System.Windows.Controls.Expander> элемента управления. В этом примере создается <xref:System.Windows.Controls.Expander> выглядит предыдущей иллюстрации.  
  
 [!code-xaml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> И <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> из <xref:System.Windows.Controls.Expander> может также содержать сложного содержимого, такие как <xref:System.Windows.Controls.RadioButton> и <xref:System.Windows.Controls.Image> объектов.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Задание направления развертывания области содержимого  
 Можно задать область содержимого <xref:System.Windows.Controls.Expander> управления для развертывания в одном из четырех направлениях (<xref:System.Windows.Controls.ExpandDirection.Down>, <xref:System.Windows.Controls.ExpandDirection.Up>, <xref:System.Windows.Controls.ExpandDirection.Left>, или <xref:System.Windows.Controls.ExpandDirection.Right>) с помощью <xref:System.Windows.Controls.ExpandDirection> свойство. Когда область содержимого свернута, только <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и отображаются его выключатель. Объект <xref:System.Windows.Controls.Button> элемент управления, отображающий стрелку направления используется в качестве выключателя можно разворачивать и сворачивать область содержимого. Когда она открыта, <xref:System.Windows.Controls.Expander> пытается отобразить все его содержимое в области окна.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Управление размером элемента управления Expander на панели  
 Если <xref:System.Windows.Controls.Expander> управления находится внутри элемента управления макета, который наследует от <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.StackPanel>, не указывайте <xref:System.Windows.FrameworkElement.Height%2A> на <xref:System.Windows.Controls.Expander> при <xref:System.Windows.Controls.Expander.ExpandDirection%2A> свойству <xref:System.Windows.Controls.ExpandDirection.Down> или <xref:System.Windows.Controls.ExpandDirection.Up>. Аналогично, не следует задавать <xref:System.Windows.FrameworkElement.Width%2A> на <xref:System.Windows.Controls.Expander> при <xref:System.Windows.Controls.Expander.ExpandDirection%2A> свойству <xref:System.Windows.Controls.ExpandDirection.Left> или <xref:System.Windows.Controls.ExpandDirection.Right>.  
  
 При задании измерения размера в <xref:System.Windows.Controls.Expander> управления в направлении отображения развернутого содержимого, <xref:System.Windows.Controls.Expander> возьмет на себя управление область, которая используется в содержимом и отображает рамку вокруг нее. Рамка отображается даже тогда, когда содержимое свернуто. Чтобы задать размер развернутой области содержимого, задайте размерности для содержимого <xref:System.Windows.Controls.Expander>, или если требуется возможность прокрутки, для <xref:System.Windows.Controls.ScrollViewer> , содержащего данные.  
  
 Когда <xref:System.Windows.Controls.Expander> управления является последним элементом в <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] автоматически задает <xref:System.Windows.Controls.Expander> размерности равными оставшейся области <xref:System.Windows.Controls.DockPanel>. Это поведение по умолчанию, задайте <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> свойство <xref:System.Windows.Controls.DockPanel> объект `false`, или убедитесь, что <xref:System.Windows.Controls.Expander> не является последним элементом в <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## <a name="creating-scrollable-content"></a>Создание прокручиваемого содержимого  
 Если содержимое слишком велико для размера области содержимого, можно упаковать содержимое <xref:System.Windows.Controls.Expander> в <xref:System.Windows.Controls.ScrollViewer> для обеспечения прокручиваемого содержимого. <xref:System.Windows.Controls.Expander> Управления автоматически не предоставляет возможность прокрутки. На следующем рисунке показана <xref:System.Windows.Controls.Expander> управления, содержащий <xref:System.Windows.Controls.ScrollViewer> элемента управления.  
  
 **Expander в ScrollViewer**  
  
 ![Элемент управления Expander со ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 При размещении <xref:System.Windows.Controls.Expander> управления <xref:System.Windows.Controls.ScrollViewer>, задайте <xref:System.Windows.Controls.ScrollViewer> измерения свойство, соответствующее направление, в котором <xref:System.Windows.Controls.Expander> открывается содержимое размер <xref:System.Windows.Controls.Expander> содержимого области. Например, если задать <xref:System.Windows.Controls.Expander.ExpandDirection%2A> свойство <xref:System.Windows.Controls.Expander> для <xref:System.Windows.Controls.ExpandDirection.Down> (область содержимого открывается вниз), задать <xref:System.Windows.FrameworkElement.Height%2A> свойство <xref:System.Windows.Controls.ScrollViewer> управления требуемую высоту области содержимого. Если вместо этого задать измерение высоты самого содержимого, <xref:System.Windows.Controls.ScrollViewer> не распознает этот параметр и поэтому не обеспечивает прокручиваемого содержимого.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.Expander> элемент управления с составным содержимым, содержащий <xref:System.Windows.Controls.ScrollViewer> элемента управления. В этом примере создается <xref:System.Windows.Controls.Expander> это похоже на рисунке в начале этого раздела.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## <a name="using-the-alignment-properties"></a>Использование свойств выравнивания  
 Содержимое можно выровнять, задав <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> свойства <xref:System.Windows.Controls.Expander> элемента управления. При задании этих свойств выравнивание применяется к заголовку и развернутому содержимому.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Expander>  
 <xref:System.Windows.Controls.ExpandDirection>  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
