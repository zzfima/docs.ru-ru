---
title: Безопасность элемента управления WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: b25cabca050d06dbfe97c563eb56622d1f21be54
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095259"
---
# <a name="webbrowser-security"></a><span data-ttu-id="e875f-102">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="e875f-102">WebBrowser Security</span></span>
<span data-ttu-id="e875f-103">Элемент управления <xref:System.Windows.Forms.WebBrowser> предназначен для работы только с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="e875f-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="e875f-104">Содержимое HTML, отображаемое в элементе управления, может поступать от внешних веб-серверов и может содержать неуправляемый код в виде скриптов или веб-элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e875f-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="e875f-105">Если в этой ситуации используется элемент управления <xref:System.Windows.Forms.WebBrowser>, элемент управления не менее безопасен, чем Internet Explorer, но управляемый <xref:System.Windows.Forms.WebBrowser> элемент управления не препятствует запуску такого неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e875f-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="e875f-106">Дополнительные сведения о проблемах безопасности, связанных с базовым элементом управления ActiveX `WebBrowser`, см. в разделе [элемент управления WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="e875f-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e875f-107">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e875f-107">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="e875f-108">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="e875f-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- <span data-ttu-id="e875f-109">[Элемент управления WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="e875f-109">[WebBrowser Control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))</span></span>
