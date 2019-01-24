---
title: Использование управляемой объектной модели HTML-документов
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: 1405bb43e971f02bafa892de84a6b8acde2e319b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691428"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="b2f6b-102">Использование управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="b2f6b-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="b2f6b-103">Управляемый HTML объектная модель документов (DOM) предоставляет оболочку на основе [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для классов HTML, предоставленных Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-103">The managed HTML document object model (DOM) provides a wrapper based on the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="b2f6b-104">Эти классы используются для управления HTML-страницами в <xref:System.Windows.Forms.WebBrowser> элемента управления, или создавать новые страницы с самого начала.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b2f6b-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="b2f6b-105">In This Section</span></span>  
 [<span data-ttu-id="b2f6b-106">Практическое руководство. Доступ к объектной модели управляемого HTML-документ</span><span class="sxs-lookup"><span data-stu-id="b2f6b-106">How to: Access the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="b2f6b-107">Описывается, как получить допустимый экземпляр <xref:System.Windows.Forms.HtmlDocument> из приложения Windows Forms или <xref:System.Windows.Forms.UserControl> размещенного в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="b2f6b-108">Практическое руководство. Доступ к исходному коду HTML с объектной модели управляемого HTML-документ</span><span class="sxs-lookup"><span data-stu-id="b2f6b-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="b2f6b-109">Описывает, как получить исходный код HTML исходном, неизмененном и способах получения источника «live», который отражает текущее состояние модели DOM.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="b2f6b-110">Практическое руководство. Изменение стилей элемента в объектной модели управляемого HTML-документ</span><span class="sxs-lookup"><span data-stu-id="b2f6b-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="b2f6b-111">Описывает способ управления стилями, которые используются для управления визуальное отображение элементов.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="b2f6b-112">Доступ к фреймам с использованием управляемой объектной модели HTML-документов</span><span class="sxs-lookup"><span data-stu-id="b2f6b-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="b2f6b-113">Описание кадры и наборы фреймов и как получить доступ к модели DOM рамки.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="b2f6b-114">Доступ к членам управляемой объектной модели документов HTML, доступ к которым не предоставляется явно</span><span class="sxs-lookup"><span data-stu-id="b2f6b-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](../../../../docs/framework/winforms/controls/accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="b2f6b-115">Описывает, как получить доступ к элементам базовой модели DOM, у которых нет управляемый эквивалент.</span><span class="sxs-lookup"><span data-stu-id="b2f6b-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b2f6b-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="b2f6b-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="b2f6b-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="b2f6b-117">Related Sections</span></span>  
 [<span data-ttu-id="b2f6b-118">Элемент управления WebBrowser</span><span class="sxs-lookup"><span data-stu-id="b2f6b-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)  
  
## <a name="see-also"></a><span data-ttu-id="b2f6b-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b2f6b-119">See also</span></span>
- [<span data-ttu-id="b2f6b-120">Сведения об объектной модели DHTML</span><span class="sxs-lookup"><span data-stu-id="b2f6b-120">About the DHTML Object Model</span></span>](https://msdn.microsoft.com/library/default.asp?url=/workshop/author/om/doc_object.asp)
