---
title: "Объект My.Response | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Response"
  - "My.Response"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Response - объект"
ms.assetid: 626359bc-3165-40b4-bfaf-2c610e26eb5b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Объект My.Response
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Получает объект <xref:System.Web.HttpResponse>, связанный с <xref:System.Web.UI.Page>.  Этот объект позволяет отправить клиенту ответные данные HTTP и содержит сведения об этом ответе.  
  
## Заметки  
 Объект `My.Response`, содержит текущий объект <xref:System.Web.HttpResponse>, связанный со страницей.  
  
 Объект `My.Response` доступен только для приложений [!INCLUDE[vstecasp](../../../csharp/language-reference/preprocessor-directives/includes/vstecasp_md.md)].  
  
## Пример  
 Следующий пример получает коллекцию заголовков из объекта `My.Request` и использует `My.Response` для записи ее на страницу ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-response-object_1.aspx)]  
  
## См. также  
 <xref:System.Web.HttpResponse>   
 [Объект My.Request](../../../visual-basic/language-reference/objects/my-request-object.md)