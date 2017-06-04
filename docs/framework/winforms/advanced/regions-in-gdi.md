---
title: "Области в GDI+ | Microsoft Docs"
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
  - "рисование, области"
  - "GDI+, области"
  - "области"
ms.assetid: 52184f9b-16dd-4bbd-85be-029112644ceb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Области в GDI+
Область — это часть зоны, отображаемой устройством вывода.  Области могут быть как простыми \(один прямоугольник\), так и сложными \(набор многоугольников и замкнутых кривых\).  На приведенном ниже рисунке изображены две области: одна из них образована прямоугольником, а другая образована контуром.  
  
 ![Области](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art27.png "AboutGdip02\_Art27")  
  
## Использование областей  
 Области часто используются для задания обрезки и для проверки попадания в некоторую зону.  Обрезка заключается в запрете на рисование вне границ определенной области экрана, обычно это область, нуждающаяся в обновлении.  Проверка на попадание заключается в определении, находился ли курсор в определенной области экрана, когда была нажата кнопка мыши.  
  
 Область можно построить на основе прямоугольника или контура.  .Можно также создавать сложные области путем объединения существующих областей.  У класса <xref:System.Drawing.Region> имеются следующие методы для объединения областей: <xref:System.Drawing.Region.Intersect%2A>, <xref:System.Drawing.Region.Union%2A>, <xref:System.Drawing.Region.Xor%2A>, <xref:System.Drawing.Region.Exclude%2A> и <xref:System.Drawing.Region.Complement%2A>.  
  
 Пересечение двух областей состоит из всех точек, принадлежащих обеим областям.  Объединение — это набор из всех точек, принадлежащих одной или обеим областям.  Дополнение области состоит из всех точек, не входящих в область.  На приведенном ниже рисунке изображено пересечение и объединение двух областей, изображенных на предыдущем рисунке.  
  
 ![Области](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art28.png "AboutGdip02\_Art28")  
  
 Метод <xref:System.Drawing.Region.Xor%2A>, примененный к паре областей, выдает область, содержащую все точки, которые принадлежат только одной из заданных областей, но не им обеим.  Метод <xref:System.Drawing.Region.Exclude%2A>, примененный к паре областей, выдает область, содержащую все точки первой области, не являющиеся точками второй области.  На приведенном ниже рисунке изображены области, полученные в результате применения методов <xref:System.Drawing.Region.Xor%2A> и <xref:System.Drawing.Region.Exclude%2A> к двум областям, изображение которых приведено в начале раздела.  
  
 ![Области](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art29.png "AboutGdip02\_Art29")  
  
 Чтобы залить область, требуются объекты <xref:System.Drawing.Graphics>, <xref:System.Drawing.Brush> и <xref:System.Drawing.Region>.  У объекта <xref:System.Drawing.Graphics> имеется метод <xref:System.Drawing.Graphics.FillRegion%2A>, а объект <xref:System.Drawing.Brush> предназначен для хранения таких параметров заливки, как ее цвет и шаблон.  В приведенном ниже примере демонстрируется заливка области сплошным цветом.  
  
 [!code-csharp[LinesCurvesAndShapes#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#61)]
 [!code-vb[LinesCurvesAndShapes#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#61)]  
  
## См. также  
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Использование областей](../../../../docs/framework/winforms/advanced/using-regions.md)