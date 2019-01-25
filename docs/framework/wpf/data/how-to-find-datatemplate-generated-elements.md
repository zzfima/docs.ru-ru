---
title: Как выполнить Поиск элементов, созданных с использованием шаблона DataTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: d271a3d53a0e102f8f969fd0751e15b470a52862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54511570"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Как выполнить Поиск элементов, созданных с использованием шаблона DataTemplate
В этом примере показано, как для поиска элементов, создаваемых <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется <xref:System.Windows.Controls.ListBox> , привязанный к некоторым [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных:  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox> Использует следующие <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Если вы хотите получить <xref:System.Windows.Controls.TextBlock> элемент, созданный <xref:System.Windows.DataTemplate> определенного <xref:System.Windows.Controls.ListBoxItem>, необходимо получить <xref:System.Windows.Controls.ListBoxItem>, найти <xref:System.Windows.Controls.ContentPresenter> внутри этого <xref:System.Windows.Controls.ListBoxItem>, а затем вызвать <xref:System.Windows.FrameworkTemplate.FindName%2A> на <xref:System.Windows.DataTemplate> установленное, <xref:System.Windows.Controls.ContentPresenter>. В следующем примере показано, как для выполнения этих шагов. В демонстрационных целях в этом примере создается окно сообщения, которое будет отображен текст содержимого из <xref:System.Windows.DataTemplate>-созданный блок текста.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Ниже приведен реализация `FindVisualChild`, которая использует <xref:System.Windows.Media.VisualTreeHelper> методы:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Найти, созданного шаблоном ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)
- [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
- [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)
- [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)
- [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
