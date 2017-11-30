---
title: "Объект My.Response"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
helpviewer_keywords: My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76d0e701107add0d5bd468ba7a829759739e0cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="myresponse-object"></a><span data-ttu-id="14ccb-102">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="14ccb-102">My.Response Object</span></span>
<span data-ttu-id="14ccb-103">Возвращает <xref:System.Web.HttpResponse> объекта, связанного с <xref:System.Web.UI.Page>.</span><span class="sxs-lookup"><span data-stu-id="14ccb-103">Gets the <xref:System.Web.HttpResponse> object associated with the <xref:System.Web.UI.Page>.</span></span> <span data-ttu-id="14ccb-104">Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.</span><span class="sxs-lookup"><span data-stu-id="14ccb-104">This object allows you to send HTTP response data to a client and contains information about that response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14ccb-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="14ccb-105">Remarks</span></span>  
 <span data-ttu-id="14ccb-106">`My.Response` Содержит текущий объект <xref:System.Web.HttpResponse> объект, связанный со страницей.</span><span class="sxs-lookup"><span data-stu-id="14ccb-106">The `My.Response` object contains the current <xref:System.Web.HttpResponse> object associated with the page.</span></span>  
  
 <span data-ttu-id="14ccb-107">`My.Response` Объект доступен только для [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] приложений.</span><span class="sxs-lookup"><span data-stu-id="14ccb-107">The `My.Response` object is only available for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ccb-108">Пример</span><span class="sxs-lookup"><span data-stu-id="14ccb-108">Example</span></span>  
 <span data-ttu-id="14ccb-109">Следующий пример получает коллекцию заголовков из `My.Request` объекта и использует `My.Response` объекта, чтобы записать его на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="14ccb-109">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="14ccb-110">См. также</span><span class="sxs-lookup"><span data-stu-id="14ccb-110">See Also</span></span>  
 <xref:System.Web.HttpResponse>  
 [<span data-ttu-id="14ccb-111">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="14ccb-111">My.Request Object</span></span>](../../../visual-basic/language-reference/objects/my-request-object.md)
