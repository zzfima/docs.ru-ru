---
title: Создание средства просмотра HTML-документов в приложении Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 913bc86af034645b4b8cf3d69da4c9def58fc19c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732848"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="9dddb-102">Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9dddb-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="9dddb-103">Можно использовать элемент управления <xref:System.Windows.Forms.WebBrowser> для отображения и печати HTML-документов, не предоставляя полный набор функций браузера Интернета.</span><span class="sxs-lookup"><span data-stu-id="9dddb-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="9dddb-104">Это полезно, если вы хотите использовать возможности форматирования HTML, но не хотите, чтобы пользователи загружали произвольные веб-страницы, которые могут содержать ненадежные веб-элементы управления или потенциально вредоносный код скрипта.</span><span class="sxs-lookup"><span data-stu-id="9dddb-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="9dddb-105">Может потребоваться ограничить возможности элемента управления <xref:System.Windows.Forms.WebBrowser> таким образом, например, чтобы использовать его в качестве средства просмотра электронной почты HTML или для предоставления в приложении справки в формате HTML.</span><span class="sxs-lookup"><span data-stu-id="9dddb-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="9dddb-106">Создание средства просмотра HTML-документов</span><span class="sxs-lookup"><span data-stu-id="9dddb-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="9dddb-107">Задайте для свойства <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> значение `false`, чтобы элемент управления <xref:System.Windows.Forms.WebBrowser> не открывал файлы.</span><span class="sxs-lookup"><span data-stu-id="9dddb-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="9dddb-108">Задайте для свойства <xref:System.Windows.Forms.WebBrowser.Url%2A> расположение исходного файла для вывода.</span><span class="sxs-lookup"><span data-stu-id="9dddb-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9dddb-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9dddb-109">Compiling the Code</span></span>  
 <span data-ttu-id="9dddb-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="9dddb-110">This example requires:</span></span>  
  
- <span data-ttu-id="9dddb-111">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="9dddb-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
- <span data-ttu-id="9dddb-112">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="9dddb-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dddb-113">См. также:</span><span class="sxs-lookup"><span data-stu-id="9dddb-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="9dddb-114">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9dddb-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="9dddb-115">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9dddb-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="9dddb-116">Практическое руководство. Переход по заданному URL-адресу с помощью элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9dddb-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="9dddb-117">Практическое руководство. Печать с использованием элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="9dddb-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
