---
title: "Практическое руководство. Рисование текста на фоне элемента управления"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f0c98422e337678e68a8e4b72979635e8c867b4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>Практическое руководство. Рисование текста на фоне элемента управления
Можно нарисовать текст непосредственно на фоне элемента управления путем преобразования текстовую строку для <xref:System.Windows.Media.FormattedText> объекта, а затем рисование объекта элемента управления <xref:System.Windows.Media.DrawingContext>. Эту технологию можно также использовать для рисования фона для объектов, производных от <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.  
  
 ![Элементы управления, отображающие текст в качестве фона](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Пример элементов управления с фоном из пользовательского текста  
  
## <a name="example"></a>Пример  
 Чтобы нарисовать фон элемента управления, создайте новый <xref:System.Windows.Media.DrawingBrush> и рисовать текст, преобразованный в объект <xref:System.Windows.Media.DrawingContext>. После этого назначьте новый <xref:System.Windows.Media.DrawingBrush> свойству фона элемента управления.  
  
 В следующем примере кода показано, как создать <xref:System.Windows.Media.FormattedText> и рисовать фон <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button> объекта.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.FormattedText>  
 [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
