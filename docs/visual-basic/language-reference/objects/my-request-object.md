---
title: Объект My.Request
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 22329bc501c9bb75b1336dd5384ab5b23a98ac21
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350681"
---
# <a name="myrequest-object"></a><span data-ttu-id="3c949-102">Объект My.Request</span><span class="sxs-lookup"><span data-stu-id="3c949-102">My.Request Object</span></span>
<span data-ttu-id="3c949-103">Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.</span><span class="sxs-lookup"><span data-stu-id="3c949-103">Gets the <xref:System.Web.HttpRequest> object for the requested page.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c949-104">Заметки</span><span class="sxs-lookup"><span data-stu-id="3c949-104">Remarks</span></span>  
 <span data-ttu-id="3c949-105">Объект `My.Request` содержит сведения о текущем HTTP-запросе.</span><span class="sxs-lookup"><span data-stu-id="3c949-105">The `My.Request` object contains information about the current HTTP request.</span></span>  
  
 <span data-ttu-id="3c949-106">Объект `My.Request` доступен только для приложений ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3c949-106">The `My.Request` object is available only for ASP.NET applications.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c949-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3c949-107">Example</span></span>  
 <span data-ttu-id="3c949-108">Следующий пример получает коллекцию заголовков из объекта `My.Request` и использует объект `My.Response` для записи на страницу ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="3c949-108">The following example gets the header collection from the `My.Request` object and uses the `My.Response` object to write it to the ASP.NET page.</span></span>  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3c949-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3c949-109">See also</span></span>

- <xref:System.Web.HttpRequest>
- [<span data-ttu-id="3c949-110">Объект My.Response</span><span class="sxs-lookup"><span data-stu-id="3c949-110">My.Response Object</span></span>](../../../visual-basic/language-reference/objects/my-response-object.md)
