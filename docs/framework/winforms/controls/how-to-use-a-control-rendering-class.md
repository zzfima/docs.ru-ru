---
title: "Практическое руководство. Использование класса отрисовки элемента управления | Microsoft Docs"
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
  - "профессиональный вид, отрисовка элементов управления Windows Forms"
  - "визуальные стили, отрисовка элементов управления Windows Forms"
  - "визуальные темы, применение к элементам управления Windows Forms"
ms.assetid: c0125e34-cd74-4c35-818c-3e40f462b0a3
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Использование класса отрисовки элемента управления
В следующем примере кода показывается, как использовать класс <xref:System.Windows.Forms.ComboBoxRenderer> для визуализации стрелки поля с раскрывающимся списком  Этот пример включает метод <xref:System.Windows.Forms.Control.OnPaint%2A> простого пользовательского элемента управления.  Свойство <xref:System.Windows.Forms.ComboBoxRenderer.IsSupported%2A?displayProperty=fullName> определяют, будут ли включены визуальные стили в клиентской области окон приложения.  Если визуальные стили включены, метод <xref:System.Windows.Forms.ComboBoxRenderer.DrawDropDownButton%2A?displayProperty=fullName> визуализирует стрелку поля с раскрывающимся списком в применением визуальных стилей; в противном случае, метод <xref:System.Windows.Forms.ControlPaint.DrawComboButton%2A?displayProperty=fullName> визуализирует эту стрелку в классическом стиле Windows.  
  
## Пример  
 [!code-cpp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/cpp/form1.cpp#10)]
 [!code-csharp[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms_ControlRenderer#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms_ControlRenderer/VB/form1.vb#10)]  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Пользовательский элемент управления, производный от класса <xref:System.Windows.Forms.Control>.  
  
-   <xref:System.Windows.Forms.Form> с элементом управления.  
  
-   Ссылки на пространства имен <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> и <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName>.  
  
## См. также  
 [Отрисовка элементов управления с применением визуальных стилей](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)