---
title: "Обрезка и масштабирование изображений в GDI+"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI+, scaling images
- GDI+, cropping images
- images [Windows Forms], cropping
- compressing data [Windows Forms], images
- images [Windows Forms], expansion
- images [Windows Forms], scaling
- rectangles [Windows Forms], source
- rectangles [Windows Forms], destination
- images [Windows Forms], compression
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63e1e55e57d586cbbca87361b95c18f0f53b8c75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Обрезка и масштабирование изображений в GDI+
Можно использовать <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> класса для рисования и размещения векторных и растровых изображений. <xref:System.Drawing.Graphics.DrawImage%2A>— перегружаемый метод, поэтому существует несколько способов передачи аргументов.  
  
## <a name="drawimage-variations"></a>DrawImage вариантов  
 Один из вариантов <xref:System.Drawing.Graphics.DrawImage%2A> метод получает <xref:System.Drawing.Bitmap> и <xref:System.Drawing.Rectangle>. Прямоугольник определяет место назначения для операции рисования; то есть он указывает прямоугольник, в котором будет рисоваться изображение. Если размер прямоугольника назначения отличается от размера исходного изображения, изображение масштабируется по размерам прямоугольника назначения. В следующем примере кода показано, как рисовать тот же образ три раза: один раз без масштабирования, рисование с увеличением и рисование со сжатием:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 На следующем рисунке три изображения.  
  
 ![Масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Некоторые варианты <xref:System.Drawing.Graphics.DrawImage%2A> метод иметь исходный прямоугольник, а также параметр прямоугольника назначения. Исходный прямоугольник задает часть исходного изображения для рисования. Прямоугольник назначения задает прямоугольник, в которой выводится часть изображения. Если размер прямоугольника назначения отличается от размера исходного прямоугольника, изображение масштабируется по размерам прямоугольника назначения.  
  
 В следующем примере кода показано создание <xref:System.Drawing.Bitmap> из файла Runner.jpg. Все изображение рисуется без масштабирования на (0, 0). Затем небольшую часть изображения отображается дважды: один раз со сжатием и один раз с помощью расширения.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 На следующем рисунке зависимым изображения и сжатые и увеличенная части рисунка.  
  
 ![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
