---
title: Безопасность элемента управления WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 957c11a085c971a81e5baa81a5b797dd53f2451a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703437"
---
# <a name="webbrowser-security"></a><span data-ttu-id="43b70-102">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="43b70-102">WebBrowser Security</span></span>
<span data-ttu-id="43b70-103"><xref:System.Windows.Forms.WebBrowser> Управления предназначен для работы в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="43b70-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="43b70-104">Содержимое HTML, отображаемый в элементе управления могут поступать из внешних веб-серверов и может содержать неуправляемый код в виде скриптов или веб-элементов управления.</span><span class="sxs-lookup"><span data-stu-id="43b70-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="43b70-105">Если вы используете <xref:System.Windows.Forms.WebBrowser> элемента управления в этом случае элемент управления не менее безопасен, чем бы Internet Explorer, но управляемый <xref:System.Windows.Forms.WebBrowser> управления не такого неуправляемого кода применялось.</span><span class="sxs-lookup"><span data-stu-id="43b70-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="43b70-106">Дополнительные сведения о проблемах безопасности, относящиеся к базового ActiveX `WebBrowser` управления, см. в разделе [элемент управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="43b70-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b70-107">См. также</span><span class="sxs-lookup"><span data-stu-id="43b70-107">See also</span></span>
- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="43b70-108">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="43b70-108">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="43b70-109">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="43b70-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
