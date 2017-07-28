---
title: "Практическое руководство. Автоматическое слияние меню в приложениях MDI | Microsoft Docs"
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
  - "MenuStrip, слияние"
  - "слияние, автоматическое меню"
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Автоматическое слияние меню в приложениях MDI
Следующая процедура описывает действия по настройке автоматического слияния меню в приложениях MDI с <xref:System.Windows.Forms.MenuStrip>.  
  
### Для настройки автоматического слияния меню  
  
1.  Создайте родительскую форму MDI путем присвоения свойству <xref:System.Windows.Forms.Form.IsMdiContainer%2A> значения `true`.  
  
2.  Добавьте элемент <xref:System.Windows.Forms.MenuStrip> к родительскому элементу MDI, установив его свойство <xref:System.Windows.Forms.Form.MainMenuStrip%2A> равным <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Создайте дочернюю форму MDI и установите ее свойство <xref:System.Windows.Forms.Form.MdiParent%2A> равным имени родительской формы.  
  
4.  Добавьте в дочернюю форму MDI элемент управления <xref:System.Windows.Forms.MenuStrip>.  
  
5.  В дочерней форме задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Visible%2A> элемента <xref:System.Windows.Forms.MenuStrip> значение `false`.  
  
6.  Добавьте пункты меню в элемент <xref:System.Windows.Forms.MenuStrip> дочерней формы, который требуется объединить с элементом <xref:System.Windows.Forms.MenuStrip> родительской формы при активации дочерней формы.  
  
7.  Используйте свойство <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> пунктов меню в элементе <xref:System.Windows.Forms.MenuStrip> дочерней формы для управления слиянием в родительской форме.  
  
## См. также  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Общие сведения об элементе управления MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)