---
title: "Практическое руководство. Перебор установленных шрифтов | Microsoft Docs"
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
  - "примеры [Windows Forms], шрифты"
  - "шрифты, перечисление установленного"
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Перебор установленных шрифтов
Класс <xref:System.Drawing.Text.InstalledFontCollection> наследуется от абстрактного базового класса <xref:System.Drawing.Text.FontCollection>.  Объект <xref:System.Drawing.Text.InstalledFontCollection> служит для хранения перечисления шрифтов, установленных на компьютере.  Свойство <xref:System.Drawing.Text.FontCollection.Families%2A> объекта <xref:System.Drawing.Text.InstalledFontCollection> является массивом объектов <xref:System.Drawing.FontFamily>.  
  
## Пример  
 В следующем примере выводится список названий всех семейств шрифтов, установленных на компьютере.  Приведенный код извлекает свойство <xref:System.Drawing.FontFamily.Name%2A> каждого объекта <xref:System.Drawing.FontFamily>, содержащегося в массиве, возвращаемом свойством <xref:System.Drawing.Text.FontCollection.Families%2A>.  По мере извлечения имена семейств шрифтов объединяются в список имен, разделенных запятыми.  Затем метод <xref:System.Drawing.Graphics.DrawString%2A> класса <xref:System.Drawing.Graphics> рисует список имен, разделенных запятыми, в прямоугольнике.  
  
 Результат выполнения этого кода будет аналогичен приведенному на следующем рисунке.  
  
 ![Установленные шрифты](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику событий <xref:System.Windows.Forms.PaintEventHandler>.  Кроме того, нужно импортировать пространство имен <xref:System.Drawing.Text>.  
  
## См. также  
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)