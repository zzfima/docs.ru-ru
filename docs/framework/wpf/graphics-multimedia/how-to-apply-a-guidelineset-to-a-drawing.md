---
title: Практическое руководство. Применение GuidelineSet к рисованию
ms.date: 03/30/2017
helpviewer_keywords:
- GuidelineSet property [WPF], applying to drawings
- graphics [WPF], GuidelineSet property
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
ms.openlocfilehash: 88c44cadce916c2ce10165a586e813ecaaaec672
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362998"
---
# <a name="how-to-apply-a-guidelineset-to-a-drawing"></a>Практическое руководство. Применение GuidelineSet к рисованию
В этом примере показано, как применить <xref:System.Windows.Media.GuidelineSet> для <xref:System.Windows.Media.DrawingGroup>.  
  
 <xref:System.Windows.Media.DrawingGroup> Класс является единственным типом <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> свойство. Чтобы применить <xref:System.Windows.Media.GuidelineSet> к другому типу <xref:System.Windows.Media.Drawing>, добавьте его в <xref:System.Windows.Media.DrawingGroup> , а затем применить <xref:System.Windows.Media.GuidelineSet> для вашей <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="example"></a>Пример  
 В следующем примере создается два <xref:System.Windows.Media.DrawingGroup> объекты, которые практически идентичны; единственное отличие заключается в: второй <xref:System.Windows.Media.DrawingGroup> имеет <xref:System.Windows.Media.GuidelineSet> и первый — нет.  
  
 На следующем рисунке показан результат выполнения этого примера. Так как два различия в отрисовке <xref:System.Windows.Media.DrawingGroup> объекты не очень заметны, части рисунков увеличены.  
  
 ![DrawingGroup c GuidelineSet и без него ](./media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm_drawinggroup_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.DrawingGroup>
- <xref:System.Windows.Media.GuidelineSet>
- [Обзор объектов Drawing](drawing-objects-overview.md)
