---
title: Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 3f383b6cccba7825637ea65a0e13280b91b406c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939729"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a>Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip
Можно отобразить <xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> для нужного `true`элемента управления, присвоив свойству элемента управления значение. <xref:System.Windows.Forms.ToolStrip>  
  
### <a name="to-display-a-tooltip"></a>Отображение подсказки  
  
- Присвойте `true`свойству элемента управления значение. <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>  
  
     Значение <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> по умолчанию равно `true` <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> , а значение <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> по умолчанию — `false`.  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a>Использование свойства ToolTipText для текста подсказки в ToolStripButton  
  
1. Присвойте `true`свойству кнопки значение. <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>  
  
2. Присвойте `false`свойству кнопки значение. <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType>  
  
     `true` <xref:System.Windows.Forms.ToolStripDropDownButton>По умолчанию<xref:System.Windows.Forms.ToolStripButton>свойство имеет значение, и<xref:System.Windows.Forms.ToolStripSplitButton>. `AutoToolTip`  
  
     По умолчанию `Text`компонентиспользует его <xref:System.Windows.Forms.ToolTip> свойство для текста. <xref:System.Windows.Forms.ToolStripButton> Эта процедура используется для вывода пользовательского текста в <xref:System.Windows.Forms.ToolStripButton>. <xref:System.Windows.Forms.ToolTip>  
  
> [!NOTE]
> Если задано <xref:System.Windows.Forms.ToolStripItemDisplayStyle> значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, текст на кнопке не отображается, но подсказка по-прежнему отображается.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
