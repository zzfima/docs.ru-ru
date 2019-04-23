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
ms.openlocfilehash: 99609e4bf5a352c436986e0773375d1c8e15e790
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340754"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a><span data-ttu-id="bb3e9-102">Практическое руководство. Создание средства просмотра HTML-документов в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb3e9-102">How to: Create an HTML Document Viewer in a Windows Forms Application</span></span>
<span data-ttu-id="bb3e9-103">Можно использовать <xref:System.Windows.Forms.WebBrowser> управления для отображения и печати HTML-документов с ограниченными возможностями обозревателя.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-103">You can use the <xref:System.Windows.Forms.WebBrowser> control to display and print HTML documents without providing the full functionality of an Internet Web browser.</span></span> <span data-ttu-id="bb3e9-104">Это полезно в том случае, если вы хотите воспользоваться преимуществами возможности форматирования HTML-кода, но запретить пользователям произвольным веб-страницам, которые могут содержать ненадежных веб-элементы управления или потенциально вредоносный код сценария.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-104">This is useful when you want to take advantage of the formatting capabilities of HTML but do not want your users to load arbitrary Web pages that may contain untrusted Web controls or potentially malicious script code.</span></span> <span data-ttu-id="bb3e9-105">Может потребоваться ограничить возможность <xref:System.Windows.Forms.WebBrowser> управления таким образом, например, для использования в качестве средстве просмотра HTML по электронной почте или для предоставления справки формате HTML в приложении.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-105">You might want to restrict the capability of the <xref:System.Windows.Forms.WebBrowser> control in this manner, for example, to use it as an HTML email viewer or to provide HTML-formatted help in your application.</span></span>  
  
### <a name="to-create-an-html-document-viewer"></a><span data-ttu-id="bb3e9-106">Чтобы создать средство просмотра документа HTML</span><span class="sxs-lookup"><span data-stu-id="bb3e9-106">To create an HTML document viewer</span></span>  
  
1. <span data-ttu-id="bb3e9-107">Задайте <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> свойства `false` во избежание <xref:System.Windows.Forms.WebBrowser> управления открывать файлы, которые перетаскиваются на него.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-107">Set the <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A> property to `false` to prevent the <xref:System.Windows.Forms.WebBrowser> control from opening files dropped onto it.</span></span>  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. <span data-ttu-id="bb3e9-108">Задайте <xref:System.Windows.Forms.WebBrowser.Url%2A> свойство в расположение исходного файла для отображения.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-108">Set the <xref:System.Windows.Forms.WebBrowser.Url%2A> property to the location of the initial file to display.</span></span>  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bb3e9-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="bb3e9-109">Compiling the Code</span></span>  
 <span data-ttu-id="bb3e9-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="bb3e9-110">This example requires:</span></span>  
  
-   <span data-ttu-id="bb3e9-111">элемент управления <xref:System.Windows.Forms.WebBrowser> с именем `webBrowser1`;</span><span class="sxs-lookup"><span data-stu-id="bb3e9-111">A <xref:System.Windows.Forms.WebBrowser> control named `webBrowser1`.</span></span>  
  
-   <span data-ttu-id="bb3e9-112">ссылки на сборки `System` и `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="bb3e9-112">References to the `System` and `System.Windows.Forms` assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb3e9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bb3e9-113">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [<span data-ttu-id="bb3e9-114">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="bb3e9-114">WebBrowser Control Overview</span></span>](webbrowser-control-overview.md)
- [<span data-ttu-id="bb3e9-115">Безопасность элемента управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="bb3e9-115">WebBrowser Security</span></span>](webbrowser-security.md)
- [<span data-ttu-id="bb3e9-116">Практическое руководство. Перейдите на URL-адрес с элементом управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="bb3e9-116">How to: Navigate to a URL with the WebBrowser Control</span></span>](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [<span data-ttu-id="bb3e9-117">Практическое руководство. Печать с элементом управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="bb3e9-117">How to: Print with a WebBrowser Control</span></span>](how-to-print-with-a-webbrowser-control.md)
