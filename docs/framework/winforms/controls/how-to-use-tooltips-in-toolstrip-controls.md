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
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="d14bf-102">Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d14bf-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="d14bf-103">Можно отобразить <xref:System.Windows.Forms.ToolTip> <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> для нужного `true`элемента управления, присвоив свойству элемента управления значение. <xref:System.Windows.Forms.ToolStrip></span><span class="sxs-lookup"><span data-stu-id="d14bf-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="d14bf-104">Отображение подсказки</span><span class="sxs-lookup"><span data-stu-id="d14bf-104">To display a ToolTip</span></span>  
  
- <span data-ttu-id="d14bf-105">Присвойте `true`свойству элемента управления значение. <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A></span><span class="sxs-lookup"><span data-stu-id="d14bf-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="d14bf-106">Значение <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> по умолчанию равно `true` <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> , а значение <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="d14bf-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="d14bf-107">Использование свойства ToolTipText для текста подсказки в ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="d14bf-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1. <span data-ttu-id="d14bf-108">Присвойте `true`свойству кнопки значение. <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A></span><span class="sxs-lookup"><span data-stu-id="d14bf-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2. <span data-ttu-id="d14bf-109">Присвойте `false`свойству кнопки значение. <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d14bf-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="d14bf-110">`true` <xref:System.Windows.Forms.ToolStripDropDownButton>По умолчанию<xref:System.Windows.Forms.ToolStripButton>свойство имеет значение, и<xref:System.Windows.Forms.ToolStripSplitButton>. `AutoToolTip`</span><span class="sxs-lookup"><span data-stu-id="d14bf-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="d14bf-111">По умолчанию `Text`компонентиспользует его <xref:System.Windows.Forms.ToolTip> свойство для текста. <xref:System.Windows.Forms.ToolStripButton></span><span class="sxs-lookup"><span data-stu-id="d14bf-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="d14bf-112">Эта процедура используется для вывода пользовательского текста в <xref:System.Windows.Forms.ToolStripButton>. <xref:System.Windows.Forms.ToolTip></span><span class="sxs-lookup"><span data-stu-id="d14bf-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d14bf-113">Если задано <xref:System.Windows.Forms.ToolStripItemDisplayStyle> значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, текст на кнопке не отображается, но подсказка по-прежнему отображается.</span><span class="sxs-lookup"><span data-stu-id="d14bf-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14bf-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d14bf-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="d14bf-115">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="d14bf-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
