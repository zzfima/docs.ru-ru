---
title: "Практическое руководство. Смещение элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2f9b8363f0c3b9e0a9653dfc9864727c9460f695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-translate-an-element"></a>Практическое руководство. Смещение элемента
В этом примере показано, как для переноса (перемещения) элемента с помощью <xref:System.Windows.Media.TranslateTransform>.  
  
 <xref:System.Windows.Media.TranslateTransform> Класс особенно полезен для перемещения элементов внутри панелей, которые не поддерживают абсолютное позиционирование. Например, применяя <xref:System.Windows.Media.TranslateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойства элемента, можно переместить элемент в пределах <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel>.  
  
 Используйте <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> , чтобы задать интервал в пикселях для перемещения элемента по оси x. Используйте <xref:System.Windows.Media.TranslateTransform.Y%2A> свойство, чтобы задать интервал в пикселях для перемещения элемента по оси y. Наконец, примените <xref:System.Windows.Media.TranslateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойства элемента.  
  
 В следующем примере используется <xref:System.Windows.Media.TranslateTransform> для перемещения элемента на 50 пикселей вправо до 50 пикселей вниз.  
  
## <a name="example"></a>Пример  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 Полный пример см. в разделе [Примеры двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
