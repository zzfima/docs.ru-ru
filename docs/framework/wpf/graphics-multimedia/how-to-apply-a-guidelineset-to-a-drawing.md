---
title: "Практическое руководство. Применение GuidelineSet к рисованию"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dd8d93d128c03cb9ee482860603e5734e96c6fc2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Практическое руководство. Применение GuidelineSet к рисованию
В этом примере показано, как применить <xref:System.Windows.Media.GuidelineSet> для <xref:System.Windows.Media.DrawingGroup>.  
  
 <xref:System.Windows.Media.DrawingGroup> Класс является единственным типом <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> свойство. Для применения <xref:System.Windows.Media.GuidelineSet> к другому типу подсистемы <xref:System.Windows.Media.Drawing>, добавьте его в <xref:System.Windows.Media.DrawingGroup> , а затем применить <xref:System.Windows.Media.GuidelineSet> для вашей <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два <xref:System.Windows.Media.DrawingGroup> объектов, которые практически идентичны; единственное отличие заключается в: второй <xref:System.Windows.Media.DrawingGroup> имеет <xref:System.Windows.Media.GuidelineSet> и первый — нет.  
  
 На следующем рисунке показан результат выполнения этого примера. Поскольку визуализация разница между двумя <xref:System.Windows.Media.DrawingGroup> объекты не очень заметны, части рисунков увеличены.  
  
 ![DrawingGroup c GuidelineSet и без него ](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.GuidelineSet>  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
