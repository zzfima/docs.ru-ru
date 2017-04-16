---
title: "Практическое руководство. Сглаживание текста | Microsoft Docs"
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
  - "сглаживание, использование с текстом"
  - "строки [Windows Forms], сглаживание при рисовании"
  - "строки [Windows Forms], смягчение рисования"
  - "текст [Windows Forms], сглаживание"
  - "текст [Windows Forms], смягчение"
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Сглаживание текста
*Сглаживанием* называют "смягчение" неровных границ графических элементов и текста для улучшения их внешнего вида или повышения удобочитаемости.  Управляемые классы [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] позволяют выводить на экран высококачественный сглаженный текст, а также текст низкого качества.  Обычно более качественная отрисовка требует больших затрат вычислительных ресурсов, чем менее качественная.  Для задания уровня качества отображения текста следует установить свойство <xref:System.Drawing.Graphics.TextRenderingHint%2A> объекта <xref:System.Drawing.Graphics> равным одному из значений перечисления <xref:System.Drawing.Text.TextRenderingHint>.  
  
## Пример  
 В следующем примере кода текст прорисовывается с двумя различными уровнями качества.  
  
 На следующем рисунке показан результат выполнения этого кода.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)