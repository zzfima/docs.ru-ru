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
ms.openlocfilehash: f9265e3f7b287e1e8c264e89325f7c9649eebe2c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459131"
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Практическое руководство. Поиск элементов, созданных с использованием шаблона DataTemplate
В этом примере показано, как найти элементы, создаваемые <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Пример  
 В этом примере имеется <xref:System.Windows.Controls.ListBox>, привязанный к некоторым [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] данным:  
  
 [!code-xaml[FindGeneratedItems#LB](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox> использует следующие <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Если требуется получить элемент <xref:System.Windows.Controls.TextBlock>, созданный <xref:System.Windows.DataTemplate> определенного <xref:System.Windows.Controls.ListBoxItem>, необходимо получить <xref:System.Windows.Controls.ListBoxItem>, найти <xref:System.Windows.Controls.ContentPresenter> в этом <xref:System.Windows.Controls.ListBoxItem>, а затем вызвать <xref:System.Windows.FrameworkTemplate.FindName%2A> в <xref:System.Windows.DataTemplate>, установленном в Это <xref:System.Windows.Controls.ContentPresenter>. В следующем примере показано, как выполнить эти действия. В демонстрационных целях в этом примере создается окно сообщения, в котором отображается текстовое содержимое текстового блока, созданного <xref:System.Windows.DataTemplate>.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Ниже приведена реализация `FindVisualChild`, которая использует методы <xref:System.Windows.Media.VisualTreeHelper>:  
  
 [!code-csharp[FindGeneratedItems#FVC](~/samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>См. также

- [Поиск элемента, созданного шаблоном ControlTemplate](../controls/how-to-find-controltemplate-generated-elements.md)
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Области видимости имен XAML в WPF](../advanced/wpf-xaml-namescopes.md)
- [Деревья в WPF](../advanced/trees-in-wpf.md)
