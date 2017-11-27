---
title: "Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения"
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
- images [Windows Forms], using with brushes
- bitmaps [Windows Forms], using texture
- shapes [Windows Forms], filling with images
ms.assetid: 508da5a6-2433-4d2b-9680-eaeae4e96e3b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c20562cade6917a3426fe04861a05c4b6b0bd543
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-fill-a-shape-with-an-image-texture"></a>Практическое руководство. Заливка фигуры текстурой, созданной на основе изображения
Можно заполнить замкнутую фигуру текстуры с помощью <xref:System.Drawing.Image> класса и <xref:System.Drawing.TextureBrush> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере заполняется эллипса с изображением. Код создает <xref:System.Drawing.Image> объекта, а затем передает адрес объекта <xref:System.Drawing.Image> объект в качестве аргумента для <xref:System.Drawing.TextureBrush.%23ctor%2A> конструктор. Третья инструкция выполняет изменение масштаба изображения, а Четвертая инструкция выполняет заливку эллипса повторяющиеся копии масштабированного изображения.  
  
 В следующем коде <xref:System.Drawing.TextureBrush.Transform%2A> свойство содержит преобразование, которое применяется к изображению перед его прорисовкой. Предположим, что исходное изображение имеет ширину 640 пикселей и высотой 480 пикселей. Преобразование уменьшает изображение до 75 × 75, задав значения горизонтальные и вертикальные масштабирования.  
  
> [!NOTE]
>  В следующем примере составляет 75 × 75 и размер эллипса, который составляет 150 × 250. Так как изображение меньше заполняемой эллипса, выполняется мозаичное заполнение эллипса с изображением. Достигнут мозаичное заполнение означает, что изображение повторяется горизонтально и вертикально до границы фигуры. Дополнительные сведения о мозаичное заполнение см. в разделе [как: мозаичное заполнение фигуры с изображением](../../../../docs/framework/winforms/advanced/how-to-tile-a-shape-with-an-image.md).  
  
 [!code-csharp[System.Drawing.UsingABrush#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingABrush/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.UsingABrush#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingABrush/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, и для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="see-also"></a>См. также  
 [Использование кисти для заливки фигур](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)
