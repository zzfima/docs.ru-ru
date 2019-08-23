---
title: Общие сведения об элементе управления StatusBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: bd58d4c70e3a3c88e57fe242957f669d1944fd71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964437"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="c8e3b-102">Общие сведения об элементе управления StatusBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c8e3b-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="c8e3b-103"><xref:System.Windows.Forms.StatusBarPanel> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBarPanel> Элементы управления <xref:System.Windows.Forms.ToolStripStatusLabel> и заменяют и добавляют функциональные возможности в элементы управления и, однако, элементы управления и сохраняются для обратной совместимости и использования в будущем, если <xref:System.Windows.Forms.StatusStrip> выбрали.</span><span class="sxs-lookup"><span data-stu-id="c8e3b-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="c8e3b-104">[Элемент управления StatusBar](statusbar-control-windows-forms.md) Windows Forms используется в формах как область, обычно отображаемую в нижней части окна, в которой приложение может отображать различные виды информации о состоянии.</span><span class="sxs-lookup"><span data-stu-id="c8e3b-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="c8e3b-105"><xref:System.Windows.Forms.StatusBar>элементы управления могут иметь панели строки состояния, которые отображают текст или значки, указывающие на состояние, или ряд значков в анимации, указывающих, что процесс работает. Например, Microsoft Word, указывающий, что документ сохраняется.</span><span class="sxs-lookup"><span data-stu-id="c8e3b-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="c8e3b-106">Использование элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="c8e3b-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="c8e3b-107">Internet Explorer использует строку состояния для указания URL-адреса страницы при наведении указателя мыши на гиперссылку; Microsoft Word предоставляет сведения о расположении страницы, расположении раздела и режимах редактирования, таких как изменение типа и отслеживание исправлений. и Visual Studio использует строку состояния для предоставления контекстно-зависимой информации, например, о том, как управлять закрепляемыми окнами как закрепленными, так и плавающими.</span><span class="sxs-lookup"><span data-stu-id="c8e3b-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="c8e3b-108">В строке состояния можно отобразить одно сообщение, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> для `false` свойства значение ( <xref:System.Windows.Forms.StatusBar.Text%2A> по умолчанию) и установив для свойства строки состояния текст, который должен отображаться в строке состояния.</span><span class="sxs-lookup"><span data-stu-id="c8e3b-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="c8e3b-109">Можно разделить строку состояния на панели, чтобы отобразить более одного типа информации, <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> задав для `true` свойства значение <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="c8e3b-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8e3b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c8e3b-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="c8e3b-111">Практическое руководство. Определите, какая панель элемента управления Windows Forms StatusBar была нажата</span><span class="sxs-lookup"><span data-stu-id="c8e3b-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
