---
title: Общие сведения об элементе управления Expander
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Expander
- Expander control [WPF], about Expander control
ms.assetid: 877bf425-0e54-49ec-8fd2-13a211377abb
ms.openlocfilehash: 892d972a5704d50e91d04e05d6fdea7180a3155d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187114"
---
# <a name="expander-overview"></a>Общие сведения об элементе управления Expander
Элемент <xref:System.Windows.Controls.Expander> управления обеспечивает способ предоставления содержимого в расширяемой области, которая напоминает окно и включает в себя заголовок.  

<a name="CreatinganExpanderinXAML"></a>
## <a name="creating-a-simple-expander"></a>Создание простого элемента управления Expander  
 Ниже приводится следующий пример, как создать простой <xref:System.Windows.Controls.Expander> элемент управления. Этот пример <xref:System.Windows.Controls.Expander> создает, который выглядит как предыдущая иллюстрация.  
  
 [!code-xaml[ExpanderExample#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderExample/CSharp/Page1.xaml#2)]  
  
 И <xref:System.Windows.Controls.ContentControl.Content%2A> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> <xref:System.Windows.Controls.Expander> может также содержать сложный контент, такие как <xref:System.Windows.Controls.RadioButton> и <xref:System.Windows.Controls.Image> объекты.  
  
<a name="SettingtheDirectionoftheExpandingWindow"></a>
## <a name="setting-the-direction-of-the-expanding-content-area"></a>Задание направления развертывания области содержимого  
 Вы можете установить область <xref:System.Windows.Controls.Expander> содержимого элемента управления,<xref:System.Windows.Controls.ExpandDirection.Down>чтобы <xref:System.Windows.Controls.ExpandDirection.Up> <xref:System.Windows.Controls.ExpandDirection.Left>расширить <xref:System.Windows.Controls.ExpandDirection.Right>в одном <xref:System.Windows.Controls.ExpandDirection> из четырех направлений (, , или ) с помощью свойства. При стомоте содержимого <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> появляется только кнопка переключения и ее переключения. Элемент <xref:System.Windows.Controls.Button> управления, отображаемый направленной стрелкой, используется в качестве кнопки переключения для расширения или сворачивания области содержимого. При расширении, <xref:System.Windows.Controls.Expander> пытается отобразить все его содержимое в окне, как область.  
  
<a name="SettingSizeDimensionsonanExpanderinaPanel"></a>
## <a name="controlling-the-size-of-an-expander-in-a-panel"></a>Управление размером элемента управления Expander на панели  
 Если <xref:System.Windows.Controls.Expander> элемент управления находится внутри элемента <xref:System.Windows.Controls.Panel>управления макета, который наследует от, <xref:System.Windows.Controls.StackPanel>например, не укажите <xref:System.Windows.FrameworkElement.Height%2A> на том, <xref:System.Windows.Controls.Expander> когда <xref:System.Windows.Controls.Expander.ExpandDirection%2A> свойство установлено <xref:System.Windows.Controls.ExpandDirection.Down> или <xref:System.Windows.Controls.ExpandDirection.Up>. Аналогичным образом, не <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Controls.Expander> указать <xref:System.Windows.Controls.Expander.ExpandDirection%2A> на, когда <xref:System.Windows.Controls.ExpandDirection.Left> <xref:System.Windows.Controls.ExpandDirection.Right>свойство установлено или .  
  
 При установке размера размера <xref:System.Windows.Controls.Expander> на элементе управления в направлении <xref:System.Windows.Controls.Expander> отображения расширенного содержимого, берет под контроль область, которая используется содержимого и отображает границу вокруг него. Рамка отображается даже тогда, когда содержимое свернуто. Чтобы установить размер расширенной области содержимого, установите <xref:System.Windows.Controls.Expander>размерразмеры на содержимое, или <xref:System.Windows.Controls.ScrollViewer> если вы хотите возможность прокрутки, на том, что привязает содержимое.  
  
 Когда <xref:System.Windows.Controls.Expander> элемент управления является последним <xref:System.Windows.Controls.DockPanel> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] элементом <xref:System.Windows.Controls.Expander> в, автоматически устанавливает размеры, чтобы равняться оставшейся <xref:System.Windows.Controls.DockPanel>области . Чтобы предотвратить это поведение <xref:System.Windows.Controls.DockPanel.LastChildFill%2A> по умолчанию, установите свойство на <xref:System.Windows.Controls.DockPanel> объекте, или `false`убедитесь, что <xref:System.Windows.Controls.Expander> это не последний элемент в . <xref:System.Windows.Controls.DockPanel>  
  
<a name="CreatingScrollableContent"></a>
## <a name="creating-scrollable-content"></a>Создание прокручиваемого содержимого  
 Если содержимое слишком велико для размера области содержимого, можно <xref:System.Windows.Controls.Expander> обернуть <xref:System.Windows.Controls.ScrollViewer> содержимое содержимого, чтобы обеспечить прокрутки содержимого. Элемент <xref:System.Windows.Controls.Expander> управления автоматически не обеспечивает возможность прокрутки. На следующей <xref:System.Windows.Controls.Expander> иллюстрации показан <xref:System.Windows.Controls.ScrollViewer> элемент управления, содержащий элемент управления.  
  
 **Expander в ScrollViewer**  
  
 ![Скриншот, который показывает расширитель с ScrollBar.](./media/expander-overview/expander-scrollbar-control.jpg)  
  
 При установке <xref:System.Windows.Controls.Expander> элемента <xref:System.Windows.Controls.ScrollViewer>управления <xref:System.Windows.Controls.ScrollViewer> в свойство измерения, которое <xref:System.Windows.Controls.Expander> соответствует направлению, в <xref:System.Windows.Controls.Expander> котором содержимое открывается размеру области содержимого. Например, если вы <xref:System.Windows.Controls.Expander.ExpandDirection%2A> установите <xref:System.Windows.Controls.Expander> <xref:System.Windows.Controls.ExpandDirection.Down> свойство на to (область <xref:System.Windows.FrameworkElement.Height%2A> содержимого <xref:System.Windows.Controls.ScrollViewer> открывается вниз), установите свойство на элементе управления на требуемую высоту для области содержимого. Если вместо этого вы установите размер <xref:System.Windows.Controls.ScrollViewer> высоты на само содержимое, не распознает эту настройку и, следовательно, не предоставляет прокрутки содержимого.  
  
 В следующем примере показано, как создать <xref:System.Windows.Controls.Expander> элемент управления, который имеет сложное содержимое и содержащий <xref:System.Windows.Controls.ScrollViewer> элемент управления. Этот пример <xref:System.Windows.Controls.Expander> создает иллюстрацию в начале этого раздела.  
  
 [!code-csharp[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ExpanderRichContent#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpanderRichContent/VisualBasic/Window1.xaml.vb#1)]
 [!code-xaml[ExpanderRichContent#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#1)]  
  
<a name="UsingtheAlignmentProperties"></a>
## <a name="using-the-alignment-properties"></a>Использование свойств выравнивания  
 Содержимое можно выровнять, установив элементируи <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> свойства на элементе <xref:System.Windows.Controls.Expander> управления. При задании этих свойств выравнивание применяется к заголовку и развернутому содержимому.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Expander>
- <xref:System.Windows.Controls.ExpandDirection>
- [Как-к темам](expander-how-to-topics.md)
