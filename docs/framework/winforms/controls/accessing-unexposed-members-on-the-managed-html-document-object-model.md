---
title: Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- unexposed members
- managed HTML DOM [Windows Forms], accessing unexposed members
ms.assetid: 762295bd-2355-4aa7-b43c-5bff997a33e6
ms.openlocfilehash: 8767ef0fb484d43ffad4888affebb9d6bb74cc3a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43384644"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="5ab61-102">Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно</span><span class="sxs-lookup"><span data-stu-id="5ab61-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="5ab61-103">Управляемые объектной модели (DOM) HTML документа содержит класс с именем <xref:System.Windows.Forms.HtmlElement> , предоставляющая свойства, методы и события, общие для всех элементов HTML.</span><span class="sxs-lookup"><span data-stu-id="5ab61-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="5ab61-104">Иногда тем не менее, необходимо будет получить доступ к членам, которые управляемый интерфейс не предоставляется напрямую.</span><span class="sxs-lookup"><span data-stu-id="5ab61-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="5ab61-105">В этом разделе рассматриваются два способа получения доступа к членам, не предоставленным явно, включая [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] и функции VBScript, определенные внутри веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="5ab61-105">This topic examines two ways for accessing unexposed members, including [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="5ab61-106">Доступ к членам, не предоставленным явно с помощью управляемых интерфейсов</span><span class="sxs-lookup"><span data-stu-id="5ab61-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="5ab61-107"><xref:System.Windows.Forms.HtmlDocument> и <xref:System.Windows.Forms.HtmlElement> предоставляют четыре метода, которые обеспечивают доступ к членам, не предоставленным явно.</span><span class="sxs-lookup"><span data-stu-id="5ab61-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="5ab61-108">Ниже приведены типы и соответствующие методы.</span><span class="sxs-lookup"><span data-stu-id="5ab61-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="5ab61-109">Тип члена</span><span class="sxs-lookup"><span data-stu-id="5ab61-109">Member Type</span></span>|<span data-ttu-id="5ab61-110">Методы</span><span class="sxs-lookup"><span data-stu-id="5ab61-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5ab61-111">Свойства (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="5ab61-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="5ab61-112">Методы</span><span class="sxs-lookup"><span data-stu-id="5ab61-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="5ab61-113">События (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="5ab61-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="5ab61-114">События (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="5ab61-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="5ab61-115">События (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="5ab61-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="5ab61-116">При использовании этих методов, предполагается, что имеется элемент Неправильный базовый тип.</span><span class="sxs-lookup"><span data-stu-id="5ab61-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="5ab61-117">Предположим, что требуется ожидать передачи данных для `Submit` событие `FORM` на HTML-странице, чтобы выполнить предварительную обработку `FORM`его значения перед их отправкой на сервер.</span><span class="sxs-lookup"><span data-stu-id="5ab61-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="5ab61-118">В идеале, если у вас есть контроль над HTML, необходимо определить `FORM` уникальный `ID` атрибута.</span><span class="sxs-lookup"><span data-stu-id="5ab61-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```  
<HTML>  
  
    <HEAD>  
        <TITLE>Form Page</TITLE>  
    </HEAD>  
  
    <BODY>  
        <FORM ID="form1">  
             ... form fields defined here ...  
        </FORM>  
    </BODY>  
  
</HTML>  
```  
  
 <span data-ttu-id="5ab61-119">После загрузки этой страницы в <xref:System.Windows.Forms.WebBrowser> элемента управления, можно использовать <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> метод для извлечения `FORM` во время выполнения с помощью `form1` в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="5ab61-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="5ab61-120">Доступ к неуправляемым интерфейсам</span><span class="sxs-lookup"><span data-stu-id="5ab61-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="5ab61-121">Можно также получить доступ к членов, не предоставленные явно в управляемая модель HTML DOM, используя неуправляемые интерфейсы компонента объекта модели (COM), предоставляемых каждый класс DOM.</span><span class="sxs-lookup"><span data-stu-id="5ab61-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="5ab61-122">Это рекомендуется, если у вас есть несколько вызовов к которым не предоставляется явно членов или не предоставленным явно члены возвращают неуправляемые интерфейсы, не заключаются в оболочку управляемому HTML DOM</span><span class="sxs-lookup"><span data-stu-id="5ab61-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="5ab61-123">В следующей таблице показаны все неуправляемые интерфейсы, предоставляемые через управляемому HTML DOM</span><span class="sxs-lookup"><span data-stu-id="5ab61-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="5ab61-124">Щелкните ссылку Описание его использования и пример кода.</span><span class="sxs-lookup"><span data-stu-id="5ab61-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="5ab61-125">Тип</span><span class="sxs-lookup"><span data-stu-id="5ab61-125">Type</span></span>|<span data-ttu-id="5ab61-126">Неуправляемый интерфейс</span><span class="sxs-lookup"><span data-stu-id="5ab61-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="5ab61-127">Самый простой способ использования интерфейсов COM является добавление ссылки на неуправляемую библиотеку HTML DOM (MSHTML.dll) из своего приложения, несмотря на то, что это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5ab61-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="5ab61-128">Дополнительные сведения см. в разделе [934368 статьи базы знаний](https://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="5ab61-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="5ab61-129">Функции доступа к скрипту</span><span class="sxs-lookup"><span data-stu-id="5ab61-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="5ab61-130">HTML-страницы можно определить одну или несколько функций с помощью языка сценариев, таких как [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] или VBScript.</span><span class="sxs-lookup"><span data-stu-id="5ab61-130">An HTML page can define one or more functions by using a scripting language such as [!INCLUDE[jsprjscript](../../../../includes/jsprjscript-md.md)] or VBScript.</span></span> <span data-ttu-id="5ab61-131">Эти функции помещаются внутри `SCRIPT` страницы на странице и могут выполняться по запросу или в ответ на событие в модели DOM.</span><span class="sxs-lookup"><span data-stu-id="5ab61-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="5ab61-132">Можно вызвать любую функцию скрипта, определяются в HTML-страницы с использованием <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="5ab61-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="5ab61-133">Если в метод скрипта возвращает HTML-элемент, можно использовать приведение преобразовать этот возвращаемый результат <xref:System.Windows.Forms.HtmlElement>.</span><span class="sxs-lookup"><span data-stu-id="5ab61-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="5ab61-134">Дополнительные сведения и пример кода, см. в разделе <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ab61-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ab61-135">См. также</span><span class="sxs-lookup"><span data-stu-id="5ab61-135">See Also</span></span>  
 [<span data-ttu-id="5ab61-136">Использование управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="5ab61-136">Using the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/using-the-managed-html-document-object-model.md)
