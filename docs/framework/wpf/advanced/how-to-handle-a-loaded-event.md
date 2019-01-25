---
title: Как выполнить Обработка загруженного события
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XAML [WPF], Loaded events
- events [WPF], Loaded
- Loaded events [WPF]
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
ms.openlocfilehash: 187d75c436913140855f4d860eb3b6ad4656f309
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682947"
---
# <a name="how-to-handle-a-loaded-event"></a>Как выполнить Обработка загруженного события
В этом примере демонстрируется обработка <xref:System.Windows.FrameworkElement.Loaded?displayProperty=nameWithType> событий и соответствующий скрипт для обработки этого события. Создает обработчик <xref:System.Windows.Controls.Button> при загрузке страницы.  
  
## <a name="example"></a>Пример  
 В следующем примере используется [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] вместе с файлом кода.  
  
 [!code-xaml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.FrameworkElement>
- [События времени жизни объекта](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)
- [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
