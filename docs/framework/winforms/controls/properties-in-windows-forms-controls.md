---
title: "Свойства элементов управления Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5de09635fb92b46a2c0f89427ad03449de6bd53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="properties-in-windows-forms-controls"></a>Свойства элементов управления Windows Forms
Элемент управления Windows Forms наследует много свойств базового класса <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. К ним относятся свойства, такие как <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>и многие другие. Дополнительные сведения о наследуемых свойств см. в разделе <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 Вы можете переопределять наследуемые свойства в элементе управления, а также задавать новые свойства.  
  
## <a name="in-this-section"></a>Содержание  
 [Определение свойства](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 Показывает, как реализовать свойство настраиваемого элемента управления или компонента и интегрировать свойство в среду разработки.  
  
 [Определение значений по умолчанию с помощью методов ShouldSerialize и Reset](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Показывает, как определить значения свойства по умолчанию для настраиваемого элемента управления или компонента.  
  
 [События изменения свойств](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 Показывает, как включить уведомления об изменении свойств при изменении значения свойства.  
  
 [Практическое руководство. Обеспечение доступа к свойствам составных элементов управления](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 Показывает, как предоставить доступ к свойствам составных элементов управления в настраиваемом составном элементе управления.  
  
 [Реализация методов в специализированных элементах управления](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 Показывает, как реализовывать методы в настраиваемых элементах управления и компонентах.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.Windows.Forms.UserControl>  
 Описание базового класса для реализации составных элементов управления.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Документирует атрибут, задающий <xref:System.ComponentModel.TypeConverter> для типа пользовательского свойства.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Документирует атрибут, задающий <xref:System.Drawing.Design.UITypeEditor> для пользовательского свойства.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Атрибуты в элементах управления Windows Forms](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 Описываются атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов.  
  
 [Атрибуты времени разработки для компонентов](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.  
  
 [Расширения поддержки времени разработки](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 Описывается, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку во время разработки.
