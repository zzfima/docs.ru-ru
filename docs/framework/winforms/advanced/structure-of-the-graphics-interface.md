---
title: "Структура интерфейса Graphics"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 43bd899a1dd53dc8cdae4f81e90b1aa74c29cb67
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="structure-of-the-graphics-interface"></a>Структура интерфейса Graphics
Интерфейс управляемых классов [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] содержит около 60 классов, 50 перечислений и 8 структур. <xref:System.Drawing.Graphics> Класс является основой [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] функциональные возможности; это класс, который фактически рисует линии, кривые, фигур, изображений и текста.  
  
## <a name="important-classes"></a>Важные классы  
 Многие классы работают совместно с <xref:System.Drawing.Graphics> класса. Например <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> объекта, который хранит атрибуты рисуемой линии (цвет, ширину, стиль штриха и like). <xref:System.Drawing.Graphics.FillRectangle%2A> Метод может получить указатель на <xref:System.Drawing.Drawing2D.LinearGradientBrush> объекта, который работает с <xref:System.Drawing.Graphics> объекта для заполнения прямоугольника постепенно изменения цвета. <xref:System.Drawing.Font>и <xref:System.Drawing.StringFormat> объектов влияют на способ <xref:System.Drawing.Graphics> объект рисуется текст. Объект <xref:System.Drawing.Drawing2D.Matrix> объект хранит и управляет мировое преобразование объекта <xref:System.Drawing.Graphics> объекта, который используется для вращения, масштабирования и зеркальное отражение изображения.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]предоставляет несколько структур (например, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, и <xref:System.Drawing.Size>) для хранения графических данных. Кроме того некоторые классы служат в основном как структурированные типы данных. Например <xref:System.Drawing.Imaging.BitmapData> класс представляет вспомогательный класс для <xref:System.Drawing.Bitmap> класса и <xref:System.Drawing.Drawing2D.PathData> класс представляет вспомогательный класс для <xref:System.Drawing.Drawing2D.GraphicsPath> класса.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]определяет несколько перечислений, которые представляют собой наборы связанных констант. Например <xref:System.Drawing.Drawing2D.LineJoin> перечисление содержит элементы <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, и <xref:System.Drawing.Drawing2D.LineJoin.Round>, указывающие, стили, которые можно использовать для соединения двух строк.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о графике](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [Управляемый код GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Использование управляемых графических классов](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
