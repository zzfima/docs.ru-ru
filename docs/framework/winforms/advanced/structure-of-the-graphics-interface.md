---
title: Структура интерфейса Graphics
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: d3b16249b6bae4a113661f5a3a47097046ba20f1
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505278"
---
# <a name="structure-of-the-graphics-interface"></a>Структура интерфейса Graphics
Интерфейс управляемых классов в GDI + содержит около 60 классов, 50 перечислений и 8 структур. <xref:System.Drawing.Graphics> Класс в основные функциональные возможности GDI +, это класс, который фактически рисует линий, кривых, фигур, изображений и текста.  
  
## <a name="important-classes"></a>Важные классы  
 Многие классы работают вместе с <xref:System.Drawing.Graphics> класса. Например <xref:System.Drawing.Graphics.DrawLine%2A> метод получает <xref:System.Drawing.Pen> объект, который содержит атрибуты линии для отрисовки (цвет, ширину, штриха и т.п). <xref:System.Drawing.Graphics.FillRectangle%2A> Метод может получить указатель на <xref:System.Drawing.Drawing2D.LinearGradientBrush> объект, который работает с <xref:System.Drawing.Graphics> объекта для заполнения прямоугольника постепенного изменения цвета. <xref:System.Drawing.Font> и <xref:System.Drawing.StringFormat> объектов влияют на способ <xref:System.Drawing.Graphics> объект Рисует текст. Объект <xref:System.Drawing.Drawing2D.Matrix> объект хранит и управляет мировое преобразование объекта <xref:System.Drawing.Graphics> объект, который используется для поворота, масштабирования и отражать изображения.  
  
 GDI + предоставляет несколько структур (например, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Point>, и <xref:System.Drawing.Size>) для хранения графических данных. Кроме того некоторые классы служат главным образом как структурированные типы данных. Например <xref:System.Drawing.Imaging.BitmapData> класс — это вспомогательный объект для <xref:System.Drawing.Bitmap> класса и <xref:System.Drawing.Drawing2D.PathData> класс — это вспомогательный объект для <xref:System.Drawing.Drawing2D.GraphicsPath> класса.  
  
 GDI + определены несколько перечислений, которые являются коллекциями связанных констант. Например <xref:System.Drawing.Drawing2D.LineJoin> перечисление содержит элементы <xref:System.Drawing.Drawing2D.LineJoin.Bevel>, <xref:System.Drawing.Drawing2D.LineJoin.Miter>, и <xref:System.Drawing.Drawing2D.LineJoin.Round>, которые определяют стили, которые могут использоваться для соединения двух строк.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о графике](graphics-overview-windows-forms.md)
- [Управляемый код GDI+](about-gdi-managed-code.md)
- [Использование управляемых графических классов](using-managed-graphics-classes.md)
