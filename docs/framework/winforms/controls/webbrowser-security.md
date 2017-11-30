---
title: "Безопасность элемента управления WebBrowser"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WebBrowser control [Windows Forms], security
- security [Windows Forms], WebBrowser control
ms.assetid: 0968846e-48ee-485a-9797-65b5b9a622f8
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a0d84f0c70619324bbbd38a2961914f88ac42671
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="webbrowser-security"></a><span data-ttu-id="d3acd-102">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d3acd-102">WebBrowser Security</span></span>
<span data-ttu-id="d3acd-103"><xref:System.Windows.Forms.WebBrowser> Управления предназначен для работы в режиме полного доверия.</span><span class="sxs-lookup"><span data-stu-id="d3acd-103">The <xref:System.Windows.Forms.WebBrowser> control is designed to work in full trust only.</span></span> <span data-ttu-id="d3acd-104">HTML-содержимое, отображаемое на элементе управления могут поступать из внешних веб-серверов и может содержать неуправляемый код в форме скриптов или веб-элементов управления.</span><span class="sxs-lookup"><span data-stu-id="d3acd-104">The HTML content displayed in the control can come from external Web servers and may contain unmanaged code in the form of scripts or Web controls.</span></span> <span data-ttu-id="d3acd-105">Если вы используете <xref:System.Windows.Forms.WebBrowser> управления в этом случае элемент управления не менее безопасен, чем бы Internet Explorer, но управляемый <xref:System.Windows.Forms.WebBrowser> управления не препятствует такого неуправляемого кода выполняется.</span><span class="sxs-lookup"><span data-stu-id="d3acd-105">If you use the <xref:System.Windows.Forms.WebBrowser> control in this situation, the control is no less secure than Internet Explorer would be, but the managed <xref:System.Windows.Forms.WebBrowser> control does not prevent such unmanaged code from running.</span></span>  
  
 <span data-ttu-id="d3acd-106">Дополнительные сведения о проблемах безопасности, связанные с базовой ActiveX `WebBrowser` управления см. в разделе [элемент управления WebBrowser](http://go.microsoft.com/fwlink/?LinkId=198812).</span><span class="sxs-lookup"><span data-stu-id="d3acd-106">For more information about security issues relating to the underlying ActiveX `WebBrowser` control, see [WebBrowser Control](http://go.microsoft.com/fwlink/?LinkId=198812).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3acd-107">См. также</span><span class="sxs-lookup"><span data-stu-id="d3acd-107">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="d3acd-108">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d3acd-108">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="d3acd-109">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d3acd-109">WebBrowser Control</span></span>](http://go.microsoft.com/fwlink/?LinkId=198812)
