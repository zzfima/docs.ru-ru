---
title: "Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bc52dd1b629829564532fd93650737f51e5d7f24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
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
