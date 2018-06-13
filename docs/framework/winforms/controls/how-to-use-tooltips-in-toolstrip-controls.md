---
title: Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 2b10b3fcf3930d5848f1d7a9602cfcc945bc8975
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534077"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip
Можно отобразить <xref:System.Windows.Forms.ToolTip> для <xref:System.Windows.Forms.ToolStrip> управления, присвоив элемента управления <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> свойства `true`.  
  
### <a name="to-display-a-tooltip"></a>Для отображения всплывающей подсказки  
  
-   Задать <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> свойства элемента управления для `true`.  
  
     Значение по умолчанию <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> — `true`и значение по умолчанию <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> — `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>Чтобы использовать свойство ToolTipText для ToolStripButton текст всплывающей подсказки  
  
1.  Задать <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> свойства кнопки, чтобы `true`.  
  
2.  Задать <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> свойства кнопки, чтобы `false`.  
  
     `AutoToolTip` Свойство `true` по умолчанию для <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, и <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     Объект <xref:System.Windows.Forms.ToolStripButton> использует его `Text` свойство <xref:System.Windows.Forms.ToolTip> текст по умолчанию. Эта процедура используется для отображения пользовательского текста в <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.  
  
> [!NOTE]
>  Если задать <xref:System.Windows.Forms.ToolStripItemDisplayStyle> для <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, текст не будет отображаться на кнопке, но по-прежнему отобразится всплывающая подсказка.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>  
 <xref:System.Windows.Forms.ToolStripButton>  
 <xref:System.Windows.Forms.ToolStripDropDownButton>  
 <xref:System.Windows.Forms.ToolStripSplitButton>  
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
