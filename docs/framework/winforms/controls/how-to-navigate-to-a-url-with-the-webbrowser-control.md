---
title: Практическое руководство. Перейдите на URL-адрес с элементом управления WebBrowser
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- WebBrowser.Navigate
helpviewer_keywords:
- WebBrowser control [Windows Forms], examples
- URLs [Windows Forms], navigating to
- WebBrowser control [Windows Forms], navigating to URLs
- examples [Windows Forms], WebBrowser control
ms.assetid: b3ec38cb-f509-4d0b-bd79-9f3611259c62
ms.openlocfilehash: 8d592aea972a95a582cc35ecb14227edec5860ce
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707239"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a>Практическое руководство. Перейдите на URL-адрес с элементом управления WebBrowser
В следующем примере кода показано, как перемещаться <xref:System.Windows.Forms.WebBrowser> управления определенный URL-адрес.  
  
 Чтобы определить, когда новый документ загружен полностью, обрабатывать <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событий. Для демонстрации этого события, см. в разделе [как: Печать с элементом управления WebBrowser](how-to-print-with-a-webbrowser-control.md).  
  
## <a name="example"></a>Пример  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;  
  
-   ссылки на сборки `System` и `System.Windows.Forms`.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [Элемент управления WebBrowser](webbrowser-control-windows-forms.md)
- [Практическое руководство. Печать с элементом управления WebBrowser](how-to-print-with-a-webbrowser-control.md)
