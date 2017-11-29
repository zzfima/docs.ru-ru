---
title: "Отрисовка, позиционирование и клонирование изображений в GDI+"
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
- raster images [Windows Forms]
- images [Windows Forms], positioning
- drawing [Windows Forms], images
- drawing [Windows Forms], raster images
- images [Windows Forms], cloning
- images [Windows Forms], drawing
- GDI+, drawing images
- GDI+, cloning images
- GDI+, positioning images
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a3ba716a36280d2ac08dae907abbdbe05e563dfc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="drawing-positioning-and-cloning-images-in-gdi"></a>Отрисовка, позиционирование и клонирование изображений в GDI+
Можно использовать <xref:System.Drawing.Bitmap> класс для загрузки и отображения растровых изображений и может использовать <xref:System.Drawing.Imaging.Metafile> класса для загрузки и отображения векторных изображений. <xref:System.Drawing.Bitmap> И <xref:System.Drawing.Imaging.Metafile> классы наследуют от <xref:System.Drawing.Image> класса. Для отображения векторного изображения, требуется экземпляр <xref:System.Drawing.Graphics> класса и <xref:System.Drawing.Imaging.Metafile>. Чтобы отобразить растровое изображение, требуется экземпляр <xref:System.Drawing.Graphics> класса и <xref:System.Drawing.Bitmap>. Экземпляр <xref:System.Drawing.Graphics> класс предоставляет <xref:System.Drawing.Graphics.DrawImage%2A> метод, который получает <xref:System.Drawing.Imaging.Metafile> или <xref:System.Drawing.Bitmap> в качестве аргумента.  
  
## <a name="file-types-and-cloning"></a>Типы файлов и клонирование  
 В следующем примере кода показано создание <xref:System.Drawing.Bitmap> из файла Climber.jpg и отображает растровое изображение. Конечная точка верхнего левого угла изображения, (10, 10), указанный в второй и третий параметры.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 На следующем рисунке изображения.  
  
 ![Пример изображения](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.gif "AboutGdip03_Art04")  
  
 Можно создать <xref:System.Drawing.Bitmap> объекты из различных графических форматов файлов: BMP, GIF, JPEG, EXIF, PNG, TIFF и значок.  
  
 В следующем примере кода показано создание <xref:System.Drawing.Bitmap> объекты из различных типов файлов и отображение точечных рисунков.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 <xref:System.Drawing.Bitmap> Класс предоставляет <xref:System.Drawing.Bitmap.Clone%2A> метод, который можно использовать для создания копии существующего <xref:System.Drawing.Bitmap>. <xref:System.Drawing.Bitmap.Clone%2A> Метод имеет параметр исходный прямоугольник, можно использовать для указания часть исходного точечного рисунка, который требуется скопировать. В следующем примере кода показано, как создать <xref:System.Drawing.Bitmap> путем клонирования в верхней части существующей <xref:System.Drawing.Bitmap>. Затем оба изображения отображаются.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 На следующем рисунке два изображения.  
  
 ![Обрезка](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.gif "AboutGdip03_Art05")  
  
## <a name="see-also"></a>См. также  
 [Изображения, точечные рисунки и метафайлы](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [Практическое руководство. Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
