---
title: "Отрисовка, позиционирование и клонирование изображений в GDI+ | Microsoft Docs"
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
  - "рисование, изображения"
  - "рисование, растровые изображения"
  - "GDI+, клонирование изображений"
  - "GDI+, создание изображений"
  - "GDI+, размещение изображений"
  - "изображения [Windows Forms], клонирование"
  - "изображения [Windows Forms], рисование"
  - "изображения [Windows Forms], размещение"
  - "растровые изображения"
ms.assetid: 09f0c07a-19c0-43b4-90a2-862a10545ce8
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Отрисовка, позиционирование и клонирование изображений в GDI+
Класс <xref:System.Drawing.Bitmap> позволяет загружать и отображать растровые изображения, а класс <xref:System.Drawing.Imaging.Metafile> служит для загрузки и отображения векторных изображений.  Классы <xref:System.Drawing.Bitmap> и <xref:System.Drawing.Imaging.Metafile> наследуются от класса <xref:System.Drawing.Image>.  Для вывода векторного изображения необходим экземпляр класса <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Imaging.Metafile>.  Для вывода растрового изображения необходим экземпляр класса <xref:System.Drawing.Graphics> и объект <xref:System.Drawing.Bitmap>.  У экземпляра класса <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.DrawImage%2A>, который в качестве аргумента принимает объект <xref:System.Drawing.Imaging.Metafile> или <xref:System.Drawing.Bitmap>.  
  
## Типы файлов и клонирование  
 Приведенный ниже пример кода демонстрирует создание объекта <xref:System.Drawing.Bitmap> из файла Climber.jpg и отображение извлеченного из этого файла растрового рисунка.  Верхний левый угол изображения совмещается с точкой с координатами \(10, 10\), которые задаются вторым и третьим параметром.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#11)]  
  
 На приведенном ниже рисунке показано полученное изображение.  
  
 ![Пример работы с изображением](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art04.png "AboutGdip03\_Art04")  
  
 Объект <xref:System.Drawing.Bitmap> можно создавать из файлов различных графических форматов, таких как BMP, GIF, JPEG, EXIF, PNG, TIFF или ICON.  
  
 Приведенный ниже пример кода демонстрирует создание объекта <xref:System.Drawing.Bitmap> из файлов различных типов и отображение извлеченных из этих файлов растровых рисунков.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#12)]  
  
 У класса <xref:System.Drawing.Bitmap> имеется метод <xref:System.Drawing.Bitmap.Clone%2A>, который можно использовать для создания копии существующего объекта <xref:System.Drawing.Bitmap>.  Метод <xref:System.Drawing.Bitmap.Clone%2A> получает в качестве аргумента исходный прямоугольник, который определяет часть исходного растрового рисунка, которую нужно скопировать.  Следующий пример кода показывает, как создать новый объект <xref:System.Drawing.Bitmap> путем копирования верхней половины существующего объекта <xref:System.Drawing.Bitmap>.  После этого оба изображения будут выведены на экран.  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#13)]  
  
 На приведенном ниже рисунке показаны полученные изображения.  
  
 ![Обрезка](../../../../docs/framework/winforms/advanced/media/aboutgdip03-art05.png "AboutGdip03\_Art05")  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)