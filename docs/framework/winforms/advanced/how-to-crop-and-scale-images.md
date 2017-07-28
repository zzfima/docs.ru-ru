---
title: "Практическое руководство. Обрезка и масштабирование изображений | Microsoft Docs"
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
  - "изображения [Windows Forms], обрезка"
  - "изображения [Windows Forms], масштабирование"
ms.assetid: 053e3360-bca0-4b25-9afa-0e77a6f17b03
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Обрезка и масштабирование изображений
Класс <xref:System.Drawing.Graphics> включает различные методы <xref:System.Drawing.Graphics.DrawImage%2A>, некоторые из которых принимают параметры "исходный прямоугольник" и "прямоугольник назначения", используемые для обрезки и масштабирования изображений.  
  
## Пример  
 В следующем примере создается объект <xref:System.Drawing.Image> на основе файла Apple.gif.  Этот код рисует изображение яблока целиком, используя его фактический размер.  Затем вызывается метод <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics> для рисования фрагмента изображения яблока в прямоугольнике назначения, имеющем больший размер, чем исходное изображение яблока.  
  
 Метод <xref:System.Drawing.Graphics.DrawImage%2A> определяет, какой именно фрагмент изображения яблока выводить на экран, анализируя исходный прямоугольник, задаваемый третьим, четвертым, пятым и шестым параметрами метода.  В рассматриваемом случае изображение яблока обрезается до 75% его ширины и 75% высоты.  
  
 Метод <xref:System.Drawing.Graphics.DrawImage%2A> определяет, где рисовать обрезанное изображение яблока и как его следует масштабировать, анализируя прямоугольник назначения, задаваемый вторым параметром метода.  В данном случае прямоугольник назначения на 30% шире и на 30% выше, чем исходное изображение.  
  
 На следующем рисунке показаны исходное изображение яблока и его масштабированное обрезанное изображение.  
  
 ![Обрезка и масштабирование](../../../../docs/framework/winforms/advanced/media/cscropscale1.png "csCropScale1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.WorkingWithImages#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  Не забудьте заменить путь и имя файла `Apple.gif` именем файла изображения в вашей системе.  
  
## См. также  
 [Работа с растровыми и векторными изображениями с использованием классов Image, Bitmap и Metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)   
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)