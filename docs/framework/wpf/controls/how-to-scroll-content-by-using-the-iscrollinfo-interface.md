---
title: Как выполнить Прокручивание содержимого с помощью интерфейса IScrollInfo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ScrollViewer control [WPF], scrolling content
- scrolling content [WPF]
- IScrollInfo interface [WPF]
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
ms.openlocfilehash: 49b3483750582aa51d1de418f745d931604d2786
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637863"
---
# <a name="how-to-scroll-content-by-using-the-iscrollinfo-interface"></a>Как выполнить Прокручивание содержимого с помощью интерфейса IScrollInfo
В этом примере показано, как прокручивание содержимого с помощью <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейс.  
  
## <a name="example"></a>Пример  
 Следующий пример демонстрирует функции <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейс. В примере создается <xref:System.Windows.Controls.StackPanel> элемент в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , вложенный в родительский элемент <xref:System.Windows.Controls.ScrollViewer>. Дочерние элементы <xref:System.Windows.Controls.StackPanel> можно прокручивать с помощью методов, определенных логически <xref:System.Windows.Controls.Primitives.IScrollInfo> интерфейс и приведение к экземпляру <xref:System.Windows.Controls.StackPanel> (`sp1`) в коде.  
  
 [!code-xaml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Каждый <xref:System.Windows.Controls.Button> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] файл активирует связанный настраиваемый метод, который управляет поведением прокрутки в <xref:System.Windows.Controls.StackPanel>. В следующем примере показано, как использовать <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A> методов; также в целом демонстрируется использование всех методов позиционирования, <xref:System.Windows.Controls.Primitives.IScrollInfo> определяет класс.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.Primitives.IScrollInfo>
- <xref:System.Windows.Controls.StackPanel>
- [Общие сведения об элементе управления ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)
- [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)
