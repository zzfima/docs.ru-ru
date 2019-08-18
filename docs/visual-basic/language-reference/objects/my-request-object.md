---
title: Объект My. Request (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: da17872acb839cdcdfa7f80c3f58f26dc25d0ab5
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567470"
---
# <a name="myrequest-object"></a><span data-ttu-id="27614-102">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="27614-102">My.Request Object</span></span>
<span data-ttu-id="27614-103">Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.</span><span class="sxs-lookup"><span data-stu-id="27614-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27614-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="27614-104">Remarks</span></span>  
 <span data-ttu-id="27614-105">Объект `My.Request` содержит сведения о текущем HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="27614-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="27614-106">Объект `My.Request` доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="27614-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27614-107">Пример</span><span class="sxs-lookup"><span data-stu-id="27614-107">Example</span></span>  
 <span data-ttu-id="27614-108">Следующий пример получает коллекцию заголовков из `My.Request` объекта и `My.Response` использует объект для записи на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="27614-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="27614-109">См. также</span><span class="sxs-lookup"><span data-stu-id="27614-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="27614-110">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="27614-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
