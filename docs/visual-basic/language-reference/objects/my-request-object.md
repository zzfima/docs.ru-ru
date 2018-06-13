---
title: Объект My.Request
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 88c3a9a01b50a97b556fa94026df391248bdf912
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595892"
---
# <a name="myrequest-object"></a><span data-ttu-id="c3309-102">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="c3309-102">My.Request Object</span></span>
<span data-ttu-id="c3309-103">Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.</span><span class="sxs-lookup"><span data-stu-id="c3309-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3309-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="c3309-104">Remarks</span></span>  
 <span data-ttu-id="c3309-105">Объект `My.Request` содержит сведения о текущем HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="c3309-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="c3309-106">Объект `My.Request` доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c3309-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3309-107">Пример</span><span class="sxs-lookup"><span data-stu-id="c3309-107">Example</span></span>  
 <span data-ttu-id="c3309-108">Следующий пример получает коллекцию заголовков из `My.Request` объекта и использует `My.Response` объекта, чтобы записать его на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c3309-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## <a name="see-also"></a><span data-ttu-id="c3309-109">См. также</span><span class="sxs-lookup"><span data-stu-id="c3309-109">See Also</span></span>  
 <xref:System.Web.HttpRequest>  
 [<span data-ttu-id="c3309-110">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="c3309-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
