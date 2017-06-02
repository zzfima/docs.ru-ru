---
title: "Практическое руководство. Рисование текста с использованием GDI | Microsoft Docs"
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
  - "рисование, текст"
  - "GDI, рисование текста [Windows Forms]"
  - "текст, рисование с использованием TextRenderer"
  - "Windows Forms, рисование текста с помощью GDI"
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Рисование текста с использованием GDI
Метод <xref:System.Windows.Forms.TextRenderer.DrawText%2A> класса <xref:System.Windows.Forms.TextRenderer> позволяет использовать функциональность [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], связанную с возможностями размещения текста на форме или элементе управления.  Функции отрисовки текста [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] в большинстве случаев обладают большей производительностью и более точно управляют параметрами текста, чем функции [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
> [!NOTE]
>  Методы <xref:System.Windows.Forms.TextRenderer.DrawText%2A> класса <xref:System.Windows.Forms.TextRenderer> не поддерживаются для печати.  Для печати всегда следует использовать методы <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>.  
  
## Пример  
 В следующем примере демонстрируется рисование текста на нескольких строках внутри прямоугольника с помощью метода <xref:System.Windows.Forms.TextRenderer.DrawText%2A>.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Чтобы отобразить с помощью класса <xref:System.Windows.Forms.TextRenderer> какой\-либо текст, потребуется интерфейс <xref:System.Drawing.IDeviceContext>, например <xref:System.Drawing.Graphics> и <xref:System.Drawing.Font>, а также место для вывода текста и цвет этого текста.  Формат текста можно также указать с помощью перечисления <xref:System.Windows.Forms.TextFormatFlags>.  
  
 Дополнительные сведения о получении объекта <xref:System.Drawing.Graphics> см. в разделе [Практическое руководство. Создание объектов Graphics для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).  Дополнительные сведения о создании объекта <xref:System.Drawing.Font> см. в разделе [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).  
  
## Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 <xref:System.Windows.Forms.TextRenderer>   
 <xref:System.Drawing.Font>   
 <xref:System.Drawing.Color>   
 <xref:System.Drawing.Color>   
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)