---
title: "Практическое руководство. Создание расширителя с элементом ScrollViewer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a2066ccce28138cfecf4e0b4574d45783a9ba4ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a>Практическое руководство. Создание расширителя с элементом ScrollViewer
В этом примере показано, как создать <xref:System.Windows.Controls.Expander> элемент управления, содержащий сложного содержимого, такие как изображение и текст. Пример также помещает содержимое <xref:System.Windows.Controls.Expander> в <xref:System.Windows.Controls.ScrollViewer> элемента управления.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как создать <xref:System.Windows.Controls.Expander>. В этом примере <xref:System.Windows.Controls.Primitives.BulletDecorator> управления, который содержит изображение и текст, чтобы определить <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>. Объект <xref:System.Windows.Controls.ScrollViewer> управления предоставляет метод для прокрутки развернутого содержимого.  
  
 Обратите внимание, что в этом примере <xref:System.Windows.FrameworkElement.Height%2A> свойство <xref:System.Windows.Controls.ScrollViewer> вместо доступа к содержимому. Если <xref:System.Windows.FrameworkElement.Height%2A> устанавливается с содержимым, <xref:System.Windows.Controls.ScrollViewer> не позволяет пользователю выполнять прокрутку содержимого. <xref:System.Windows.FrameworkElement.Width%2A> Установлено свойство <xref:System.Windows.Controls.Expander> управления и этот параметр применяется к <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> и развернутого содержимого.  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Expander>  
 [Общие сведения о расширителе](../../../../docs/framework/wpf/controls/expander-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/controls/expander-how-to-topics.md)
