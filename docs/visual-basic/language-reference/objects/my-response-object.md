---
title: Объект My.Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: d5f49529a2593093a234babc22f64b591ea3cc61
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43479816"
---
# <a name="myresponse-object"></a><span data-ttu-id="ffd40-102">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="ffd40-102">My.Response Object</span></span>
<span data-ttu-id="ffd40-103">Получает <xref:System.Web.HttpResponse> объект, связанный с <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="ffd40-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="ffd40-104">Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.</span><span class="sxs-lookup"><span data-stu-id="ffd40-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffd40-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ffd40-105">Remarks</span></span>  
 <span data-ttu-id="ffd40-106">`My.Response` Объект содержит текущий <xref:System.Web.HttpResponse> объект, связанный со страницей.</span><span class="sxs-lookup"><span data-stu-id="ffd40-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="ffd40-107">`My.Response` Объект доступен только для [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="ffd40-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffd40-108">Пример</span><span class="sxs-lookup"><span data-stu-id="ffd40-108">Example</span></span>  
 <span data-ttu-id="ffd40-109">Следующий пример получает коллекцию заголовков из `My.Request` и использует `My.Response` объект для записи его на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="ffd40-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="ffd40-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ffd40-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="ffd40-111">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="ffd40-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
