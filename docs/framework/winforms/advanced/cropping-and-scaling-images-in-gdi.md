---
title: Обрезка и масштабирование изображений в GDI+
ms.date: 03/30/2017
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
ms.openlocfilehash: 6c3ad0892ea0892b7c4c0e21e14bdb75fe22b447
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554222"
---
# <a name="cropping-and-scaling-images-in-gdi"></a>Обрезка и масштабирование изображений в GDI+
Можно использовать <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> позволяет рисовать и размещать векторные и растровые изображения. <xref:System.Drawing.Graphics.DrawImage%2A> — Это перегруженный метод, поэтому существует несколько способов передачи аргументов.  
  
## <a name="drawimage-variations"></a>DrawImage вариантов  
 Один из вариантов <xref:System.Drawing.Graphics.DrawImage%2A> метод получает <xref:System.Drawing.Bitmap> и <xref:System.Drawing.Rectangle>. Прямоугольник определяет место назначения для операции рисования; то есть он задает прямоугольник, в котором должно быть нарисовано изображение. Если размер целевого прямоугольника отличаются от размера исходного изображения, изображение масштабируется по размерам прямоугольника назначения. В следующем примере кода показано, как должно быть нарисовано изображение же три раза: один раз без масштабирования, один раз с помощью расширения и один раз с сжатия:  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 Ниже показаны три изображения.  
  
 ![Масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.gif "AboutGdip03_Art06")  
  
 Некоторые варианты <xref:System.Drawing.Graphics.DrawImage%2A> метод иметь исходный прямоугольник, а также параметр целевого прямоугольника. Исходный прямоугольник задает часть исходного изображения для рисования. Прямоугольник назначения задает прямоугольник, в котором для рисования эту часть изображения. Если размер целевого прямоугольника отличаются от размера исходного прямоугольника, изображение масштабируется по размерам прямоугольника назначения.  
  
 В следующем примере кода показано создание <xref:System.Drawing.Bitmap> из файла Runner.jpg. Все изображение рисуется без масштабирования на (0, 0). Затем небольшую часть изображения отображается дважды: один раз со сжатием и один раз с помощью расширения.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 Ниже показан немасштабированного рисунка и части, сжатые и Развернутое изображение.  
  
 ![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.gif "AboutGdip03_Art07")  
  
## <a name="see-also"></a>См. также
- [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
