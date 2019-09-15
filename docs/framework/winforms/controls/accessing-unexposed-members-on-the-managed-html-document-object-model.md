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
ms.openlocfilehash: 525ef52ecbbc61fba787fa8286c56c638d837faf
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70988401"
---
# <a name="accessing-unexposed-members-on-the-managed-html-document-object-model"></a><span data-ttu-id="1ab01-102">Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно</span><span class="sxs-lookup"><span data-stu-id="1ab01-102">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>
<span data-ttu-id="1ab01-103">Управляемый HTML-модель DOM (DOM) содержит класс с <xref:System.Windows.Forms.HtmlElement> именем, который предоставляет свойства, методы и события, общие для всех элементов HTML.</span><span class="sxs-lookup"><span data-stu-id="1ab01-103">The managed HTML Document Object Model (DOM) contains a class called <xref:System.Windows.Forms.HtmlElement> that exposes the properties, methods, and events that all HTML elements have in common.</span></span> <span data-ttu-id="1ab01-104">Тем не менее иногда требуется доступ к членам, которые управляемый интерфейс не предоставляет напрямую.</span><span class="sxs-lookup"><span data-stu-id="1ab01-104">Sometimes, however, you will need to access members that the managed interface does not directly expose.</span></span> <span data-ttu-id="1ab01-105">В этом разделе рассматриваются два способа доступа к неоткрытым членам, в том числе функции JScript и VBScript, определенные в веб-странице.</span><span class="sxs-lookup"><span data-stu-id="1ab01-105">This topic examines two ways for accessing unexposed members, including JScript and VBScript functions defined inside of a Web page.</span></span>  
  
## <a name="accessing-unexposed-members-through-managed-interfaces"></a><span data-ttu-id="1ab01-106">Доступ к неоткрытым членам через управляемые интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1ab01-106">Accessing Unexposed Members through Managed Interfaces</span></span>  
 <span data-ttu-id="1ab01-107"><xref:System.Windows.Forms.HtmlDocument>и <xref:System.Windows.Forms.HtmlElement> предоставляют четыре метода, которые обеспечивают доступ к неоткрытым членам.</span><span class="sxs-lookup"><span data-stu-id="1ab01-107"><xref:System.Windows.Forms.HtmlDocument> and <xref:System.Windows.Forms.HtmlElement> provide four methods that enable access to unexposed members.</span></span> <span data-ttu-id="1ab01-108">В следующей таблице показаны типы и соответствующие им методы.</span><span class="sxs-lookup"><span data-stu-id="1ab01-108">The following table shows the types and their corresponding methods.</span></span>  
  
|<span data-ttu-id="1ab01-109">Тип члена</span><span class="sxs-lookup"><span data-stu-id="1ab01-109">Member Type</span></span>|<span data-ttu-id="1ab01-110">Метод (ы)</span><span class="sxs-lookup"><span data-stu-id="1ab01-110">Method(s)</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1ab01-111">Свойства (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="1ab01-111">Properties (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.GetAttribute%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.SetAttribute%2A>|  
|<span data-ttu-id="1ab01-112">Методы</span><span class="sxs-lookup"><span data-stu-id="1ab01-112">Methods</span></span>|<xref:System.Windows.Forms.HtmlElement.InvokeMember%2A>|  
|<span data-ttu-id="1ab01-113">События (<xref:System.Windows.Forms.HtmlDocument>)</span><span class="sxs-lookup"><span data-stu-id="1ab01-113">Events (<xref:System.Windows.Forms.HtmlDocument>)</span></span>|<xref:System.Windows.Forms.HtmlDocument.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlDocument.DetachEventHandler%2A>|  
|<span data-ttu-id="1ab01-114">События (<xref:System.Windows.Forms.HtmlElement>)</span><span class="sxs-lookup"><span data-stu-id="1ab01-114">Events (<xref:System.Windows.Forms.HtmlElement>)</span></span>|<xref:System.Windows.Forms.HtmlElement.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlElement.DetachEventHandler%2A>|  
|<span data-ttu-id="1ab01-115">События (<xref:System.Windows.Forms.HtmlWindow>)</span><span class="sxs-lookup"><span data-stu-id="1ab01-115">Events (<xref:System.Windows.Forms.HtmlWindow>)</span></span>|<xref:System.Windows.Forms.HtmlWindow.AttachEventHandler%2A><br /><br /> <xref:System.Windows.Forms.HtmlWindow.DetachEventHandler%2A>|  
  
 <span data-ttu-id="1ab01-116">При использовании этих методов предполагается, что у вас есть элемент правильного базового типа.</span><span class="sxs-lookup"><span data-stu-id="1ab01-116">When you use these methods, it is assumed that you have an element of the correct underlying type.</span></span> <span data-ttu-id="1ab01-117">Предположим, что необходимо прослушивать `Submit` событие `FORM` элемента на HTML-странице, чтобы можно было выполнить `FORM`предварительную обработку значений до того, как пользователь отправит их на сервер.</span><span class="sxs-lookup"><span data-stu-id="1ab01-117">Suppose that you want to listen to the `Submit` event of a `FORM` element on an HTML page, so that you can perform some pre-processing on the `FORM`'s values before the user submits them to the server.</span></span> <span data-ttu-id="1ab01-118">В идеале, если вы управляете HTML, определите `FORM` для атрибута значение Unique. `ID`</span><span class="sxs-lookup"><span data-stu-id="1ab01-118">Ideally, if you have control over the HTML, you would define the `FORM` to have a unique `ID` attribute.</span></span>  
  
```html  
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
  
 <span data-ttu-id="1ab01-119">После <xref:System.Windows.Forms.WebBrowser> загрузки этой страницы в элемент управления можно <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> использовать метод для получения `FORM` во время выполнения, используя `form1` в качестве аргумента.</span><span class="sxs-lookup"><span data-stu-id="1ab01-119">After you load this page into the <xref:System.Windows.Forms.WebBrowser> control, you can use the <xref:System.Windows.Forms.HtmlDocument.GetElementById%2A> method to retrieve the `FORM` at run time using `form1` as the argument.</span></span>  
  
 [!code-csharp[System.Windows.Forms.HtmlElement#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/CS/Form1.cs#10)]
 [!code-vb[System.Windows.Forms.HtmlElement#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.HtmlElement/VB/Form1.vb#10)]  
  
## <a name="accessing-unmanaged-interfaces"></a><span data-ttu-id="1ab01-120">Доступ к неуправляемым интерфейсам</span><span class="sxs-lookup"><span data-stu-id="1ab01-120">Accessing Unmanaged Interfaces</span></span>  
 <span data-ttu-id="1ab01-121">Вы также можете получить доступ к неоткрытым членам управляемой модели HTML DOM с помощью неуправляемых интерфейсов COM, предоставляемых каждым классом DOM.</span><span class="sxs-lookup"><span data-stu-id="1ab01-121">You can also access unexposed members on the managed HTML DOM by using the unmanaged Component Object Model (COM) interfaces exposed by each DOM class.</span></span> <span data-ttu-id="1ab01-122">Это рекомендуется делать, если необходимо выполнить несколько вызовов для невидимых членов или если непредоставленные члены возвращают другие неуправляемые интерфейсы, не инкапсулированные управляемой моделью HTML DOM.</span><span class="sxs-lookup"><span data-stu-id="1ab01-122">This is recommended if you have to make several calls against unexposed members, or if the unexposed members return other unmanaged interfaces not wrapped by the managed HTML DOM.</span></span>  
  
 <span data-ttu-id="1ab01-123">В следующей таблице показаны все неуправляемые интерфейсы, предоставляемые через управляемую модель DOM HTML.</span><span class="sxs-lookup"><span data-stu-id="1ab01-123">The following table shows all of the unmanaged interfaces exposed through the managed HTML DOM.</span></span> <span data-ttu-id="1ab01-124">Щелкните каждую ссылку, чтобы получить объяснение его использования и пример кода.</span><span class="sxs-lookup"><span data-stu-id="1ab01-124">Click on each link for an explanation of its usage and for example code.</span></span>  
  
|<span data-ttu-id="1ab01-125">Тип</span><span class="sxs-lookup"><span data-stu-id="1ab01-125">Type</span></span>|<span data-ttu-id="1ab01-126">Неуправляемый интерфейс</span><span class="sxs-lookup"><span data-stu-id="1ab01-126">Unmanaged Interface</span></span>|  
|----------|-------------------------|  
|<xref:System.Windows.Forms.HtmlDocument>|<xref:System.Windows.Forms.HtmlDocument.DomDocument%2A>|  
|<xref:System.Windows.Forms.HtmlElement>|<xref:System.Windows.Forms.HtmlElement.DomElement%2A>|  
|<xref:System.Windows.Forms.HtmlWindow>|<xref:System.Windows.Forms.HtmlWindow.DomWindow%2A>|  
|<xref:System.Windows.Forms.HtmlHistory>|<xref:System.Windows.Forms.HtmlHistory.DomHistory%2A>|  
  
 <span data-ttu-id="1ab01-127">Самый простой способ использования интерфейсов COM — добавить ссылку на неуправляемую библиотеку DOM HTML (MSHTML. dll) из приложения, хотя это не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1ab01-127">The easiest way to use the COM interfaces is to add a reference to the unmanaged HTML DOM library (MSHTML.dll) from your application, although this is unsupported.</span></span> <span data-ttu-id="1ab01-128">Дополнительные сведения см. в [статье базы знаний 934368](https://support.microsoft.com/kb/934368).</span><span class="sxs-lookup"><span data-stu-id="1ab01-128">For more information, see [Knowledge Base Article 934368](https://support.microsoft.com/kb/934368).</span></span>  
  
## <a name="accessing-script-functions"></a><span data-ttu-id="1ab01-129">Доступ к функциям скрипта</span><span class="sxs-lookup"><span data-stu-id="1ab01-129">Accessing Script Functions</span></span>  
 <span data-ttu-id="1ab01-130">HTML-страница может определять одну или несколько функций с помощью языка сценариев, такого как JScript или VBScript.</span><span class="sxs-lookup"><span data-stu-id="1ab01-130">An HTML page can define one or more functions by using a scripting language such as JScript or VBScript.</span></span> <span data-ttu-id="1ab01-131">Эти функции помещаются внутри `SCRIPT` страницы страницы и могут выполняться по требованию или в ответ на событие в модели DOM.</span><span class="sxs-lookup"><span data-stu-id="1ab01-131">These functions are placed inside of a `SCRIPT` page in the page, and can be run on demand or in response to an event on the DOM.</span></span>  
  
 <span data-ttu-id="1ab01-132">Вы можете вызывать любые функции скриптов, определенные на HTML-странице, с <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> помощью метода.</span><span class="sxs-lookup"><span data-stu-id="1ab01-132">You can call any script functions you define in an HTML page using the <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A> method.</span></span> <span data-ttu-id="1ab01-133">Если метод скрипта возвращает HTML-элемент, можно использовать приведение для преобразования возвращаемого результата в <xref:System.Windows.Forms.HtmlElement>.</span><span class="sxs-lookup"><span data-stu-id="1ab01-133">If the script method returns an HTML element, you can use a cast to convert this return result to an <xref:System.Windows.Forms.HtmlElement>.</span></span> <span data-ttu-id="1ab01-134">Дополнительные сведения и примеры кода см. <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>в разделе.</span><span class="sxs-lookup"><span data-stu-id="1ab01-134">For details and example code, see <xref:System.Windows.Forms.HtmlDocument.InvokeScript%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab01-135">См. также</span><span class="sxs-lookup"><span data-stu-id="1ab01-135">See also</span></span>

- [<span data-ttu-id="1ab01-136">Использование управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="1ab01-136">Using the Managed HTML Document Object Model</span></span>](using-the-managed-html-document-object-model.md)
