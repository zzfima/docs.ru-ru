---
title: Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStrip control [Windows Forms], adding tooltips
- toolbars [Windows Forms], adding tooltips
- tooltips [Windows Forms], adding
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
ms.openlocfilehash: 7177daef469f6c601cfa468c6437deb9653ffc85
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707473"
---
# <a name="how-to-use-tooltips-in-toolstrip-controls"></a><span data-ttu-id="1c398-102">Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1c398-102">How to: Use ToolTips in ToolStrip Controls</span></span>
<span data-ttu-id="1c398-103">Можно отобразить <xref:System.Windows.Forms.ToolTip> для <xref:System.Windows.Forms.ToolStrip> элемента управления, присвоив элемента управления <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="1c398-103">You can display a <xref:System.Windows.Forms.ToolTip> for the <xref:System.Windows.Forms.ToolStrip> control you want by setting the control's <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property to `true`.</span></span>  
  
### <a name="to-display-a-tooltip"></a><span data-ttu-id="1c398-104">Для отображения всплывающей подсказки</span><span class="sxs-lookup"><span data-stu-id="1c398-104">To display a ToolTip</span></span>  
  
-   <span data-ttu-id="1c398-105">Задайте <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> свойство элемента управления, `true`.</span><span class="sxs-lookup"><span data-stu-id="1c398-105">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the control to `true`.</span></span>  
  
     <span data-ttu-id="1c398-106">Значение по умолчанию <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> — `true`и значение по умолчанию <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> является `false`.</span><span class="sxs-lookup"><span data-stu-id="1c398-106">The default value of <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `true`, and the default value of <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=nameWithType> and <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=nameWithType> is `false`.</span></span>  
  
### <a name="to-use-the-tooltiptext-property-for-the-tooltip-text-of-a-toolstripbutton"></a><span data-ttu-id="1c398-107">Чтобы использовать свойство ToolTipText для текста подсказки ToolStripButton</span><span class="sxs-lookup"><span data-stu-id="1c398-107">To use the ToolTipText property for the ToolTip text of a ToolStripButton</span></span>  
  
1.  <span data-ttu-id="1c398-108">Задайте <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> свойство кнопки `true`.</span><span class="sxs-lookup"><span data-stu-id="1c398-108">Set the <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> property of the button to `true`.</span></span>  
  
2.  <span data-ttu-id="1c398-109">Задайте <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> свойство кнопки `false`.</span><span class="sxs-lookup"><span data-stu-id="1c398-109">Set the <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=nameWithType> property of the button to `false`.</span></span>  
  
     <span data-ttu-id="1c398-110">`AutoToolTip` Свойство `true` по умолчанию для <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, и <xref:System.Windows.Forms.ToolStripSplitButton>.</span><span class="sxs-lookup"><span data-stu-id="1c398-110">The `AutoToolTip` property is `true` by default for <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton>, and <xref:System.Windows.Forms.ToolStripSplitButton>.</span></span>  
  
     <span data-ttu-id="1c398-111">Объект <xref:System.Windows.Forms.ToolStripButton> использует его `Text` свойство для <xref:System.Windows.Forms.ToolTip> текст по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1c398-111">A <xref:System.Windows.Forms.ToolStripButton> uses its `Text` property for the <xref:System.Windows.Forms.ToolTip> text by default.</span></span> <span data-ttu-id="1c398-112">Эта процедура используется для отображения пользовательского текста в <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="1c398-112">Use this procedure to display custom text in a <xref:System.Windows.Forms.ToolStripButton><xref:System.Windows.Forms.ToolTip>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1c398-113">Если задать <xref:System.Windows.Forms.ToolStripItemDisplayStyle> для <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, текст не будет отображаться на кнопке, но по-прежнему отображается всплывающая подсказка.</span><span class="sxs-lookup"><span data-stu-id="1c398-113">If you set <xref:System.Windows.Forms.ToolStripItemDisplayStyle> to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.None> or <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Image>, no text will appear on the button, but the tool tip still appears.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c398-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1c398-114">See also</span></span>
- <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>
- <xref:System.Windows.Forms.ToolStripButton>
- <xref:System.Windows.Forms.ToolStripDropDownButton>
- <xref:System.Windows.Forms.ToolStripSplitButton>
- [<span data-ttu-id="1c398-115">Общие сведения об элементе управления ToolStrip</span><span class="sxs-lookup"><span data-stu-id="1c398-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
