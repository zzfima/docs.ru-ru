---
title: Безопасность элемента управления WebBrowser
ms.date: 03/30/2017
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
ms.openlocfilehash: 683c6ad4cbc55a889f4a0c1d20ebe8e8a2669a13
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46538944"
---
# <a name="webbrowser-security"></a><span data-ttu-id="47419-102">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="47419-102">WebBrowser Security</span></span>
<span data-ttu-id="47419-103"><xref:System.Windows.Forms.WebBrowser> Управления предназначен для работы в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="47419-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="47419-104">Содержимое HTML, отображаемый в элементе управления могут поступать из внешних веб-серверов и может содержать неуправляемый код в виде скриптов или веб-элементов управления.</span><span class="sxs-lookup"><span data-stu-id="47419-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="47419-105">Если вы используете <xref:System.Windows.Forms.WebBrowser> элемента управления в этом случае элемент управления не менее безопасен, чем бы Internet Explorer, но управляемый <xref:System.Windows.Forms.WebBrowser> управления не такого неуправляемого кода применялось.</span><span class="sxs-lookup"><span data-stu-id="47419-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="47419-106">Дополнительные сведения о проблемах безопасности, относящиеся к базового ActiveX `WebBrowser` управления, см. в разделе [элемент управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="47419-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](https://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47419-107">См. также</span><span class="sxs-lookup"><span data-stu-id="47419-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="47419-108">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="47419-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="47419-109">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="47419-109">WebBrowser Control</span></span>](https://go.microsoft.com/fwlink/?LinkId=198812)
