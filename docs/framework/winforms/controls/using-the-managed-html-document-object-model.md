---
title: "Использование управляемой объектной модели HTML-документов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ff1004248e709b4b4913b90eb81f0726ab390c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="232a4-102">Использование управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="232a4-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="232a4-103">Управляемый HTML модель объектов документов (DOM) обеспечивает оболочку, основанную на [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для классов HTML, предоставленных Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="232a4-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="232a4-104">Эти классы используются для управления HTML-страницами в <xref:System.Windows.Forms.WebBrowser> элемента управления, или для создания новых страниц с начала.</span><span class="sxs-lookup"><span data-stu-id="232a4-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="232a4-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="232a4-105">In This Section</span></span>  
 [<span data-ttu-id="232a4-106">Практическое руководство. Доступ к управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="232a4-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="232a4-107">Описывает, как получить допустимый экземпляр <xref:System.Windows.Forms.HtmlDocument> из приложения Windows Forms или <xref:System.Windows.Forms.UserControl> размещенного в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="232a4-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="232a4-108">Практическое руководство. Доступ к исходному коду HTML с использованием управляемой объектной модели документов HTML</span><span class="sxs-lookup"><span data-stu-id="232a4-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="232a4-109">Описывает способы получения исходного, неизмененного HTML-код и получить «live» источника, которая отражает текущее состояние модели DOM.</span><span class="sxs-lookup"><span data-stu-id="232a4-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="232a4-110">Практическое руководство. Изменение стилей элемента в управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="232a4-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="232a4-111">Описание способов управления стилями, которые используются для управления визуальным представлением элементов.</span><span class="sxs-lookup"><span data-stu-id="232a4-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="232a4-112">Доступ к фреймам с использованием управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="232a4-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="232a4-113">Описание фреймы и наборы фреймов и как получить доступ к модели DOM рамки.</span><span class="sxs-lookup"><span data-stu-id="232a4-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="232a4-114">Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно</span><span class="sxs-lookup"><span data-stu-id="232a4-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="232a4-115">Описывает, как получить доступ к членам базовой модели DOM, у которых нет управляемый эквивалент.</span><span class="sxs-lookup"><span data-stu-id="232a4-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="232a4-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="232a4-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="232a4-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="232a4-117">Related Sections</span></span>  
 [<span data-ttu-id="232a4-118">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="232a4-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="232a4-119">См. также</span><span class="sxs-lookup"><span data-stu-id="232a4-119">See Also</span></span>  
 [<span data-ttu-id="232a4-120">Об объектной модели DHTML</span><span class="sxs-lookup"><span data-stu-id="232a4-120">About the DHTML Object Model</span></span>](http://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
