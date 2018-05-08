---
title: Инструкция по перечислению системных шрифтов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7fc996a2d3ba7042fce70afc20be5d64042c2b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-system-fonts"></a>Инструкция по перечислению системных шрифтов
## <a name="example"></a>Пример  
 В следующем примере показано, как перечисление шрифтов в коллекции системных шрифтов. Имя семейства шрифтов каждого <xref:System.Windows.Media.FontFamily> в <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> добавляется как элемент в поле со списком.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Если несколько версий одного семейства шрифтов находятся в том же каталоге [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] перечисление шрифтов возвращает самую последнюю версию шрифта. Если сведения о версии не предоставляют разрешения, возвращается шрифт с последней временной меткой. Если метки времени эквивалентно, возвращается файл шрифта, который является первым в алфавитном порядке.
