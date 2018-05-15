---
title: Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 1330e20cc4fe7df86e51bebca28e4a71e3108673
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="f920d-102">Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f920d-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="f920d-103">Можно использовать <xref:System.Windows.Forms.WebBrowser> управления для отображения и печати HTML-документов с ограниченными возможностями обозревателя.</span><span class="sxs-lookup"><span data-stu-id="f920d-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="f920d-104">Это полезно в том случае, если необходимо воспользоваться возможностями форматирования HTML, но запретить пользователям произвольным веб-страницам, которые могут содержать ненадежных веб-элементы управления или потенциально вредоносный код скрипта.</span><span class="sxs-lookup"><span data-stu-id="f920d-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="f920d-105">Может потребоваться ограничить возможности <xref:System.Windows.Forms.WebBrowser> управления таким образом, например, для использования в качестве средства просмотра электронной почты HTML или предоставить справку формате HTML в приложении.</span><span class="sxs-lookup"><span data-stu-id="f920d-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="f920d-106">Создание средства просмотра документа HTML</span><span class="sxs-lookup"><span data-stu-id="f920d-106">To create an HTML document viewer</span></span>  
  
1.  <span data-ttu-id="f920d-107">Задать <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> свойства `false` для предотвращения <xref:System.Windows.Forms.WebBrowser> управления открывать файлы, которые перетаскиваются на него.</span><span class="sxs-lookup"><span data-stu-id="f920d-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2.  <span data-ttu-id="f920d-108">Задать <xref:System.Windows.Forms.WebBrowser.Url%2A> свойства нужный исходный файл для отображения.</span><span class="sxs-lookup"><span data-stu-id="f920d-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f920d-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f920d-109">Compiling the Code</span></span>  
 <span data-ttu-id="f920d-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="f920d-110">This example requires:</span></span>  
  
-   <span data-ttu-id="f920d-111">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="f920d-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="f920d-112">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="f920d-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f920d-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f920d-113">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>  
 <xref:System.Windows.Forms.WebBrowser.Url%2A>  
 [<span data-ttu-id="f920d-114">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f920d-114">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)  
 [<span data-ttu-id="f920d-115">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f920d-115">WebBrowser Security</span></span>](../../../../docs/framework/winforms/controls/webbrowser-security.md)  
 [<span data-ttu-id="f920d-116">Практическое руководство. Переход по заданному URL-адресу с помощью элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f920d-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-navigate-to-a-url-with-the-webbrowser-control.md)  
 [<span data-ttu-id="f920d-117">Практическое руководство. Печать с использованием элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="f920d-117">How to: Print with a WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/how-to-print-with-a-webbrowser-control.md)
