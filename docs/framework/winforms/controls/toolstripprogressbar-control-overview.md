---
title: "Общие сведения об элементе управления ToolStripProgressBar"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3ee73d87a65e9febed6ebd5ad981dcd548fc2404
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="bbb2b-102">Общие сведения об элементе управления ToolStripProgressBar</span><span class="sxs-lookup"><span data-stu-id="bbb2b-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="bbb2b-103"><xref:System.Windows.Forms.ToolStripProgressBar> Объединяет нависание и функциональные возможности визуализации всех <xref:System.Windows.Forms.ToolStrip> элементов управления с его обычные функциональные возможности отслеживания выполнения процесса.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="bbb2b-104">Объект <xref:System.Windows.Forms.ToolStripProgressBar> наиболее обычно размещается <xref:System.Windows.Forms.StatusStrip>и менее часто, <xref:System.Windows.Forms.ToolStrip>.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="bbb2b-105">Несмотря на то что <xref:System.Windows.Forms.ToolStripProgressBar> заменяет и расширяет его функциональные возможности для управления в предыдущих версиях <xref:System.Windows.Forms.ToolStripProgressBar> при необходимости можно сохранить для обратной совместимости и использования в будущем.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="bbb2b-106">ToolStripProgressBar важные члены</span><span class="sxs-lookup"><span data-stu-id="bbb2b-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="bbb2b-107">name</span><span class="sxs-lookup"><span data-stu-id="bbb2b-107">Name</span></span>|<span data-ttu-id="bbb2b-108">Описание:</span><span class="sxs-lookup"><span data-stu-id="bbb2b-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="bbb2b-109">Возвращает или задает значение, представляющее задержку между каждым <xref:System.Windows.Forms.ProgressBarStyle.Marquee> отображения обновления, в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="bbb2b-110">Возвращает или задает верхнюю границу диапазона, определенные для данного <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="bbb2b-111">Возвращает или задает нижнюю границу диапазона, определенные для данного <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="bbb2b-112">Возвращает или задает стиль, <xref:System.Windows.Forms.ToolStripProgressBar> используется для отображения хода выполнения операции.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="bbb2b-113">Возвращает или задает текущее значение <xref:System.Windows.Forms.ToolStripProgressBar>.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="bbb2b-114">Перемещает текущую позицию индикатора хода выполнения в зависимости от объема <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="bbb2b-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bbb2b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bbb2b-115">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripProgressBar>
