---
title: Объект My.Response
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 0a907d74112586e7b88c5a0a6f40080455454d7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597527"
---
# <a name="myresponse-object"></a><span data-ttu-id="a14fe-102">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="a14fe-102">My.Response Object</span></span>
<span data-ttu-id="a14fe-103">Возвращает <xref:System.Web.HttpResponse> объекта, связанного с <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="a14fe-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="a14fe-104">Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.</span><span class="sxs-lookup"><span data-stu-id="a14fe-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a14fe-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="a14fe-105">Remarks</span></span>  
 <span data-ttu-id="a14fe-106">`My.Response` Содержит текущий объект <xref:System.Web.HttpResponse> объект, связанный со страницей.</span><span class="sxs-lookup"><span data-stu-id="a14fe-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="a14fe-107">`My.Response` Объект доступен только для [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="a14fe-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a14fe-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a14fe-108">Example</span></span>  
 <span data-ttu-id="a14fe-109">Следующий пример получает коллекцию заголовков из `My.Request` объекта и использует `My.Response` объекта, чтобы записать его на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a14fe-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="a14fe-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a14fe-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="a14fe-111">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="a14fe-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
