---
title: "Свойства элементов управления Windows Forms | Microsoft Docs"
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
  - "элементы управления [Windows Forms], свойства"
  - "пользовательские элементы управления [Windows Forms], общие сведения о свойтсвах (с использованием кода)"
  - "свойства [Windows Forms]"
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Свойства элементов управления Windows Forms
Элемент управления Windows Forms наследует много свойств базового класса <xref:System.Windows.Forms.Control?displayProperty=fullName>.  В число этих свойств входят следующие: <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A> и многие другие.  Подробные сведения о наследованных свойствах см. в разделе <xref:System.Windows.Forms.Control?displayProperty=fullName>.  
  
 Можно переопределить наследуемые свойства в элементе управления пользователя, а также определить новые свойства.  
  
## В этом подразделе  
 [Определение свойства](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 Продемонстрировано, как реализовать свойство пользовательского элемента управления и показано, как интегрировать свойство с среду разработки.  
  
 [Определение значений по умолчанию с помощью методов ShouldSerialize и Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Показано, как определить значения свойства по умолчанию для пользовательского элемента управления или компонента.  
  
 [События изменения свойств](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 Описание порядка включения уведомлений об изменений свойств при изменении значений свойства.  
  
 [Практическое руководство. Обеспечение доступа к свойствам составных элементов управления](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 Описание порядка предоставления свойств составного элемента управления в пользовательском составном элементе управления.  
  
 [Реализация методов в специализированных элементах управления](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 Описание порядка реализации методов в пользовательских элементах управления и компонентах.  
  
## Ссылка  
 <xref:System.Windows.Forms.UserControl>  
 Документирование базового класса для реализации составных элементов управления.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Документирование атрибута, определяющего использование <xref:System.ComponentModel.TypeConverter> для типа пользовательского свойства.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Документирование атрибута, определяющего использование <xref:System.Drawing.Design.UITypeEditor> для пользовательского свойства.  
  
## Связанные подразделы  
 [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 Описание атрибутов, которые можно применять к свойствам или другим членам собственных элементов управления и компонентов.  
  
 [Design\-Time Attributes for Components](../Topic/Design-Time%20Attributes%20for%20Components.md)  
 Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.  
  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)  
 Описано, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку режима разработки.