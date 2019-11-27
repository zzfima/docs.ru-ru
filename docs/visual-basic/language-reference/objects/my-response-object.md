---
title: Объект My.Response
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
ms.openlocfilehash: 522814ad48fb7548032b8a37779bb3ff6ca62413
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350655"
---
# <a name="myresponse-object"></a><span data-ttu-id="93602-102">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="93602-102">My.Response Object</span></span>
<span data-ttu-id="93602-103">Возвращает объект <xref:System.Web.HttpResponse>, связанный с <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="93602-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="93602-104">Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.</span><span class="sxs-lookup"><span data-stu-id="93602-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93602-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="93602-105">Remarks</span></span>  
 <span data-ttu-id="93602-106">Объект `My.Response` содержит текущий объект <xref:System.Web.HttpResponse>, связанный со страницей.</span><span class="sxs-lookup"><span data-stu-id="93602-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="93602-107">Объект `My.Response` доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="93602-107">The `My.Response` object is only available for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93602-108">Пример</span><span class="sxs-lookup"><span data-stu-id="93602-108">Example</span></span>  
 <span data-ttu-id="93602-109">Следующий пример получает коллекцию заголовков из объекта `My.Request` и использует объект `My.Response` для записи на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="93602-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="93602-110">См. также:</span><span class="sxs-lookup"><span data-stu-id="93602-110">See also</span></span>

- <xref:System.Web.HttpResponse>
- [<span data-ttu-id="93602-111">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="93602-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
