---
title: "Шрифты и текст | Microsoft Docs"
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
  - "примеры [Windows Forms], шрифты и текст"
  - "шрифты, использование в Windows Forms"
  - "GDI, рисование текста [Windows Forms]"
  - "строки [Windows Forms], рисование в Windows Forms"
  - "текст [Windows Forms], рисование в Windows Forms"
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Шрифты и текст
В [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] имеется несколько классов для рисования текста на формах Windows Forms.  Класс [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] <xref:System.Drawing.Graphics> содержит несколько методов <xref:System.Drawing.Graphics.DrawString%2A>, позволяющих указывать различные свойства текста, такие как расположение, ограничивающий прямоугольник, шрифт и формат.  Кроме того, для вывода текста и управления его параметрами в [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] можно использовать статические методы <xref:System.Windows.Forms.TextRenderer.DrawText%2A> и <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> класса `TextRenderer`.  Методы [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] также позволяют указывать расположение, шрифт и формат текста.  Для отрисовки текста можно выбрать интерфейс [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] или [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], однако в большинстве случаев [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] обеспечивает более высокую производительность и четкость в отображении текста.  К другим классам, участвующим в отрисовке текста, относятся классы `FontFamily`, `Font`, <xref:System.Drawing.StringFormat> и `TextFormatFlags`.  
  
## В этом подразделе  
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 Создание объектов `Font` и `FontFamily`.  
  
 [Практическое руководство. Рисование текста в указанной позиции](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)  
 Рисование текста в нужном месте с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Практическое руководство. Многострочный вывод текста в прямоугольнике](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)  
 Рисование текста в прямоугольнике с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 Использование [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] для рисования текста.  
  
 [Практическое руководство. Выравнивание рисуемого текста](../../../../docs/framework/winforms/advanced/how-to-align-drawn-text.md)  
 Форматирование текста в [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] и [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 [Практическое руководство. Вывод текста по вертикали](../../../../docs/framework/winforms/advanced/how-to-create-vertical-text.md)  
 Рисование выровненного по вертикали текста с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Практическое руководство. Установка позиций табуляции для выводимого текста](../../../../docs/framework/winforms/advanced/how-to-set-tab-stops-in-drawn-text.md)  
 Рисование текста с позициями табуляции с помощью [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 [Практическое руководство. Перебор установленных шрифтов](../../../../docs/framework/winforms/advanced/how-to-enumerate-installed-fonts.md)  
 Получение списка установленных шрифтов.  
  
 [Практическое руководство. Создание частной коллекции шрифтов](../../../../docs/framework/winforms/advanced/how-to-create-a-private-font-collection.md)  
 Создание объекта <xref:System.Drawing.Text.PrivateFontCollection>.  
  
 [Практическое руководство. Получение метрик шрифтов](../../../../docs/framework/winforms/advanced/how-to-obtain-font-metrics.md)  
 Получение численных характеристик шрифтов, в том числе размеров верхних и нижних выносных элементов.  
  
 [Практическое руководство. Сглаживание текста](../../../../docs/framework/winforms/advanced/how-to-use-antialiasing-with-text.md)  
 Использование сглаживания при рисовании текста.  
  
## Ссылка  
 <xref:System.Drawing.Font>  
 Описание класса и ссылки на разделы с описаниями всех его членов.  
  
 <xref:System.Drawing.FontFamily>  
 Описание класса и ссылки на разделы с описаниями всех его членов.  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 Описание класса и ссылки на разделы с описаниями всех его членов.  
  
 <xref:System.Windows.Forms.TextRenderer>  
 Описание класса и ссылки на разделы с описаниями всех его членов.  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 Описание класса и ссылки на разделы с описаниями всех его членов.