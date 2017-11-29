---
title: "Рисование текста с помощью глифов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text [WPF], drawing with Glyphs objects
- Glyphs objects [WPF], drawing text
- typography [WPF], Glyphs objects
ms.assetid: 587ab17e-a419-4ad5-b6da-8933a8e83d97
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ebce286cd93355feac7e4675ef6b142862740a92
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="draw-text-using-glyphs"></a>Рисование текста с помощью глифов
В этом разделе описывается использование нижнего уровня <xref:System.Windows.Documents.Glyphs> объекта для отображения текста в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  
  
## <a name="example"></a>Пример  
 Следующие примеры показывают, как можно задать свойства для <xref:System.Windows.Documents.Glyphs> объекта в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. <xref:System.Windows.Documents.Glyphs> Объект представляет выходные данные <xref:System.Windows.Media.GlyphRun> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. В примерах предполагается, что шрифты Arial, Courier New и Times New Roman устанавливаются в папку C:\WINDOWS\Fonts на локальном компьютере.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
 В этом примере показано, как определение других свойств <xref:System.Windows.Documents.Glyphs> объекты в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GlyphsOvwSamp2#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSamp2/CS/default.xaml#1)]  
  
## <a name="see-also"></a>См. также  
 [Оформление в WPF](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)
