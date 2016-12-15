---
title: "Объект My.Request | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "My.MyWebExtension.Request"
  - "My.Request"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Request - объект"
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Объект My.Request
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Возвращает объект <xref:System.Web.HttpRequest> для запрашиваемой страницы.  
  
## Заметки  
 Объект `My.Request` содержит сведения о текущем запросе HTTP.  
  
 Объект `My.Request` доступен только для приложений ASP.NET.  
  
## Пример  
 Следующий пример получает коллекцию заголовков из объекта `My.Request` и использует `My.Response` для записи ее на страницу ASP.NET.  
  
 [!code-vb[VbVbalrMyWeb#1](../../../visual-basic/language-reference/objects/codesnippet/VisualBasic/my-request-object_1.aspx)]  
  
## См. также  
 <xref:System.Web.HttpRequest>   
 [Объект My.Response](../../../visual-basic/language-reference/objects/my-response-object.md)