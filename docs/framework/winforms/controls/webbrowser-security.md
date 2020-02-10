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
# <a name="webbrowser-security"></a>Безопасность элемента управления WebBrowser
Элемент управления <xref:System.Windows.Forms.WebBrowser> предназначен для работы только с полным доверием. Содержимое HTML, отображаемое в элементе управления, может поступать от внешних веб-серверов и может содержать неуправляемый код в виде скриптов или веб-элементов управления. Если в этой ситуации используется элемент управления <xref:System.Windows.Forms.WebBrowser>, элемент управления не менее безопасен, чем Internet Explorer, но управляемый <xref:System.Windows.Forms.WebBrowser> элемент управления не препятствует запуску такого неуправляемого кода.  
  
 Дополнительные сведения о проблемах безопасности, связанных с базовым элементом управления ActiveX `WebBrowser`, см. в разделе [элемент управления WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.WebBrowser>
- [Общие сведения об элементе управления WebBrowser](webbrowser-control-overview.md)
- [Элемент управления WebBrowser](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))
