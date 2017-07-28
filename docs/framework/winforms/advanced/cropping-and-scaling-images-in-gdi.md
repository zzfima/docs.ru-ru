---
title: "Обрезка и масштабирование изображений в GDI+ | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "сжатие данных, изображения"
  - "GDI+, обрезка изображений"
  - "GDI+, масштабирование изображений"
  - "изображения [Windows Forms], сжатие"
  - "изображения [Windows Forms], обрезка"
  - "изображения [Windows Forms], раскрытие"
  - "изображения [Windows Forms], масштабирование"
  - "прямоугольники, назначение"
  - "прямоугольники, источник"
ms.assetid: ad5daf26-005f-45bc-a2af-e0e97777a21a
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Обрезка и масштабирование изображений в GDI+
Метод <xref:System.Drawing.Graphics.DrawImage%2A> класса <xref:System.Drawing.Graphics> позволяет рисовать и размещать векторные и растровые изображения.  Метод <xref:System.Drawing.Graphics.DrawImage%2A> перегружен, поэтому он поддерживает различные варианты передачи аргументов.  
  
## Варианты DrawImage  
 Один из вариантов метода <xref:System.Drawing.Graphics.DrawImage%2A> принимает объекты <xref:System.Drawing.Bitmap> и <xref:System.Drawing.Rectangle>.  Прямоугольник задает область, в которой должно быть нарисовано изображение.  Если размер прямоугольника назначения отличается от размеров исходного изображения, изображение масштабируется, чтобы соответствовать прямоугольнику назначения.  В приведенном ниже примере кода демонстрируется три способа рисования одного изображения: рисование без масштабирования, рисование с увеличением и рисование со сжатием.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#31)]  
  
 На приведенном ниже рисунке изображены три полученных изображения.  
  
 ![Масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art06.png "AboutGdip03\_Art06")  
  
 Некоторые варианты метода <xref:System.Drawing.Graphics.DrawImage%2A> получают в качестве параметров не только конечный, но и исходный прямоугольник.  Исходный прямоугольник задает часть исходного изображения, которая должна быть нарисована.  Прямоугольник назначения задает прямоугольник, в котором должна быть нарисована эта часть изображения.  Если размер прямоугольника назначения отличается от размера исходного прямоугольника, изображение масштабируется, чтобы соответствовать размеру прямоугольника назначения.  
  
 Приведенный ниже пример кода демонстрирует создание объекта <xref:System.Drawing.Bitmap> из файла Runner.jpg.  Изображение из файла рисуется целиком, без масштабирования, с привязкой к точке с координатами \(0, 0\).  Затем небольшой фрагмент изображения отображается дважды: один раз — со сжатием, второй раз — с увеличением.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#32)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#32](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#32)]  
  
 На приведенном ниже рисунке изображен немасштабированный рисунок, а также сжатая и увеличенная части рисунка.  
  
 ![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art07.png "AboutGdip03\_Art07")  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)