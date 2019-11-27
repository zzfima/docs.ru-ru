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
# <a name="myresponse-object"></a>Объект My.Response
Возвращает объект <xref:System.Web.HttpResponse>, связанный с <xref:System.Web.UI.Page>. Этот объект позволяет отправлять клиенту данные HTTP-ответа и содержит сведения об этом ответе.  
  
## <a name="remarks"></a>Примечания  
 Объект `My.Response` содержит текущий объект <xref:System.Web.HttpResponse>, связанный со страницей.  
  
 Объект `My.Response` доступен только для приложений ASP.NET.  
  
## <a name="example"></a>Пример  
 Следующий пример получает коллекцию заголовков из объекта `My.Request` и использует объект `My.Response` для записи на страницу ASP.NET.  
  
 [!code-aspx-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>См. также:

- <xref:System.Web.HttpResponse>
- [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
