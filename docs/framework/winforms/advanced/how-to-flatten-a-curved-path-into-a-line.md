---
title: "Практическое руководство. Спрямление участков кривой | Microsoft Docs"
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
  - "кривые, спрямление"
  - "рисование, спрямление кривых"
  - "Flatten - метод"
  - "графика, спрямления кривых до линий"
  - "GraphicsPath - объект"
  - "пути, спрямление"
ms.assetid: e654b8de-25f4-4735-9208-42e4514a589c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Спрямление участков кривой
В объекте <xref:System.Drawing.Drawing2D.GraphicsPath> хранятся последовательности линий и сплайнов Безье.  К контуру можно добавлять различные типы кривых \(эллипсы, дуги и фундаментальные сплайны\), но перед сохранением в контуре каждая кривая преобразуется в сплайн Безье.  Спрямление контура заключается в преобразовании всех сплайнов Безье в последовательность отрезков прямых линий.  На приведенном ниже рисунке изображен контур до и после спрямления.  
  
 ![Прямые линии и кривые](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art32a.png "AboutGdip02\_Art32A")  
  
### Спрямление контура  
  
-   Вызовите метод <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> объекта <xref:System.Drawing.Drawing2D.GraphicsPath>.  Метод <xref:System.Drawing.Drawing2D.GraphicsPath.Flatten%2A> получает в качестве параметра аргумент спрямления, задающий максимально допустимое расстояние между спрямленным и исходным контуром.  
  
## См. также  
 <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=fullName>   
 [Прямые и кривые линии и фигуры](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)   
 [Построение и рисование контуров](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)