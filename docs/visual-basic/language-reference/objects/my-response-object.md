---
title: Объект My. Response (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: a50701998011c25c600c2a3763459c1aba3cc59a
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567456"
---
# <a name="myresponse-object"></a><span data-ttu-id="3d7d9-102">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="3d7d9-102">My.Response Object</span></span>
<span data-ttu-id="3d7d9-103">Возвращает объект, <xref:System.Web.UI.Page>связанный с объектом. <xref:System.Web.HttpResponse></span><span class="sxs-lookup"><span data-stu-id="3d7d9-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="3d7d9-104">Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.</span><span class="sxs-lookup"><span data-stu-id="3d7d9-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d7d9-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3d7d9-105">Remarks</span></span>  
 <span data-ttu-id="3d7d9-106">Объект содержит текущий <xref:System.Web.HttpResponse> объект, связанный со страницей. `My.Response`</span><span class="sxs-lookup"><span data-stu-id="3d7d9-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="3d7d9-107">`My.Response` Объект доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3d7d9-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d7d9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3d7d9-108">Example</span></span>  
 <span data-ttu-id="3d7d9-109">Следующий пример получает коллекцию заголовков из `My.Request` объекта и `My.Response` использует объект для записи на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3d7d9-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3d7d9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="3d7d9-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="3d7d9-111">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="3d7d9-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
