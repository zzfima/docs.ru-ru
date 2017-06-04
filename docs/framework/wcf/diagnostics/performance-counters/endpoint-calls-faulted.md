---
title: "Конечная точка: сбои вызовов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 271e6284-9c4b-465f-b619-069e1555a5e4
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Конечная точка: сбои вызовов
Имя счетчика: Calls Faulted  
  
## Описание  
 Количество вызовов данной конечной точки, которые возвратили сбой.В приложениях [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] методы служб передают информацию об ошибках обработки с помощью сообщений об ошибках SOAP.Сообщения об ошибках SOAP — это типы сообщений, которые включаются в метаданные, связанные с операцией службы, и таким образом создают контракт ошибок, который клиенты могут использовать для повышения надежности и интерактивности своей работы.Поскольку сообщения об ошибках SOAP передаются клиентам в формате XML, они поддерживают возможность взаимодействия.  
  
## См. также  
 [Задание и обработка сбоев в контрактах и службах](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)