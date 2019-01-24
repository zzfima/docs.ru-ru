---
title: Как выполнить Доступ к объектной модели управляемого HTML-документ
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- HTML DOM [Windows Forms], accessing
- managed HTML DOM [Windows Forms], accessing
ms.assetid: 40fa5cd5-1ed8-42f6-a93f-9ac01608bbeb
ms.openlocfilehash: 8799ac9897771a7cdf5a1e473914f461e435c061
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637155"
---
# <a name="how-to-access-the-managed-html-document-object-model"></a><span data-ttu-id="a31de-102">Как выполнить Доступ к объектной модели управляемого HTML-документ</span><span class="sxs-lookup"><span data-stu-id="a31de-102">How to: Access the Managed HTML Document Object Model</span></span>
<span data-ttu-id="a31de-103">Получить доступ к управляемой объектной модели HTML-документа (DOM) можно из двух типов приложений.</span><span class="sxs-lookup"><span data-stu-id="a31de-103">You can access the managed HTML Document Object Model (DOM) from two types of applications:</span></span>  
  
-   <span data-ttu-id="a31de-104">Приложение Windows Forms (.EXE), в котором размещен управляемый элемент управления <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="a31de-104">A Windows Forms application (.exe) that hosted the managed <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="a31de-105">Эти две технологии дополняют друг друга: элемент управления <xref:System.Windows.Forms.WebBrowser> отображает страницу пользователю, а HTML DOM представляет логическую структуру документа.</span><span class="sxs-lookup"><span data-stu-id="a31de-105">These two technologies complement one another, with the <xref:System.Windows.Forms.WebBrowser> control displaying the page to the user and the HTML DOM representing the document's logical structure.</span></span>  
  
-   <span data-ttu-id="a31de-106">Windows Forms <xref:System.Windows.Forms.UserControl> размещается в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="a31de-106">A Windows Forms <xref:System.Windows.Forms.UserControl> hosted within Internet Explorer.</span></span> <span data-ttu-id="a31de-107">Вы можете открыть HTML DOM, который показывает страницу, где находится элемент управления <xref:System.Windows.Forms.UserControl>, и изменить структуру документа, открыть модальные диалоговые окна и т. д.</span><span class="sxs-lookup"><span data-stu-id="a31de-107">You can access the HTML DOM representing the page on which your <xref:System.Windows.Forms.UserControl> is hosted in order to change the document's structure or open modal dialog boxes, among many other possibilities.</span></span>  
  
### <a name="to-access-dom-from-a-windows-forms-application"></a><span data-ttu-id="a31de-108">Доступ к DOM из приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a31de-108">To access DOM from a Windows Forms application</span></span>  
  
1.  <span data-ttu-id="a31de-109">Разместите элемент управления <xref:System.Windows.Forms.WebBrowser> в приложении Windows Forms и наблюдайте за событием <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>.</span><span class="sxs-lookup"><span data-stu-id="a31de-109">Host a <xref:System.Windows.Forms.WebBrowser> control within your Windows Forms application and monitor for the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event.</span></span> <span data-ttu-id="a31de-110">Дополнительные сведения о размещении элементов управления и наблюдении за событиями см. в разделе [События](../../../../docs/standard/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="a31de-110">For details on hosting controls and monitoring for events, see [Events](../../../../docs/standard/events/index.md).</span></span>  
  
2.  <span data-ttu-id="a31de-111">Получите <xref:System.Windows.Forms.HtmlDocument> для текущей страницы, открыв свойство <xref:System.Windows.Forms.WebBrowser.Document%2A> элемента управления <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="a31de-111">Retrieve the <xref:System.Windows.Forms.HtmlDocument> for the current page by accessing the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span>  

### <a name="to-access-dom-from-a-usercontrol-hosted-in-internet-explorer"></a><span data-ttu-id="a31de-112">Доступ к DOM из элемента управления UserControl, размещенного в Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="a31de-112">To access DOM from a UserControl hosted in Internet Explorer</span></span>  
  
1.  <span data-ttu-id="a31de-113">Создайте собственный пользовательский класс, производный от класса <xref:System.Windows.Forms.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="a31de-113">Create your own custom derived class of the <xref:System.Windows.Forms.UserControl> class.</span></span> <span data-ttu-id="a31de-114">Дополнительные сведения см. в разделе [Как Создание составных элементов управления](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a31de-114">For more information, see [How to: Author Composite Controls](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md).</span></span>  
  
2.  <span data-ttu-id="a31de-115">Поместите в обработчик события загрузки для <xref:System.Windows.Forms.UserControl> следующий код:</span><span class="sxs-lookup"><span data-stu-id="a31de-115">Place the following code inside of your Load event handler for your <xref:System.Windows.Forms.UserControl>:</span></span>  
  
 [!code-csharp[AccessHTMLDOMControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/AccessHTMLDOMControl/cs/UserControl1.cs#1)]
 [!code-vb[AccessHTMLDOMControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/AccessHTMLDOMControl/vb/UserControl1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a31de-116">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a31de-116">Robust Programming</span></span>  
  
1.  <span data-ttu-id="a31de-117">При использовании DOM через элемент управления <xref:System.Windows.Forms.WebBrowser> необходимо подождать, пока появится событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted>, и только после этого запрашивать доступ к свойству <xref:System.Windows.Forms.WebBrowser.Document%2A> элемента управления <xref:System.Windows.Forms.WebBrowser>.</span><span class="sxs-lookup"><span data-stu-id="a31de-117">When using the DOM through the <xref:System.Windows.Forms.WebBrowser> control, you should always wait until the <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event occurs before attempting to access the <xref:System.Windows.Forms.WebBrowser.Document%2A> property of the <xref:System.Windows.Forms.WebBrowser> control.</span></span> <span data-ttu-id="a31de-118">Событие <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> порождается после загрузки всего документа. Если использовать DOM до того, как это произойдет, во время выполнения в приложении может возникнуть исключение.</span><span class="sxs-lookup"><span data-stu-id="a31de-118">The <xref:System.Windows.Forms.WebBrowser.DocumentCompleted> event is raised after the entire document has loaded; if you use the DOM before then, you risk causing a run-time exception in your application.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a31de-119">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a31de-119">.NET Framework Security</span></span>  
  
1.  <span data-ttu-id="a31de-120">Для получения доступа к управляемому HTML DOM приложение или <xref:System.Windows.Forms.UserControl> потребуют полного доверия.</span><span class="sxs-lookup"><span data-stu-id="a31de-120">Your application or <xref:System.Windows.Forms.UserControl> will require full trust in order to access the managed HTML DOM.</span></span> <span data-ttu-id="a31de-121">Если приложение Windows Forms развертывается с помощью [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], можно запросить полное доверие, используя повышение уровня разрешения или развертывание доверенных приложений (см. раздел [Защита приложений ClickOnce](/visualstudio/deployment/securing-clickonce-applications)).</span><span class="sxs-lookup"><span data-stu-id="a31de-121">If you are deploying a Windows Forms application using [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], you can request full trust using either Permission Elevation or Trusted Application Deployment; see [Securing ClickOnce Applications](/visualstudio/deployment/securing-clickonce-applications) for details.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a31de-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a31de-122">See also</span></span>
- [<span data-ttu-id="a31de-123">Использование управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="a31de-123">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
