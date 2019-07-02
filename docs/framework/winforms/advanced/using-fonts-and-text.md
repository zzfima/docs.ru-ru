---
title: Шрифты и текст
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505118"
---
# <a name="using-fonts-and-text"></a>Шрифты и текст
Существует несколько классов, предоставляемых GDI + и GDI для рисования текста в формах Windows Forms. GDI + <xref:System.Drawing.Graphics> содержит несколько <xref:System.Drawing.Graphics.DrawString%2A> методы, которые позволяют указать различные свойства текста, таких как местоположение, ограничивающий прямоугольник, шрифт и формат. Кроме того, можно нарисовать и измерить текста с использованием GDI, с помощью статического <xref:System.Windows.Forms.TextRenderer.DrawText%2A> и <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> методы `TextRenderer` класса. Методы GDI также позволяют указывать расположение, шрифт и формат. Вы можете GDI или GDI + для прорисовки текста; Тем не менее GDI обычно обеспечивает более высокую производительность и более точные измерения текста. Другие классы, которые влияют на отрисовку текста включают `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, и `TextFormatFlags`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Шрифты и их семейств](how-to-construct-font-families-and-fonts.md)  
 Демонстрируется создание `Font` и `FontFamily` объектов.  
  
 [Практическое руководство. Рисование текста в указанном расположении](how-to-draw-text-at-a-specified-location.md)  
 Описывает способ рисования текста в определенном расположении с помощью GDI + и GDI.  
  
 [Практическое руководство. Многострочный вывод текста в прямоугольнике](how-to-draw-wrapped-text-in-a-rectangle.md)  
 Объясняется, как для рисования текста в прямоугольнике с помощью GDI + и GDI.  
  
 [Практическое руководство. Рисование текста с использованием GDI](how-to-draw-text-with-gdi.md)  
 В этой статье демонстрируется использование GDI для рисования текста.  
  
 [Практическое руководство. Выравнивание рисуемого текста](how-to-align-drawn-text.md)  
 Показано, как для форматирования текста GDI + и GDI.  
  
 [Практическое руководство. Вывод текста по вертикали](how-to-create-vertical-text.md)  
 Описывает способ рисования текста, выровненного по вертикали с помощью GDI +.  
  
 [Практическое руководство. Установка позиций табуляции для выводимого текста](how-to-set-tab-stops-in-drawn-text.md)  
 Рисование текста с позициями табуляции с помощью GDI +.  
  
 [Практическое руководство. Перебор установленных шрифтов](how-to-enumerate-installed-fonts.md)  
 Объясняется, как список установленных шрифтов.  
  
 [Практическое руководство. Создание частной коллекции шрифтов](how-to-create-a-private-font-collection.md)  
 Описывает создание <xref:System.Drawing.Text.PrivateFontCollection> объекта.  
  
 [Практическое руководство. Получение метрик шрифтов](how-to-obtain-font-metrics.md)  
 Демонстрируется получение метрик шрифтов, такие как восхождение клетки и спуска.  
  
 [Практическое руководство. Сглаживание текста](how-to-use-antialiasing-with-text.md)  
 В данной статье описывается использование сглаживание при рисовании текста.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Drawing.Font>  
 Описывает данный класс и содержит ссылки на все его члены.  
  
 <xref:System.Drawing.FontFamily>  
 Описывает данный класс и содержит ссылки на все его члены.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Описывает данный класс и содержит ссылки на все его члены.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Описывает данный класс и содержит ссылки на все его члены.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Описывает данный класс и содержит ссылки на все его члены.
