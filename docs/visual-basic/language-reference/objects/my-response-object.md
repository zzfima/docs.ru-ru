---
title: "Объект My.Response | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MyWebExtension.Response
- My.Response
dev_langs:
- VB
helpviewer_keywords:
- My.Response object
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e2ae9a659bb7575023dfa1847c9d405d0f7d6ac3
ms.lasthandoff: 03/13/2017

---
# <a name="myresponse-object"></a>Объект My.Response
Возвращает <xref:System.Web.HttpResponse>объект, связанный с <xref:System.Web.UI.Page>.</xref:System.Web.UI.Page> </xref:System.Web.HttpResponse> Этот объект позволяет отправить клиенту данные ответа HTTP и содержит сведения об этом ответе.  
  
## <a name="remarks"></a>Примечания  
 `My.Response` Содержит текущий объект <xref:System.Web.HttpResponse>объект, связанный со страницей.</xref:System.Web.HttpResponse>  
  
 `My.Response` Объект доступен только для [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)] приложений.  
  
## <a name="example"></a>Пример  
 Следующий пример получает коллекцию заголовков из `My.Request` и использует `My.Response` объект для записи ее на страницу ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb&#1;](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Web.HttpResponse></xref:System.Web.HttpResponse>   
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)
