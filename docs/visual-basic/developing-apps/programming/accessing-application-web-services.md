---
title: "Доступ к веб-службам приложения (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "приложения [Visual Basic], веб-службы"
  - "My.WebServices - объект"
  - "веб-службы, My.WebServices - объект"
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Доступ к веб-службам приложения (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Объект `My.WebServices` предоставляет экземпляр каждой веб\-службы, на которую ссылается текущий проект.  Каждый экземпляр создается по запросу.  Доступ к этим веб\-службам можно получить через свойства объекта `My.WebServices`.  Имя свойства совпадает с именем веб\-службы, к которой обращается свойство.  Любой класс, наследуемый от <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> — это веб\-служба.  
  
## Задачи  
 В следующей таблице перечислены возможные способы доступа к веб\-службам, на которые ссылается приложение.  
  
|||  
|-|-|  
|Целевой тип|См.|  
|Вызов веб\-службы|[Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
|Вызов веб\-службы в асинхронном режиме и обработка события при его завершении|[Практическое руководство. Асинхронный вызов веб\-службы](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|  
  
## См. также  
 [Объект My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md)