---
title: Общие сведения об элементе управления StatusBar
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: b0b97bc3cb0291871e1fd113d82d0b480b53cdba
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742864"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="5e98d-102">Общие сведения об элементе управления StatusBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="5e98d-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="5e98d-103"><xref:System.Windows.Forms.StatusStrip> и <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и добавляют функции в элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel>. Однако элементы управления <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> сохраняются как для обратной совместимости, так и для будущего использования, если вы решили.</span><span class="sxs-lookup"><span data-stu-id="5e98d-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="5e98d-104">[Элемент управления StatusBar](statusbar-control-windows-forms.md) Windows Forms используется в формах как область, обычно отображаемую в нижней части окна, в которой приложение может отображать различные виды информации о состоянии.</span><span class="sxs-lookup"><span data-stu-id="5e98d-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="5e98d-105">элементы управления <xref:System.Windows.Forms.StatusBar> могут иметь панели строки состояния, которые отображают текст или значки, указывающие на состояние, или ряд значков в анимации, указывающих, что процесс работает. Например, Microsoft Word, указывающий, что документ сохраняется.</span><span class="sxs-lookup"><span data-stu-id="5e98d-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="5e98d-106">Использование элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="5e98d-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="5e98d-107">Internet Explorer использует строку состояния для указания URL-адреса страницы при наведении указателя мыши на гиперссылку; Microsoft Word предоставляет сведения о расположении страницы, расположении раздела и режимах редактирования, таких как изменение типа и отслеживание исправлений. и Visual Studio использует строку состояния для предоставления контекстно-зависимой информации, например, о том, как управлять закрепляемыми окнами как закрепленными, так и плавающими.</span><span class="sxs-lookup"><span data-stu-id="5e98d-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="5e98d-108">В строке состояния можно отобразить одно сообщение, задав для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значение `false` (по умолчанию) и установив для свойства <xref:System.Windows.Forms.StatusBar.Text%2A> строки состояния текст, который должен отображаться в строке состояния.</span><span class="sxs-lookup"><span data-stu-id="5e98d-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="5e98d-109">Можно разделить строку состояния на панели, чтобы отобразить более одного типа информации, задав для свойства <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> значение `true` и используя метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="5e98d-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e98d-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5e98d-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="5e98d-111">Практическое руководство. Идентификация панели элемента управления StatusBar, которую щелкнул пользователь, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5e98d-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
