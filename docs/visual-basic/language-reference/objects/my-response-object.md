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
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45989753"
---
# <a name="myresponse-object"></a>Объект My.Response
Получает <xref:System.Web.HttpResponse> объект, связанный с <xref:System.Web.UI.Page>. Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.  
  
## <a name="remarks"></a>Примечания  
 `My.Response` Объект содержит текущий <xref:System.Web.HttpResponse> объект, связанный со страницей.  
  
 `My.Response` Объект доступен только для [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] приложений.  
  
## <a name="example"></a>Пример  
 Следующий пример получает коллекцию заголовков из `My.Request` и использует `My.Response` объект для записи его на страницу ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Web.HttpResponse>  
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
