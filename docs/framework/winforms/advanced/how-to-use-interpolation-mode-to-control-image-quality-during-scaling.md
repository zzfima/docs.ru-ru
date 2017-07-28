---
title: "Практическое руководство. Использование режима интерполяции для управления качеством изображений при масштабировании | Microsoft Docs"
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
  - "изображения [Windows Forms], управление качеством"
  - "изображения [Windows Forms], масштабирование"
  - "режим интерполяции, управление качеством изображения"
ms.assetid: fde9bccf-8aa5-4b0d-ba4b-788740627b02
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Использование режима интерполяции для управления качеством изображений при масштабировании
Режим интерполяции объекта <xref:System.Drawing.Graphics> влияет на способ, с помощью которого [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] масштабирует \(растягивает и сжимает\) изображения.  Перечисление <xref:System.Drawing.Drawing2D.InterpolationMode> определяет различные режимы интерполяции, некоторые из которых приведены в следующем списке:  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
-   <xref:System.Drawing.Drawing2D.InterpolationMode>  
  
 Чтобы растянуть изображение, каждый пиксель этого исходного изображения должен быть сопоставлен группе пикселей увеличенного изображения.  Чтобы сжать изображение, группы пикселей этого исходного изображения должны быть сопоставлены отдельным пикселям уменьшенного изображения.  Качество масштабированного изображения определяется алгоритмами, используемыми для осуществления этих сопоставлений.  Алгоритмы, создающие более качественные масштабированные изображения, обычно требуют больших затрат машинного времени.  Из методов интерполяции, приведенных в предыдущем списке, <xref:System.Drawing.Drawing2D.InterpolationMode> обеспечивает наихудшее качество, а <xref:System.Drawing.Drawing2D.InterpolationMode> — наилучшее.  
  
 Чтобы установить режим интерполяции, присвойте один из членов перечисления <xref:System.Drawing.Drawing2D.InterpolationMode> свойству <xref:System.Drawing.Graphics.InterpolationMode%2A> объекта <xref:System.Drawing.Graphics>.  
  
## Пример  
 В следующем примере рисуется изображение, которое затем сжимается с использованием трех различных способов интерполяции.  
  
 На следующем рисунке показаны как исходное изображение, так и три варианта уменьшенного изображения.  
  
 ![Изображение с отличными параметрами вставки](../../../../docs/framework/winforms/advanced/media/csgrapes1.png "csgrapes1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#81)]
 [!code-vb[System.Drawing.WorkingWithImages#81](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#81)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)