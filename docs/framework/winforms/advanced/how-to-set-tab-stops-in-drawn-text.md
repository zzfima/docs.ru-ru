---
title: "Практическое руководство. Установка позиций табуляции для выводимого текста | Microsoft Docs"
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
  - "вкладки, рисование текста"
  - "текст, рисование с позициями табуляции"
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Установка позиций табуляции для выводимого текста
Для текста можно устанавливать позиции табуляции. Для этого необходимо вызвать метод <xref:System.Drawing.StringFormat.SetTabStops%2A> объекта <xref:System.Drawing.StringFormat>, а затем передать этот объект <xref:System.Drawing.StringFormat> методу <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>.  
  
> [!NOTE]
>  Класс <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName> не поддерживает добавление позиций табуляции к выведенному тексту, хотя и возможно расширение существующих позиций табуляции с помощью флага <xref:System.Windows.Forms.TextFormatFlags?displayProperty=fullName>.  
  
## Пример  
 В следующем примере позиции табуляции устанавливаются на 150, 250 и 350.  Затем код выводит табулированный список имен и результатов теста.  
  
 Табулированный текст показан на следующем рисунке.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 Приведенный ниже код передает методу <xref:System.Drawing.StringFormat.SetTabStops%2A> два параметра.  Вторым параметром является массив, содержащий смещения позиций табуляции.  В качестве первого параметра методу <xref:System.Drawing.StringFormat.SetTabStops%2A> передается 0; это означает, что первое смещение в массиве отсчитывается от позиции 0, т. е. от левого края ограничивающего прямоугольника.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## Компиляция кода  
  
-   Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)