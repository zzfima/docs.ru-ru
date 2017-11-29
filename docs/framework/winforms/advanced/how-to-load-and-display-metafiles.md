---
title: "Практическое руководство. Загрузка и отображение метафайлов"
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
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 722b6d36801c69e500535a32e952ef8f45634d03
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a>Практическое руководство. Загрузка и отображение метафайлов
<xref:System.Drawing.Imaging.Metafile> Класс, унаследованный от класса <xref:System.Drawing.Image> класса, предоставляет методы для записи, отображения и анализа векторных изображений.  
  
## <a name="example"></a>Пример  
 Для отображения векторного изображения (метафайла) на экране, следует <xref:System.Drawing.Imaging.Metafile> объекта и <xref:System.Drawing.Graphics> объекта. Передайте имя файла (или потока) в <xref:System.Drawing.Imaging.Metafile> конструктора. После создания <xref:System.Drawing.Imaging.Metafile> объекта, передать этот <xref:System.Drawing.Imaging.Metafile> объект <xref:System.Drawing.Graphics.DrawImage%2A> метод <xref:System.Drawing.Graphics> объекта.  
  
 В примере создается <xref:System.Drawing.Imaging.Metafile> объекта из файла EMF (расширенный метафайл) и рисуется изображение с его верхнего левого угла в (60, 10).  
  
 На следующем рисунке метафайла, нарисованная в указанном расположении.  
  
 ![Положение изображения](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [Работа с растровыми и векторными изображениями, значками и метафайлами](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
