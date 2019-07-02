---
title: Общие сведения об элементе управления StatusBar (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- StatusBar
helpviewer_keywords:
- StatusBar control [Windows Forms], about StatusBar control
- status bars
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
ms.openlocfilehash: 4e1816ef221641f5ad54fb429442ed43289b592a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505424"
---
# <a name="statusbar-control-overview-windows-forms"></a><span data-ttu-id="839a9-102">Общие сведения об элементе управления StatusBar (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="839a9-102">StatusBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="839a9-103"><xref:System.Windows.Forms.StatusStrip> И <xref:System.Windows.Forms.ToolStripStatusLabel> элементы управления заменяют и расширяют функциональные возможности для <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> управляет; Однако <xref:System.Windows.Forms.StatusBar> и <xref:System.Windows.Forms.StatusBarPanel> элементы управления сохраняются для обеспечения обратной совместимости и использования в будущем, если вы Выберите этот параметр.</span><span class="sxs-lookup"><span data-stu-id="839a9-103">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="839a9-104">Windows Forms [элемента управления StatusBar](statusbar-control-windows-forms.md) используется в формах в качестве области, обычно отображается в нижней части окна, в которой выводятся различные сведения о состоянии приложения.</span><span class="sxs-lookup"><span data-stu-id="839a9-104">The Windows Forms [StatusBar Control](statusbar-control-windows-forms.md) is used on forms as an area, usually displayed at the bottom of a window, in which an application can display various kinds of status information.</span></span> <span data-ttu-id="839a9-105"><xref:System.Windows.Forms.StatusBar> элементы управления могут иметь панелей строки состояния на них, которые отображают текст или значки, показывающие состояние или набор значков в анимации, которые указывают, что процесс работает; например Microsoft Word, означает, что документ сохраняется.</span><span class="sxs-lookup"><span data-stu-id="839a9-105"><xref:System.Windows.Forms.StatusBar> controls can have status bar panels on them that display text or icons to indicate state, or a series of icons in an animation that indicate a process is working; for example, Microsoft Word indicating that the document is being saved.</span></span>  
  
## <a name="using-the-statusbar-control"></a><span data-ttu-id="839a9-106">Использование элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="839a9-106">Using the StatusBar Control</span></span>  
 <span data-ttu-id="839a9-107">Internet Explorer использует строку состояния, чтобы указать URL-адрес страницы при наведении указателя мыши на гиперссылку; Microsoft Word дает информацию о расположение страницы, раздела и изменение режимов, таких как замены и правки; и Visual Studio использует строку состояния для предоставления контекстных сведений, таких как закрепляемые окнами действий с закрепленными или с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="839a9-107">Internet Explorer uses a status bar to indicate the URL of a page when the mouse rolls over the hyperlink; Microsoft Word gives you information on page location, section location, and editing modes such as overtype and revision tracking; and Visual Studio uses the status bar to give context-sensitive information, such as telling you how to manipulate dockable windows as either docked or floating.</span></span>  
  
 <span data-ttu-id="839a9-108">Можно отобразить одно сообщение в строке состояния, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `false` (по умолчанию) и параметр <xref:System.Windows.Forms.StatusBar.Text%2A> свойства в строке состояния в текст, который будет отображаться в строке состояния.</span><span class="sxs-lookup"><span data-stu-id="839a9-108">You can display a single message on the status bar by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `false` (the default) and setting the <xref:System.Windows.Forms.StatusBar.Text%2A> property of the status bar to the text you want to appear in the status bar.</span></span> <span data-ttu-id="839a9-109">Можно разделить на строке состояния панелей для отображения более чем один тип данных, задав <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> свойства `true` и с помощью <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> метод <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span><span class="sxs-lookup"><span data-stu-id="839a9-109">You can divide the status bar into panels to display more than one type of information by setting the <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> property to `true` and using the <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> method of <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="839a9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="839a9-110">See also</span></span>

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [<span data-ttu-id="839a9-111">Практическое руководство. Определить, какая из панелей в элемент управления Windows Forms StatusBar была нажата</span><span class="sxs-lookup"><span data-stu-id="839a9-111">How to: Determine Which Panel in the Windows Forms StatusBar Control Was Clicked</span></span>](determine-which-panel-wf-statusbar-control-was-clicked.md)
