---
title: "Практическое руководство. Рисование текста в визуальном элементе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], drawing text to visuals
- visuals [WPF], drawing text to
- text [WPF], drawing to visuals
- drawing [WPF], text to visuals
ms.assetid: fee4003c-e8a6-46ec-babd-2c7f4231a101
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 765d2102bc4466c2b194e03c9688212e04005ca2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-to-a-visual"></a>Практическое руководство. Рисование текста в визуальном элементе
В следующем примере показано, как нарисовать текст <xref:System.Windows.Media.DrawingVisual> с помощью <xref:System.Windows.Media.DrawingContext> объекта. Контекст рисования возвращается путем вызова <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A> метод <xref:System.Windows.Media.DrawingVisual> объекта. Можно нарисовать изображения и текст в контексте рисования.  
  
 Чтобы нарисовать текст в контексте рисования, используйте <xref:System.Windows.Media.DrawingContext.DrawText%2A> метод <xref:System.Windows.Media.DrawingContext> объекта. Когда вы закончите рисование содержимого в контексте рисования, вызовите <xref:System.Windows.Media.DrawingContext.Close%2A> метод, чтобы закрыть контекст рисования и сохранить содержимое.  
  
## <a name="example"></a>Пример  
 [!code-csharp[DrawingVisualSample#110](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#110)]
 [!code-vb[DrawingVisualSample#110](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#110)]  
  
> [!NOTE]
>  Полный код примера, из которого был взят предыдущий пример кода, см. в разделе [Проверка нажатия с помощью примера DrawingVisuals](http://go.microsoft.com/fwlink/?LinkID=159994).
