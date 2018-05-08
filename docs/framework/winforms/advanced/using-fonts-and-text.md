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
ms.openlocfilehash: d157b51e24009d847dede9ea6a9f81c8898c5b06
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-fonts-and-text"></a>Шрифты и текст
Существует несколько классов, предоставляемых [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] для рисования текста в формах Windows Forms. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> Содержит несколько <xref:System.Drawing.Graphics.DrawString%2A> методы, которые позволяют указать различные свойства текста, такие как расположение, ограничивающий прямоугольник, шрифт и формат. Кроме того, можно нарисовать и измерить текста с [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] с помощью статического <xref:System.Windows.Forms.TextRenderer.DrawText%2A> и <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> методы, предоставляемые `TextRenderer` класса. [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Методы также позволяют указывать расположение, шрифт и формат. Вы также можете выбрать [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] или [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] для отрисовки текста; Однако [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] обычно предлагает более высокую производительность и более точного текста измерения. Включить других классов, предназначенных для отрисовки текста `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, и `TextFormatFlags`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Показано, как создать `Font` и `FontFamily` объектов.  
  
 [Практическое руководство. Рисование текста в указанной позиции](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Рисование текста в нужном месте с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Практическое руководство. Многострочный вывод текста в прямоугольнике](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Рисование текста в прямоугольнике с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Демонстрируется использование [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] для рисования текста.  
  
 [Практическое руководство. Выравнивание рисуемого текста](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Форматирование [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] текста.  
  
 [Практическое руководство. Вывод текста по вертикали](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Рисование текста, выровненного по вертикали с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Практическое руководство. Установка позиций табуляции для выводимого текста](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Рисование текста с позициями табуляции с [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Практическое руководство. Перебор установленных шрифтов](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Объясняется, как вывести список имен установленных шрифтов.  
  
 [Практическое руководство. Создание частной коллекции шрифтов](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Описывает способ создания <xref:System.Drawing.Text.PrivateFontCollection> объекта.  
  
 [Практическое руководство. Получение метрик шрифтов](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Показано, как получение метрик шрифтов, такие как Восхождение ячейки и спуск.  
  
 [Практическое руководство. Сглаживание текста](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 Описание способов использования сглаживание при рисовании текста.  
  
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
