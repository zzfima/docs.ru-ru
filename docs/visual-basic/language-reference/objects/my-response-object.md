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
# <a name="myresponse-object"></a>Объект My.Response
Возвращает объект, <xref:System.Web.UI.Page>связанный с объектом. <xref:System.Web.HttpResponse> Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.  
  
## <a name="remarks"></a>Примечания  
 Объект содержит текущий <xref:System.Web.HttpResponse> объект, связанный со страницей. `My.Response`  
  
 `My.Response` Объект доступен только для приложений ASP.NET.  
  
## <a name="example"></a>Пример  
 Следующий пример получает коллекцию заголовков из `My.Request` объекта и `My.Response` использует объект для записи на страницу ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Web.HttpResponse>
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
