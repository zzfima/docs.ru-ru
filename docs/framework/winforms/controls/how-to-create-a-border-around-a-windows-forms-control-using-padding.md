---
title: "Практическое руководство. Создание рамки вокруг элемента управления в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "элементы управления [Windows Forms], Margin - свойство"
  - "элементы управления [Windows Forms], структуризация"
  - "элементы управления [Windows Forms], Padding - свойство"
  - "Margin - свойство [Windows Forms]"
  - "поля"
  - "поля, Windows Forms"
  - "Padding - свойство [Windows Forms]"
  - "заполнение, Windows Forms"
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Создание рамки вокруг элемента управления в Windows Forms
В следующем примере демонстрируется создание границы или контура вокруг элемента управления <xref:System.Windows.Forms.RichTextBox>.  В этом примере свойству <xref:System.Windows.Forms.Padding> элемента управления <xref:System.Windows.Forms.Panel> присваивается значение 5, а свойству <xref:System.Windows.Forms.Control.Dock%2A> дочернего элемента управления <xref:System.Windows.Forms.RichTextBox> присваивается значение <xref:System.Windows.Forms.DockStyle>.  Свойству <xref:System.Windows.Forms.Control.BackColor%2A> элемента управления <xref:System.Windows.Forms.Panel> присваивается значение <xref:System.Drawing.Color.Blue%2A>, что создает голубую границу вокруг элемента управления <xref:System.Windows.Forms.RichTextBox>.  
  
## Пример  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## См. также  
 <xref:System.Windows.Forms.Padding>   
 [Поля и заполнение в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)