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
# <a name="webbrowser-security"></a>Безопасность элемента управления WebBrowser
<xref:System.Windows.Forms.WebBrowser> Управления предназначен для работы в режиме полного доверия. Содержимое HTML, отображаемый в элементе управления могут поступать из внешних веб-серверов и может содержать неуправляемый код в виде скриптов или веб-элементов управления. Если вы используете <xref:System.Windows.Forms.WebBrowser> элемента управления в этом случае элемент управления не менее безопасен, чем бы Internet Explorer, но управляемый <xref:System.Windows.Forms.WebBrowser> управления не такого неуправляемого кода применялось.  
  
 Дополнительные сведения о проблемах безопасности, относящиеся к базового ActiveX `WebBrowser` управления, см. в разделе [элемент управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=198812).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.WebBrowser>
- [Общие сведения об элементе управления WebBrowser](webbrowser-control-overview.md)
- [Элемент управления WebBrowser](https://go.microsoft.com/fwlink/?LinkId=198812)
