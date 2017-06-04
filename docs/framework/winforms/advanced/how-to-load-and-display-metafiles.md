---
title: "Практическое руководство. Загрузка и отображение метафайлов | Microsoft Docs"
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
  - "примеры [Windows Forms], метафайлы"
  - "метафайлы, отображение"
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Загрузка и отображение метафайлов
Класс <xref:System.Drawing.Imaging.Metafile>, наследующий у класса <xref:System.Drawing.Image>, содержит методы для записи, отображения и проверки векторных изображений.  
  
## Пример  
 Для отображения векторного изображения \(метафайла\) на экране следует использовать объекты <xref:System.Drawing.Imaging.Metafile> и <xref:System.Drawing.Graphics>.  Имя файла \(или потока\) передается в качестве параметра конструктору <xref:System.Drawing.Imaging.Metafile>.  После создания объекта <xref:System.Drawing.Imaging.Metafile> этот объект <xref:System.Drawing.Imaging.Metafile> необходимо передать в качестве параметра методу <xref:System.Drawing.Graphics.DrawImage%2A> объекта <xref:System.Drawing.Graphics>.  
  
 В примере создается объект <xref:System.Drawing.Imaging.Metafile> на основе файла в формате EMF \(enhanced metafile — расширенный метафайл\) и на экране рисуется соответствующее изображение с верхним левым углом в точке \(60, 10\).  
  
 На следующем рисунке показан метафайл, выведенный на экран в указанном месте.  
  
 ![Положение изображения](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.Control.Paint>.  
  
## См. также  
 [Работа с растровыми и векторными изображениями](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)