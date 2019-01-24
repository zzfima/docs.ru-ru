---
title: Общие сведения об элементе управления ToolStripProgressBar
ms.date: 03/30/2017
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
ms.openlocfilehash: 57a8c61c71fa17e1d3df309007823eab76d9efb1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528632"
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="27282-102">Общие сведения об элементе управления ToolStripProgressBar</span><span class="sxs-lookup"><span data-stu-id="27282-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="27282-103"><xref:System.Windows.Forms.ToolStripProgressBar> Сочетает в себе нависание и подготовки к просмотру функциональные возможности всех <xref:System.Windows.Forms.ToolStrip> элементов управления с его обычные функциональные возможности отслеживания процесса.</span><span class="sxs-lookup"><span data-stu-id="27282-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="27282-104">Объект <xref:System.Windows.Forms.ToolStripProgressBar> наиболее обычно размещается <xref:System.Windows.Forms.StatusStrip>и менее часто с <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="27282-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="27282-105">Несмотря на то что <xref:System.Windows.Forms.ToolStripProgressBar> заменяет и расширяет функциональные возможности управления в предыдущих версиях <xref:System.Windows.Forms.ToolStripProgressBar> сохраняется для обратной совместимости и использования в будущем при необходимости.</span><span class="sxs-lookup"><span data-stu-id="27282-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="27282-106">ToolStripProgressBar важные члены</span><span class="sxs-lookup"><span data-stu-id="27282-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="27282-107">name</span><span class="sxs-lookup"><span data-stu-id="27282-107">Name</span></span>|<span data-ttu-id="27282-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="27282-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="27282-109">Возвращает или задает значение, представляющее задержку между каждым <xref:System.Windows.Forms.ProgressBarStyle.Marquee> обновлениями отображения в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="27282-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="27282-110">Возвращает или задает верхнюю границу диапазона, устанавливаемого для данного <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="27282-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="27282-111">Возвращает или задает нижнюю границу диапазона, устанавливаемого для данного <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="27282-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="27282-112">Возвращает или задает стиль, <xref:System.Windows.Forms.ToolStripProgressBar> используется для отображения хода выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="27282-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="27282-113">Возвращает или задает текущее значение <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="27282-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="27282-114">Перемещает текущую позицию индикатора хода выполнения на сумму <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="27282-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="27282-115">См. также</span><span class="sxs-lookup"><span data-stu-id="27282-115">See also</span></span>
- <xref:System.Windows.Forms.ToolStripProgressBar>
