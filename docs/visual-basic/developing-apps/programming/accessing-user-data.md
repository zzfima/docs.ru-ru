---
title: "Доступ к пользователя (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "данные [Visual Basic], доступ к данным пользователя"
  - "имена доменов, извлечение"
  - "примеры [Visual Basic], доступ к данным пользователя"
  - "имена для входа"
  - "My.User - объект, задачи"
  - "данные пользователя, доступ"
  - "данные пользователя, домен"
  - "имена пользователей, извлечение"
ms.assetid: 32492a15-ee59-4a63-a1f1-9b24cc13140a
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Доступ к пользователя (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

В этом разделе перечислены страницы, посвященные работе с объектом `My.User` и задачам, которые можно выполнить с помощью этого объекта.  
  
 Объект `My.User` предоставляет доступ к сведениям о пользователе, который вошел в систему, возвращая объект, реализующий интерфейс <xref:System.Security.Principal.IPrincipal>.  
  
## Задачи  
  
|Целевой тип|См.|  
|-----------------|---------|  
|Получение имени пользователя для входа в систему.|<xref:Microsoft.VisualBasic.ApplicationServices.User.Name%2A>|  
|Получение имени домена пользователя, если приложение использует проверку подлинности Windows|<xref:Microsoft.VisualBasic.ApplicationServices.User.CurrentPrincipal>|  
|Определение роли пользователя|<xref:Microsoft.VisualBasic.ApplicationServices.User.IsInRole%2A>|  
  
## См. также  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>