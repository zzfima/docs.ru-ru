---
title: "Практическое руководство. Разработка шрифтов и их семейств | Microsoft Docs"
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
  - "семейства шрифтов, создание"
  - "шрифты, создание"
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Практическое руководство. Разработка шрифтов и их семейств
Шрифты с одинаковым характером рисунка, но разными начертаниями группируются в интерфейсе [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] в семейства шрифтов.  Например, семейство шрифтов Arial содержит следующие шрифты:  
  
-   Arial Regular  
  
-   Arial Bold  
  
-   Arial Italic  
  
-   Arial Bold Italic  
  
 В интерфейсе [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] используются четыре начертания для формирования семейств шрифтов: обычный \(regular\), полужирный \(bold\), курсив \(italic\) и полужирный курсив \(bold italic\).  Такие прилагательные как *narrow \(узкий\)* или *rounded \(скругленный\)*  не определяют новых начертаний, а лишь являются частью имен семейств.  Например, Arial Narrow является семейством шрифтов, включающим следующие члены:  
  
-   Arial Narrow Regular  
  
-   Arial Narrow Bold  
  
-   Arial Narrow Italic  
  
-   Arial Narrow Bold Italic  
  
 Перед тем как выводить текст с помощью интерфейса [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], необходимо создать объекты <xref:System.Drawing.FontFamily> и <xref:System.Drawing.Font>.  Объект <xref:System.Drawing.FontFamily> определяет гарнитуру \(например Arial\), а объект <xref:System.Drawing.Font> указывает размер, начертание и единицы измерения.  
  
## Пример  
 В следующем примере создается шрифт Arial с обычным начертанием и размером, равным 16 пикселям.  В приведенном выше коде конструктор <xref:System.Drawing.Font.%23ctor%2A> получает в качестве своего первого параметра объект <xref:System.Drawing.FontFamily>.  Второй параметр определяет размер шрифта в единицах измерения, задаваемых в четвертом параметре.  Третий параметр указывает начертание шрифта.  
  
 Значение <xref:System.Drawing.GraphicsUnit> является членом перечисления <xref:System.Drawing.GraphicsUnit>, а значение <xref:System.Drawing.FontStyle> является членом перечисления <xref:System.Drawing.FontStyle>.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## Компиляция кода  
 Предыдущий пример предназначен для работы с Windows Forms, для него необходим объект <xref:System.Windows.Forms.PaintEventArgs> `e`, передаваемый в качестве параметра обработчику события <xref:System.Windows.Forms.PaintEventHandler>.  
  
## См. также  
 [Шрифты и текст](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Объекты Graphics и Drawing в Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)