---
title: "Практическое руководство. Установка уровня сжатия JPEG | Microsoft Docs"
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
  - "изображения [Windows Forms], изменение параметров кодировщика"
  - "JPEG - изображения, настройка уровня качества"
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Установка уровня сжатия JPEG
Чтобы сделать размер файла сохраняемого на диске изображения минимальным или улучшить его качество, может потребоваться изменить параметры изображения.  Для изменения качества изображения JPEG можно изменить его уровень сжатия.  Чтобы указать уровень сжатия при сохранении изображения в формате JPEG, необходимо создать объект <xref:System.Drawing.Imaging.EncoderParameters> и передать его методу <xref:System.Drawing.Image.Save%2A> класса <xref:System.Drawing.Image>.  Инициализируйте объект <xref:System.Drawing.Imaging.EncoderParameters>, чтобы он включал массив из одного объекта <xref:System.Drawing.Imaging.EncoderParameter>.  При создании объекта <xref:System.Drawing.Imaging.EncoderParameter> укажите кодировщик <xref:System.Drawing.Imaging.Encoder.Quality> и выберите нужный уровень сжатия.  
  
## Пример  
 Следующий пример создает объект <xref:System.Drawing.Imaging.EncoderParameter> и сохраняет три изображения JPEG.  Каждое изображение JPEG сохраняется со своим уровнем качества, для этого необходимо изменить значение типа `long`, передаваемое конструктору <xref:System.Drawing.Imaging.EncoderParameter>.  Уровень качества 0 соответствует максимальному сжатию, а уровень качества 100 — минимальному сжатию.  
  
 [!code-csharp[UsingImageEncodersDecoders#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#8)]
 [!code-vb[UsingImageEncodersDecoders#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#8)]  
[!code-csharp[UsingImageEncodersDecoders#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#6)]
[!code-vb[UsingImageEncodersDecoders#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#6)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Приложение Windows Forms.  
  
-   Объект <xref:System.Windows.Forms.PaintEventArgs>, являющийся параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
-   Файл изображения `TestPhoto.jpg`, расположенный в папке **c:\\**.  
  
## См. также  
 [Практическое руководство. Определение параметров, поддерживаемых кодировщиком](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)   
 [Типы точечных рисунков](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)   
 [Применение кодировщиков и декодеров изображений в управляемом GDI\+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)