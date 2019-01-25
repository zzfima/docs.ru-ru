---
title: Как выполнить Доступ к исходному коду HTML с объектной модели управляемого HTML-документ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- managed HTML DOM
- HTML [Windows Forms], accessing in Windows Forms
ms.assetid: 53db79fa-8a5e-448e-88c2-f54ace3860b6
ms.openlocfilehash: 310af03adf38339dd13a5095546391d4bfecac05
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674954"
---
# <a name="how-to-access-the-html-source-in-the-managed-html-document-object-model"></a><span data-ttu-id="41152-102">Как выполнить Доступ к исходному коду HTML с объектной модели управляемого HTML-документ</span><span class="sxs-lookup"><span data-stu-id="41152-102">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>
<span data-ttu-id="41152-103">Свойства <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> и <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> в элементе управления <xref:System.Windows.Forms.WebBrowser> возвращают HTML текущего документа в том виде, в котором он существовал при первом отображении.</span><span class="sxs-lookup"><span data-stu-id="41152-103">The <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> properties on the <xref:System.Windows.Forms.WebBrowser> control return the HTML of the current document as it existed when it was first displayed.</span></span> <span data-ttu-id="41152-104">Если вы измените страницу, используя вызовы таких методов и свойств, как <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> и <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, то при вызове <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> и <xref:System.Windows.Forms.WebBrowser.DocumentText%2A> эти изменения отображаться на будут.</span><span class="sxs-lookup"><span data-stu-id="41152-104">However, if you modify the page using method and property calls such as <xref:System.Windows.Forms.HtmlElement.AppendChild%2A> and <xref:System.Windows.Forms.HtmlElement.InnerHtml%2A>, these changes will not appear when you call <xref:System.Windows.Forms.WebBrowser.DocumentStream%2A> and <xref:System.Windows.Forms.WebBrowser.DocumentText%2A>.</span></span> <span data-ttu-id="41152-105">Чтобы получить актуальный HTML-источник DOM, необходимо вызвать свойство <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> по элементу HTML.</span><span class="sxs-lookup"><span data-stu-id="41152-105">To obtain the most up-to-date HTML source for the DOM, you must call the <xref:System.Windows.Forms.HtmlElement.OuterHtml%2A> property on the HTML element.</span></span>  
  
 <span data-ttu-id="41152-106">В следующей процедуре показано, как получить динамический источник и отобразить его в отдельном контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="41152-106">The following procedure shows how to retrieve the dynamic source and display it in a separate shortcut menu.</span></span>  
  
### <a name="retrieving-the-dynamic-source-with-the-outerhtml-property"></a><span data-ttu-id="41152-107">Получение динамического источника с помощью свойства OuterHtml.</span><span class="sxs-lookup"><span data-stu-id="41152-107">Retrieving the dynamic source with the OuterHtml property</span></span>  
  
1.  <span data-ttu-id="41152-108">Создайте новое приложение Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="41152-108">Create a new Windows Forms application.</span></span> <span data-ttu-id="41152-109">Создайте одну <xref:System.Windows.Forms.Form>и назовите его `Form1`.</span><span class="sxs-lookup"><span data-stu-id="41152-109">Start with a single <xref:System.Windows.Forms.Form>, and call it `Form1`.</span></span>  
  
2.  <span data-ttu-id="41152-110">Узел <xref:System.Windows.Forms.WebBrowser> управлять в приложении Windows Forms и назовите его `WebBrowser1`.</span><span class="sxs-lookup"><span data-stu-id="41152-110">Host the <xref:System.Windows.Forms.WebBrowser> control in your Windows Forms application, and name it `WebBrowser1`.</span></span> <span data-ttu-id="41152-111">Дополнительные сведения см. в разделе [Как Добавление функциональности веб-браузера в приложения Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span><span class="sxs-lookup"><span data-stu-id="41152-111">For more information, see [How to: Add Web Browser Capabilities to a Windows Forms Application](../../../../docs/framework/winforms/controls/how-to-add-web-browser-capabilities-to-a-windows-forms-application.md).</span></span>  
  
3.  <span data-ttu-id="41152-112">Создайте вторую <xref:System.Windows.Forms.Form> с именем `CodeForm`.</span><span class="sxs-lookup"><span data-stu-id="41152-112">Create a second <xref:System.Windows.Forms.Form> in your application called `CodeForm`.</span></span>  
  
4.  <span data-ttu-id="41152-113">Добавить <xref:System.Windows.Forms.RichTextBox> управления `CodeForm` и задайте его <xref:System.Windows.Forms.Control.Dock%2A> свойства `Fill`.</span><span class="sxs-lookup"><span data-stu-id="41152-113">Add a <xref:System.Windows.Forms.RichTextBox> control to `CodeForm` and set its <xref:System.Windows.Forms.Control.Dock%2A> property to `Fill`.</span></span>  
  
5.  <span data-ttu-id="41152-114">Создайте общедоступное свойство на `CodeForm` вызывается `Code`.</span><span class="sxs-lookup"><span data-stu-id="41152-114">Create a public property on `CodeForm` called `Code`.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/CodeForm.cs#1)]
     [!code-vb[DisplayWebBrowserCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/CodeForm.vb#1)]  
  
6.  <span data-ttu-id="41152-115">Добавить <xref:System.Windows.Forms.Button> управления с именем `Button1` для вашей <xref:System.Windows.Forms.Form>и отслеживать состояние <xref:System.Windows.Forms.Control.Click> событий.</span><span class="sxs-lookup"><span data-stu-id="41152-115">Add a <xref:System.Windows.Forms.Button> control named `Button1` to your <xref:System.Windows.Forms.Form>, and monitor for the <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="41152-116">Дополнительные сведения о мониторинге событий см. в разделе [события](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="41152-116">For details on monitoring events, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
7.  <span data-ttu-id="41152-117">Добавьте следующий код в обработчик событий <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="41152-117">Add the following code to the <xref:System.Windows.Forms.Control.Click> event handler.</span></span>  
  
     [!code-csharp[DisplayWebBrowserCode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/DisplayWebBrowserCode/CS/Form1.cs#2)]
     [!code-vb[DisplayWebBrowserCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/DisplayWebBrowserCode/VB/Form1.vb#2)]  
  
## <a name="robust-programming"></a><span data-ttu-id="41152-118">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="41152-118">Robust Programming</span></span>  
 <span data-ttu-id="41152-119">Всегда тестируйте значение <xref:System.Windows.Forms.WebBrowser.Document%2A>, прежде чем пытаться его извлечь.</span><span class="sxs-lookup"><span data-stu-id="41152-119">Always test the value of <xref:System.Windows.Forms.WebBrowser.Document%2A> before attempting to retrieve it.</span></span> <span data-ttu-id="41152-120">Если текущая страница не закончила загружаться, значит, <xref:System.Windows.Forms.WebBrowser.Document%2A> либо один или несколько дочерних объектов еще не инициализированы.</span><span class="sxs-lookup"><span data-stu-id="41152-120">If the current page is not finished loading, <xref:System.Windows.Forms.WebBrowser.Document%2A> or one or more of its child objects may not be initialized.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41152-121">См. также</span><span class="sxs-lookup"><span data-stu-id="41152-121">See also</span></span>
- [<span data-ttu-id="41152-122">Использование управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="41152-122">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
- [<span data-ttu-id="41152-123">Общие сведения об элементе управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="41152-123">WebBrowser Control Overview</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-overview.md)
