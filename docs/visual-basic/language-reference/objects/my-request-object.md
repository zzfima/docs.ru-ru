---
title: Объект My.Request (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: f2c43afb723944293907d0efbb4cf3cc66a40e1e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485616"
---
# <a name="myrequest-object"></a>Объект My.Request
Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.  
  
## <a name="remarks"></a>Примечания  
 Объект `My.Request` содержит сведения о текущем HTTP-запросе.  
  
 Объект `My.Request` доступен только для приложений ASP.NET.  
  
## <a name="example"></a>Пример  
 Следующий пример получает коллекцию заголовков из `My.Request` и использует `My.Response` объект для записи его на страницу ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Web.HttpRequest>  
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)
