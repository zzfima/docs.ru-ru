---
title: "Как создать фабрику каналов и использовать ее для создания каналов и управления ими | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 018dcc30-9f61-419e-af8e-412a85e8d282
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Как создать фабрику каналов и использовать ее для создания каналов и управления ими
Класс <xref:System.ServiceModel.DuplexChannelFactory%601> предоставляет средства для создания и управления дуплексными каналами различных типов, которые используются клиентами для передачи сообщений в конечные точки служб и приема сообщений из конечных точек служб.  
  
## Пример  
 В следующем коде показано создание фабрики каналов и ее использование для создания каналов и управления ими.  
  
 [!code-csharp[S_CustomAuthentication#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_customauthentication/cs/instance.cs#1)]  
  
## См. также  
 <xref:System.ServiceModel.DuplexChannelFactory%601>