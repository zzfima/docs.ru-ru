---
title: "Структура интерфейса Graphics | Microsoft Docs"
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
  - "GDI+, использование управляемых интерфейсов"
  - "графика, структура класса"
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Структура интерфейса Graphics
Интерфейс управляемых классов [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] содержит около 60 классов, 50 перечислений и 8 структур.  Класс <xref:System.Drawing.Graphics> является основой интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], этот класс непосредственно выполняет рисование прямых и кривых линий, геометрических фигур, вывод рисунков и текста.  
  
## Важные классы  
 Многие классы работают совместно с классом <xref:System.Drawing.Graphics>.  Например, метод <xref:System.Drawing.Graphics.DrawLine%2A> получает объект <xref:System.Drawing.Pen>, содержащий атрибуты рисуемой линии, такие как цвет, ширина, наличие или отсутствие пунктира и т. п.  Метод <xref:System.Drawing.Graphics.FillRectangle%2A> может получать указатель на объект <xref:System.Drawing.Drawing2D.LinearGradientBrush>, работающий совместно с объектом <xref:System.Drawing.Graphics> и реализующий заполнение прямоугольника постепенно меняющимся цветом.  Объекты <xref:System.Drawing.Font> и <xref:System.Drawing.StringFormat> определяют то, как объект <xref:System.Drawing.Graphics> выводит на экран текст.  Объект <xref:System.Drawing.Drawing2D.Matrix> обеспечивает выполнение различных действий по объемным преобразованиям объекта <xref:System.Drawing.Graphics>, которые используются для вращения, масштабирования и отражения рисунков.  
  
 Интерфейс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] предоставляет несколько структур, таких как <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point> и <xref:System.Drawing.Size>, которые используются для хранения графических данных.  Некоторые классы также используются, в основном, как структурированные типы данных.  Например, класс <xref:System.Drawing.Imaging.BitmapData> является вспомогательным хранилищем данных для класса <xref:System.Drawing.Bitmap>, а класс <xref:System.Drawing.Drawing2D.PathData> является вспомогательным хранилищем данных для класса <xref:System.Drawing.Drawing2D.GraphicsPath>.  
  
 В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] определены несколько перечислений, которые являются коллекциями связанных констант.  Например, перечисление <xref:System.Drawing.Drawing2D.LineJoin> содержит элементы <xref:System.Drawing.Drawing2D.LineJoin>, <xref:System.Drawing.Drawing2D.LineJoin> и <xref:System.Drawing.Drawing2D.LineJoin>, определяющие стили соединения линий.  
  
## См. также  
 [Общие сведения о графике](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)   
 [Управляемый код GDI\+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)   
 [Использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)