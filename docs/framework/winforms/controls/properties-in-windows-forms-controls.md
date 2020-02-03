---
title: Свойства элементов управления
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
ms.openlocfilehash: 82bfab15cef4946661a37d2d88fbe1b797f3d816
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741178"
---
# <a name="properties-in-windows-forms-controls"></a>Свойства элементов управления Windows Forms
Windows Forms элемент управления наследует многие свойства, образуя базовый класс <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. К ним относятся такие свойства, как <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>и многие другие. Дополнительные сведения о наследованных свойствах см. в разделе <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.  
  
 Вы можете переопределять наследуемые свойства в элементе управления, а также задавать новые свойства.  
  
## <a name="in-this-section"></a>в этом разделе  
 [Определение свойства](defining-a-property-in-windows-forms-controls.md)  
 Показывает, как реализовать свойство настраиваемого элемента управления или компонента и интегрировать свойство в среду разработки.  
  
 [Определение значений по умолчанию с помощью методов ShouldSerialize и Reset](defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 Показывает, как определить значения свойства по умолчанию для настраиваемого элемента управления или компонента.  
  
 [События изменения свойств](property-changed-events.md)  
 Показывает, как включить уведомления об изменении свойств при изменении значения свойства.  
  
 [Практическое руководство. Обеспечение доступа к свойствам составных элементов управления](how-to-expose-properties-of-constituent-controls.md)  
 Показывает, как предоставить доступ к свойствам составных элементов управления в настраиваемом составном элементе управления.  
  
 [Реализация методов в специализированных элементах управления](method-implementation-in-custom-controls.md)  
 Показывает, как реализовывать методы в настраиваемых элементах управления и компонентах.  
  
## <a name="reference"></a>Справочник  
 <xref:System.Windows.Forms.UserControl>  
 Описание базового класса для реализации составных элементов управления.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 Документирует атрибут, указывающий <xref:System.ComponentModel.TypeConverter>, используемый для пользовательского типа свойства.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 Документирует атрибут, указывающий <xref:System.Drawing.Design.UITypeEditor>, используемый для пользовательского свойства.  
  
## <a name="related-sections"></a>См. также  
 [Атрибуты в элементах управления Windows Forms](attributes-in-windows-forms-controls.md)  
 Описываются атрибуты, которые можно применять к свойствам или другим членам пользовательских элементов управления и компонентов.  
  
 [Атрибуты времени разработки для компонентов](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))  
 Перечислены атрибуты метаданных, которые нужно применить к компонентам и элементам управления, чтобы они корректно отображались в режиме разработки в визуальных конструкторах.  
  
 [Расширения поддержки времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))  
 Описывается, как реализовать такие классы, как редакторы и конструкторы, обеспечивающие поддержку во время разработки.
