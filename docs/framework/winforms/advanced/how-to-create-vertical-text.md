---
title: "Практическое руководство. Вывод текста по вертикали | Microsoft Docs"
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
  - "строки [Windows Forms], рисование вертикального"
  - "текст [Windows Forms], рисование вертикального"
  - "вертикальный текст, рисование"
  - "Windows Forms, рисование вертикального текста"
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Вывод текста по вертикали
Чтобы указать, что текст должен выводиться по вертикали, а не по горизонтали, можно использовать объект <xref:System.Drawing.StringFormat>.  
  
## Пример  
 В следующем примере значение <xref:System.Drawing.StringFormatFlags> присваивается свойству <xref:System.Drawing.StringFormat.FormatFlags%2A> объекта <xref:System.Drawing.StringFormat>.  Этот объект <xref:System.Drawing.StringFormat> передается методу <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics>.  Значение <xref:System.Drawing.StringFormatFlags> является членом перечисления <xref:System.Drawing.StringFormatFlags>.  
  
 Нарисованный вертикальный текст показан на следующем рисунке.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## Компиляция кода  
  
-   Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e` , передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)