---
title: "Общие сведения об элементе управления StatusBar (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df8e6b8484cf3b35c684445445ddc41adc358698
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="af563-102">Общие сведения об элементе управления StatusBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="af563-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="af563-103"><xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> заменить элементы управления и добавить функциональные возможности в <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления можно сохранить для обратной совместимости и использования в будущем, если вы Выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="af563-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="af563-104">Windows Forms [управления StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) используется в формах в качестве области, обычно отображаемой в нижней части окна, в которой выводятся различные сведения о состоянии приложения.</span><span class="sxs-lookup"><span data-stu-id="af563-104">The Windows Forms [StatusBar Control](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="af563-105"><xref:System.Windows.Forms.StatusBar>элементы управления могут включать панели строки состояния на них, отображающие текст или значки, показывающие состояние, или набор значков в анимации, указывающие, что процесс работает; например [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] означает, что при сохранении документа.</span><span class="sxs-lookup"><span data-stu-id="af563-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="af563-106">С помощью элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="af563-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="af563-107">Строка состояния Internet Explorer используется для указания URL-адрес страницы, при наведении указателя мыши на гиперссылку; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] представлены сведения о расположении страницы, расположение раздела и изменение режимы, такие как замены и правки; и [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] строка состояния используется для предоставления контекстных сведений, например о том, как управлять фиксируемого Windows как закрепленного или с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="af563-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] gives you information on page location, section location, and editing modes such as overtype and revision tracking; and [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="af563-108">Можно отобразить одно сообщение в строке состояния, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `false` (по умолчанию) и параметр <xref:System.Windows.Forms.StatusBar.Text%2A> свойство строки состояния, применяемый к тексту, который будет отображаться в строке состояния.</span><span class="sxs-lookup"><span data-stu-id="af563-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="af563-109">В строке состояния можно разделить на панелей для отображения более чем один тип данных, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true` и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="af563-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af563-110">См. также</span><span class="sxs-lookup"><span data-stu-id="af563-110">See Also</span></span>  
 <xref:System.Windows.Forms.StatusBar>  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 [<span data-ttu-id="af563-111">Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="af563-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)
