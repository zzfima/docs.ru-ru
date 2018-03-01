---
title: "Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a447d69eb6dafbff75ddd9d161abd4f78c607cdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-navigate-to-a-url-with-the-webbrowser-control"></a><span data-ttu-id="b9a80-102">Практическое руководство. Переход по заданному URL с помощью элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="b9a80-102">How to: Navigate to a URL with the WebBrowser Control</span></span>
<span data-ttu-id="b9a80-103">В следующем примере кода показано, как переходить <xref:System.Windows.Forms.WebBrowser> управления определенный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="b9a80-103">The following code example demonstrates how to navigate the <xref:System.Windows.Forms.WebBrowser> control to a specific URL.</span></span>  
  
 <span data-ttu-id="b9a80-104">Чтобы определить, когда новый документ полностью загружен, необходимо обработать событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> событий.</span><span class="sxs-lookup"><span data-stu-id="b9a80-104">To determine when the new document is fully loaded, handle the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="b9a80-105">Это событие см [как: печать с элементом управления WebBrowser](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span><span class="sxs-lookup"><span data-stu-id="b9a80-105">For a demonstration of this event, see [How to: Print with a WebBrowser Control](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9a80-106">Пример</span><span class="sxs-lookup"><span data-stu-id="b9a80-106">Example</span></span>  
  
```vb  
Me.webBrowser1.Navigate("http://www.microsoft.com")  
```  
  
```csharp  
this.webBrowser1.Navigate("http://www.microsoft.com");  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b9a80-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b9a80-107">Compiling the Code</span></span>  
 <span data-ttu-id="b9a80-108">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b9a80-108">This example requires:</span></span>  
  
-   <span data-ttu-id="b9a80-109">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="b9a80-109">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="b9a80-110">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="b9a80-110">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a80-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b9a80-111">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.DocumentCompleted?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigating?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.WebBrowser.Navigated?displayProperty=nameWithType>  
 [<span data-ttu-id="b9a80-112">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="b9a80-112">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
 [<span data-ttu-id="b9a80-113">Практическое руководство. Печать с использованием элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="b9a80-113">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
