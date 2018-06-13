---
title: Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
ms.openlocfilehash: d46a408bc1b5fc512905aa5bf176b13bd1511865
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556787"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate
В этом примере показано, как найти элементы, созданные <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется <xref:System.Windows.Controls.ListBox> , привязанный к некоторым [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данных:  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox> Использует следующие <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Если вы хотите получить <xref:System.Windows.Controls.TextBlock> элемент, созданный <xref:System.Windows.DataTemplate> определенного <xref:System.Windows.Controls.ListBoxItem>, необходимо получить <xref:System.Windows.Controls.ListBoxItem>, найти <xref:System.Windows.Controls.ContentPresenter> внутри этого <xref:System.Windows.Controls.ListBoxItem>и затем вызвать <xref:System.Windows.FrameworkTemplate.FindName%2A> на <xref:System.Windows.DataTemplate> установленное для, <xref:System.Windows.Controls.ContentPresenter>. В следующем примере показано, как для выполнения этих шагов. В целях демонстрации в этом примере создается окно сообщения, будет отображен текст содержимое <xref:System.Windows.DataTemplate>-созданный блок текста.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Ниже приведен реализация `FindVisualChild`, которая использует <xref:System.Windows.Media.VisualTreeHelper> методов:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>См. также  
 [Поиск элемента, созданного шаблоном ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Стилизация и использование шаблонов](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Области видимости имен XAML в WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Деревья в WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
