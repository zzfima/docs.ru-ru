---
title: "Ограничение поверхности для рисования в GDI+ | Microsoft Docs"
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
  - "усечение, использование GDI+"
  - "GDI+, усечение"
  - "GDI+, ограничение поверхности для рисования"
ms.assetid: 8b5f71d9-d2f0-4540-9c41-740f90fd4c26
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Ограничение поверхности для рисования в GDI+
Обрезка заключается в запрете рисования за пределами определенного прямоугольника или области.  На приведенном ниже рисунке изображена строка "Hello", выведенная с использованием обрезки в область в форме сердца.  
  
 ![Ограничение поверхности для рисования](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art30.png "AboutGdip02\_Art30")  
  
## Задание области обрезки  
 Области можно создавать из контуров, а контуры могут содержать границы строк, поэтому для обрезки можно использовать контуры текста.  На приведенном ниже рисунке изображен набор концентрических эллипсов, выведенных с использованием обрезки во внутреннюю область строки текста.  
  
 ![Ограничение поверхности для рисования](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art31.png "AboutGdip02\_Art31")  
  
 Чтобы нарисовать что\-либо с использованием обрезки, нужно создать объект <xref:System.Drawing.Graphics>, задать его свойство <xref:System.Drawing.Graphics.Clip%2A>, а затем вызывать методы рисования этого объекта <xref:System.Drawing.Graphics>.  
  
 [!code-csharp[LinesCurvesAndShapes#91](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#91)]
 [!code-vb[LinesCurvesAndShapes#91](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#91)]  
  
## См. также  
 <xref:System.Drawing.Graphics?displayProperty=fullName>   
 <xref:System.Drawing.Region?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Использование областей](../../../../docs/framework/winforms/advanced/using-regions.md)