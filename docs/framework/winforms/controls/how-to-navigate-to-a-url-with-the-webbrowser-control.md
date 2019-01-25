---
title: Как выполнить Перейдите на URL-адрес с элементом управления WebBrowser
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
ms.openlocfilehash: 599ae9fbaed3240efa05dc04f5b6dc4180e55cfb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524225"
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="d0867-102">Как выполнить Перейдите на URL-адрес с элементом управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d0867-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="d0867-103">В следующем примере кода показано, как перемещаться <xref:System.Windows.Forms.WebBrowser> управления определенный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="d0867-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="d0867-104">Чтобы определить, когда новый документ загружен полностью, обрабатывать <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событий.</span><span class="sxs-lookup"><span data-stu-id="d0867-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="d0867-105">Для демонстрации этого события, см. в разделе [как: Печать с элементом управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="d0867-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0867-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d0867-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0867-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="d0867-107">Compiling the Code</span></span>  
 <span data-ttu-id="d0867-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="d0867-108">This example requires:</span></span>  
  
-   <span data-ttu-id="d0867-109">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="d0867-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="d0867-110">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="d0867-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0867-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d0867-111">See also</span></span>
- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>
- <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>
- [<span data-ttu-id="d0867-112">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d0867-112">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)
- [<span data-ttu-id="d0867-113">Практическое руководство. Печать с элементом управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="d0867-113">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
