---
title: "Поля и заполнение в элементах управления Windows Forms | Microsoft Docs"
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
  - "макет [Windows Forms], задание полей и интервалов"
  - "Margin - свойство [Windows Forms]"
  - "Padding - свойство [Windows Forms]"
  - "Windows Forms, макет"
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Поля и заполнение в элементах управления Windows Forms
Точное расположение элементов управления на форме является важным для многих приложений.  Пространство имен <xref:System.Windows.Forms?displayProperty=fullName> предоставляет множество возможностей компоновки для решения этой задачи.  Свойства <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> — одни из наиболее важных.  
  
 Свойство <xref:System.Windows.Forms.Control.Margin%2A> определяет поле вокруг элемента управления, благодаря которому обеспечивается определенное расстояние между границами этого элемента и другими элементами.  
  
 Свойство <xref:System.Windows.Forms.Control.Padding%2A> определяет поле внутри элемента управления, благодаря которому обеспечивается определенное расстояние между содержимым элемента управления \(например, значением свойства <xref:System.Windows.Forms.Control.Text%2A>\) и его границами.  
  
 На рисунке ниже демонстрируется значение свойств <xref:System.Windows.Forms.Control.Padding%2A> и <xref:System.Windows.Forms.Control.Margin%2A> элемента управления.  
  
 ![Поля и заполнение для элементов управления Windows Forms](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS\_WinFormPadMargin")  
  
 Эта возможность поддерживается на этапе разработки в Visual Studio.  См. также [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.Control.AutoSize%2A>   
 <xref:System.Windows.Forms.Control.Margin%2A>   
 <xref:System.Windows.Forms.Control.Padding%2A>   
 <xref:System.Windows.Forms.Control.LayoutEngine%2A>   
 <xref:System.Windows.Forms.TableLayoutPanel>   
 <xref:System.Windows.Forms.FlowLayoutPanel>