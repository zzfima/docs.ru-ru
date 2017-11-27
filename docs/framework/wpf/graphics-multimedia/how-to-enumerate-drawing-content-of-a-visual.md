---
title: "Практическое руководство. Перечисление содержимого изображения визуального элемента"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e498bc8e425198e479d7ce0b2328e0efa3ede70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a>Практическое руководство. Перечисление содержимого изображения визуального элемента
<xref:System.Windows.Media.Drawing> Объекта предоставляют объектную модель для перечисления содержимого <xref:System.Windows.Media.Visual>.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> метод для извлечения <xref:System.Windows.Media.DrawingGroup> значение <xref:System.Windows.Media.Visual> и его перечисления.  
  
> [!NOTE]
>  При перечислении содержимого визуального элемента, необходимо извлечь <xref:System.Windows.Media.Drawing> объектов, а не базовое представление данных визуализации в виде списка инструкций векторной графики. Дополнительные сведения см. в разделе [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Общие сведения об отрисовке графики в WPF](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
