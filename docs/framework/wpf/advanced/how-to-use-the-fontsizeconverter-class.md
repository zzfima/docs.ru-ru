---
title: "Как Использовать класс FontSizeConverter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FontSizeConverter objects [WPF]
- typography [WPF], FontSizeConverter objects
ms.assetid: 3b0592bd-7223-4860-a108-a5d72f3a9178
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bcf2d7348ca5b6b9d3b2edc44f92afbd46d32594
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-the-fontsizeconverter-class"></a>Как Использовать класс FontSizeConverter
## <a name="example"></a>Пример  
 В этом примере показано, как создать экземпляр <xref:System.Windows.FontSizeConverter> и использовать его для изменения размера шрифта.  
  
 В примере определяется пользовательский метод с именем `changeSize` , преобразующий содержимое <xref:System.Windows.Controls.ListBoxItem>, как определено в отдельном [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файл, чтобы экземпляр <xref:System.Double>и более поздней версии в <xref:System.String>. Этот метод передает <xref:System.Windows.Controls.ListBoxItem> для <xref:System.Windows.FontSizeConverter> объекта, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> к экземпляру компонента <xref:System.Double>. Это значение затем передается обратно в качестве значения <xref:System.Windows.Controls.TextBlock.FontSize%2A> свойство <xref:System.Windows.Controls.TextBlock> элемента.  
  
 Этот пример также определяет второй пользовательский метод, вызываемый `changeFamily`. Этот метод преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> из <xref:System.Windows.Controls.ListBoxItem> для <xref:System.String>, а затем передает это значение <xref:System.Windows.Controls.TextBlock.FontFamily%2A> свойство <xref:System.Windows.Controls.TextBlock> элемент.  
  
 Этот пример не запускается.  
  
 [!code-csharp[FontSizeConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FontSizeConverter/CSharp/Window1.xaml.cs#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.FontSizeConverter>
