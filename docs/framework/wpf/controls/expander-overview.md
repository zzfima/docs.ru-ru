---
title: "Общие сведения об элементе управления Expander | Microsoft Docs"
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
  - "элементы управления, Expander"
  - "Expander - элемент управления, сведения об элементе управления Expander"
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Общие сведения об элементе управления Expander
Элемент управления <xref:System.Windows.Controls.Expander> обеспечивает способ предоставления содержимого в развертываемой области, имеющей вид окна и включающей заголовок.  
  
   
  
<a name="CreatinganExpanderinXAML"></a>   
## Создание простого элемента управления Expander  
 В следующем примере показано, как создать простой элемент управления <xref:System.Windows.Controls.Expander>.  В этом примере создается элемент <xref:System.Windows.Controls.Expander>, который выглядит, как на предыдущем рисунке.  
  
 [!code-xml[ExpanderExample#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 Свойства <xref:System.Windows.Controls.ContentControl.Content%2A> и <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> элемента управления <xref:System.Windows.Controls.Expander> могут также включать сложное содержимое, например объекты <xref:System.Windows.Controls.RadioButton> и <xref:System.Windows.Controls.Image>.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>   
## Задание направления развертывающейся области содержимого  
 Можно задать содержимое области элемента управления <xref:System.Windows.Controls.Expander> для развертывания в одном из четырех направлений \(<xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection>, <xref:System.Windows.Controls.ExpandDirection> или <xref:System.Windows.Controls.ExpandDirection>\), используя свойство <xref:System.Windows.Controls.ExpandDirection>.  Когда область содержимого свернута, отображается только <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и его выключатель.  Элемент управления <xref:System.Windows.Controls.Button>, отображающий стрелку направления, используется в качестве выключателя для развертывания или свертывания области содержимого.  При развертывании <xref:System.Windows.Controls.Expander> пытается отобразить все содержимое в области, подобной окну.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>   
## Управление размером элемента управления Expander на панели  
 Если элемент управления <xref:System.Windows.Controls.Expander> находится внутри элемента управления макетом, наследуемого из <xref:System.Windows.Controls.Panel>, например <xref:System.Windows.Controls.StackPanel>, не указывайте свойство <xref:System.Windows.FrameworkElement.Height%2A> в элементе <xref:System.Windows.Controls.Expander>, если для свойства <xref:System.Windows.Controls.Expander.ExpandDirection%2A> задано значение <xref:System.Windows.Controls.ExpandDirection> или <xref:System.Windows.Controls.ExpandDirection>.  Так же не указывайте свойство <xref:System.Windows.FrameworkElement.Width%2A> в элементе <xref:System.Windows.Controls.Expander>, если для свойства <xref:System.Windows.Controls.Expander.ExpandDirection%2A> задано значение <xref:System.Windows.Controls.ExpandDirection> или <xref:System.Windows.Controls.ExpandDirection>.  
  
 Если задается размерность элемента управления <xref:System.Windows.Controls.Expander> в направлении отображения развернутого содержимого, то <xref:System.Windows.Controls.Expander> принимает управление областью, которая используется содержимым, и отображает рамку вокруг нее.  Рамка отображается даже тогда, когда содержимое свернуто.  Чтобы установить размер развернутой области содержимого, задайте размерности для содержимого <xref:System.Windows.Controls.Expander> или, если требуется возможность прокрутки, для элемента <xref:System.Windows.Controls.ScrollViewer>, вмещающего содержимое.  
  
 Когда элемент управления <xref:System.Windows.Controls.Expander> является последним элементом в <xref:System.Windows.Controls.DockPanel>, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] автоматически устанавливает размерности равными оставшейся области <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.DockPanel>.  Чтобы избежать такой настройки по умолчанию, задайте для свойства <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> в объекте <xref:System.Windows.Controls.DockPanel> значение `false` или убедитесь, что <xref:System.Windows.Controls.Expander> не является последним элементом в <xref:System.Windows.Controls.DockPanel>.  
  
<a name="CreatingScrollableContent"></a>   
## Создание прокручиваемого содержимого  
 Если содержимое слишком велико для размера области содержимого, то можно поместить содержимое <xref:System.Windows.Controls.Expander> в элемент <xref:System.Windows.Controls.ScrollViewer>, чтобы обеспечить прокрутку содержимого.  Элемент управления <xref:System.Windows.Controls.Expander> автоматически не предоставляет возможность прокрутки.  На следующем рисунке показан элемент управления <xref:System.Windows.Controls.Expander>, содержащий элемент управления <xref:System.Windows.Controls.ScrollViewer>.  
  
 **Expander в ScrollViewer**  
  
 ![Элемент управления Expander со ScrollBar](../../../../docs/framework/wpf/controls/media/expanderwithscrollbar.JPG "ExpanderWithScrollBar")  
  
 При помещении элемента управления <xref:System.Windows.Controls.Expander> в элемент управления <xref:System.Windows.Controls.ScrollViewer> задайте свойство размерности <xref:System.Windows.Controls.ScrollViewer>, соответствующее направлению, в котором открывается содержимое <xref:System.Windows.Controls.Expander>, по размеру области содержимого <xref:System.Windows.Controls.Expander>.  Например, если для свойства <xref:System.Windows.Controls.Expander.ExpandDirection%2A> в элементе управления <xref:System.Windows.Controls.Expander> задается значение <xref:System.Windows.Controls.ExpandDirection> \(область содержимого открывается вниз\), то нужно задать для свойства <xref:System.Windows.FrameworkElement.Height%2A> в элементе управления <xref:System.Windows.Controls.ScrollViewer> требуемую высоту для области содержимого.  Если вместо этого задать размерность высоты самого содержимого, то <xref:System.Windows.Controls.ScrollViewer> не распознает этот параметр и, таким образом, не предоставит прокручиваемое содержимое.  
  
 В следующем примере показано, как создать элемент управления <xref:System.Windows.Controls.Expander>, который имеет сложное содержимое и содержит элемент управления <xref:System.Windows.Controls.ScrollViewer>.  В этом примере создается элемент управления <xref:System.Windows.Controls.Expander>, подобный показанному на рисунке в начале этого раздела.  
  
 [!code-csharp[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xml[ExpanderRichContent#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>   
## Использование свойств выравнивания  
 Можно выровнять содержимое, задавая свойства <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> в элементе управления <xref:System.Windows.Controls.Expander>.  При задании этих свойств выравнивание применяется к заголовку и развернутому содержимому.  
  
## См. также  
 <xref:System.Windows.Controls.Expander>   
 <xref:System.Windows.Controls.ExpandDirection>   
 [Практические руководства](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)